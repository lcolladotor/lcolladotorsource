---
title: You just committed a large file and can't push to GitHub
author: L. Collado-Torres
date: '2020-03-18'
slug: you-just-committed-a-large-file-and-can-t-push-to-github
categories:
  - Computing
tags:
  - Git
  - github
subtitle: ''
summary: ''
authors: []
lastmod: '2020-03-18T08:39:21-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---




{{% callout note %}}
Oh ohh! 😱 What do you do now?
{{% /callout %}}

The data me and my colleagues work with is typically too big for our personal computers, so we use a high performance computing environment (cluster) and mostly interact with it through the command line terminal. As you might know, I'm a big fan of version control and I use [`git`](https://git-scm.com/) plus [GitHub](https://github.com/) for sharing our code ^[Between our personal computers and the JHPCE cluster, but also with collaborators and the community at large.]. That's why I've been advocating others to use it for a while and when they do, they run to me if they have some issues. A while back, my former student [Amy Peterson](/authors/apeterson/) wrote a blog post titled [git to know git: an 8 minute introduction](http://research.libd.org/rstatsclub/post/git-to-know-git/) which is useful if you are getting started. Amy also links to the excellent [Happy Git and GitHub for the useR](https://happygitwithr.com/) book.

### Recurrent problem: you just commited a large file and can't push to GitHub

One situation that I've frequently helped others with is when they use `git add *` or `git add .` and version control _every_ file in their project. They then do a commit such as `git commit -m "added all files"` and run `git push` to sync their files to GitHub. But oops, GitHub complains that you are trying to commit files larger than 50 Mb and even grinds to a halt if they are larger than 100 Mb. Which given that we work with large data, happens frequently (even a PDF file can be that big!).

Ok, so what can you do at this point? Remember, this is the scenario where you **just** made that commit. That is, it's the last commit. At that point, it's best to _undo your last git commit_ which is well described in [this website](https://www.git-tower.com/learn/git/faq/undo-last-commit). However, when you _undo_ a commit, you can either fully wipe out any changes (wipe them out fully from your disk, not only `git`'s version control!) or undo the version control step but also keep your files intact. The main solution then is to use:


```bash
git reset --soft HEAD~1
```

However, maybe you tried other commands and it's a bit more complicated than that. Which is why I greatly advise that you create a local backup of your `main_project` directory before you dive into commands such as `git reset`, specially whenever you see the `--hard` option being suggested. That is, do something like this:



```bash
## Nagivate to the parent directory of your main_project
cd directory_containing_your_project

## Check the full size of your project directory
du -sh main_project

## Do you have enough disk space?
df -h .

## If you have enough disk space, then create a full backup
cp -r main_project main_project_backup/
```


Once you are able to roll back the offending commit, instead of running `git add *` or `git add .` and similar commands, repeat the following cycle:

1. Check which files are not being version controlled (untracked) with `git status`.
2. Check how big each of your untracked files is. You can do so with `ls -lh` and `ls -lh some_pattern`.
3. Add the files or file patterns you want to avoid version controlling (the large files) to your `.gitignore` file ^[Note that you can also create `.gitignore` files inside each directory if you want to have tighter control. You could also ignore a full directory and the use `git add -f` to forcibly version control files, for example, `echo "my_subdir" >> .gitignore` plus `git add -f my_subdir/*.R` to forcibly version control the R script files inside `my_subdir` but ignore everything else.].
4. Double check that your pattern worked by confirming that these files do not show up as _untracked_ when you run `git status`.

Repeat this until the only remaining untracked files are those you actually want to version control and that are small enough ^[If you really want to version control large files, look into [`git lfs`](https://git-lfs.github.com/).].

And that's it! Keep version controlling your code and reap the benefits later on when you need to.

<iframe src="https://giphy.com/embed/KEXly2BwaldSlhY8BL" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/latenightseth-seth-meyers-lnsm-late-night-with-KEXly2BwaldSlhY8BL">via GIPHY</a></p>

We all run into this situation at some point (or multiple times), so please keep using version control. The benefits will outweigh the negatives!

### Use case story: the issue

Thanks to a colleague who gave me permission to share their use case, here we can dive down into a real life example. First, this was their description (edited for anonymity):

> Ran these, as per GitHub’s instructions, and it went fine


```bash
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:LieberInstitute/some_repository.git
git push -u origin master
```

> Even added a `.gitignore` with some instructions on what to ignore when committing

> But it wasn’t enough and I hadn’t come to appreciate yet that there’s no need to commit `.rda`’s or other very large files, so my `git push` died.

> Since these were already staged, I thought the next move was to make another commit with an edited `.gitignore` listing anything in my `rdas/`

> Putting me two branches ahead of master (Leo: commits I think)

> I got frustrated and thought then that ok, I want to go back two commits...

> my  Googling suggested me to go for `git reset --hard HEAD~2`...

> That’s when I started panicking 😭

My colleague started panicking at this point because they couldn't see the files anymore. That is, running `ls -lh rdas/` didn't list the files they had worked on really hard to create over the past months. But at this point, these large files were under version control by `git` ^[Stored and hidden in some way inside the `.git` directory.], just not available on `GitHub` due to the file size limitations.

> So then my panic Googling took me to https://stackoverflow.com/questions/5788037/recover-from-git-reset-hard

> where I thought ok I just can run `git reset HEAD@{2}` , which was


```bash
7cb9bac HEAD@{0}: reset: moving to HEAD@{2}
1e8499d HEAD@{1}: reset: moving to HEAD~2
f03b884 HEAD@{2}: commit: Committing EVERYTHING
7cb9bac HEAD@{3}: commit: Commiting EVERYTHING			<- this one
1e8499d HEAD@{4}: commit (initial): first commit
```

> And there it looked like not everything was quite lost, as I could see


```bash
$ git status
# On branch master
# Your branch is ahead of 'origin/master' by 1 commit.
#   (use "git push" to publish your local commits)
#
# Changes not staged for commit:
#   (use "git add/rm <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	deleted:    .RData
#	deleted:    .gitignore
#	deleted:    *.R ## Lots of files with this pattern
#	deleted:    *.sh ## same story about the file pattern
#	deleted:    pdfs/*.pdf
#	deleted:    rdas/*.rda
#	deleted:    tables/*.csv
#
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#	logs/
#	pdfs/*other*.pdf
#	rdas/*other*.rda
#	*other*.R
no changes added to commit (use "git add" and/or "git commit -a")
```

So now my colleague realizes that somehow `git` is version controlling the files, but the `deleted` label is still VERY scary!!

> And then I thought ok I just need to re-stage those deleted files...

> So I ran `git add -A` , but now I see


```bash
$ git status
# On branch master
# Your branch is ahead of 'origin/master' by 1 commit.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#	deleted:    .RData
#	deleted:    .gitignore
#	deleted:    *.R ## Lots of files with this pattern
#	deleted:    *.sh ## same story about the file pattern
#	deleted:    pdfs/*.pdf
#	deleted:    rdas/*.rda
#	deleted:    tables/*.csv
#	new file:   logs/*.Rout
#	new file:   logs/*.sh.*
#	new file:   pdfs/*other*.pdf
#	new file:   rdas/*other*.rda
#	new file:   *other*.R
#	renamed:    pdfs/*something*.pdf -> pdfs/*something_else*.pdf
#	renamed:    rdas/*something*.rda -> rdas/*something_else*.rda
```

> and clearly I don’t know what I’m doing so I stopped

> And thanked the lord you were online.  😭😭

> I promise I did some reviewing of resources and testing with local and JHPCE test dirs before

My colleague then pointed me to the directory with the files and we fixed their files.

### Use case story: the solution

Like I mentioned earlier, the first thing to do in cases like this is to create a backup. 


```bash
## Check how big it is
du -sh project_FINAL

## Create a backup
cp -r project_FINAL project_leo_backup/

## To wipe out the original copy
## proceed with EXTREME caution!
# rm -fr project_FINAL

## Then restore everything from your backup copy
cp -r project_leo_backup project_FINAL/
```

I actually messed up at one point and had to rely on this backup!! So, like I said,

{{% callout note %}}
Please backup everything before you start using `git reset` and similar commands!
{{% /callout %}}

Next, to undo all the `git rm` (deleting a file), I undid the `git add -A` step using a combination of `git reset` and `git checkout` (to restore files).


```bash
# https://stackoverflow.com/a/2125713/9374370
$ git reset HEAD
$ git checkout .

## check things
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean
$ git log
commit 7cb9bac5378500b35a0c22480a5961248ecf67ea (HEAD -> master)
Author: xx <xx@jhmi.edu>
Date:   Tue Mar 17 19:27:31 2020 -0400
    Commiting EVERYTHING
commit 1e8499d7d41cab6c12ea23ccdb2da8120b00a7f7 (origin/master)
Author: XX <xx@jhmi.edu>
Date:   Tue Mar 17 19:04:03 2020 -0400
    first commit

$ ls -lh rdas
total 6.2G
## I see tons of stuff (many of which I'm now the "owner" of)
```

I then finally used `git reset --soft` to undo the last commit.


```bash
# https://www.git-tower.com/learn/git/faq/undo-last-commit
git reset --soft HEAD~1 ## note that I'm not using --hard

## Everything is back to before that big commit
$ git log
commit 1e8499d7d41cab6c12ea23ccdb2da8120b00a7f7 (HEAD -> master, origin/master)
Author: XX <xx@jhmi.edu>
Date:   Tue Mar 17 19:04:03 2020 -0400
    first commit

## and the files are there =)
$ ls -lh rdas
total 6.2G
-rwxrwx--- 1 lcollado lieber_jaffe 690M Mar 18 00:22 *.rda ## exmaple file
```

Now that the directory and files have been restored to before all files were committed, we can proceed to ignore large files. For example, we can ignore the `rdas/` directory that has many large files that we don't want to version control ^[Maybe later we'll version control a few of them using `git add -f rdas/some_file.rda` but it'll be a targeted version control command.].


```bash
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.RData
	.gitignore
	*.R ## Lots of files with this pattern
	*.sh ## Lots of files with this pattern
	pdfs/
	rdas/
	tables/

$ echo "rdas" >> .gitignore

## Notice that rdas is not there anymore ^^
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.RData
	.gitignore
	*.R ## Lots of files with this pattern
	*.sh ## Lots of files with this pattern
	pdfs/
	tables/
```

And now we can update our `.gitignore` and push this small change (ignoring the `rdas/` directory) to GitHub.


```bash
$ git add .gitignore

$ git commit -m "Ignore rdas"
[master 52f1850] Ignore rdas
 1 file changed, 14 insertions(+)
 create mode 100755 .gitignore

$ git push
X11 forwarding request failed on channel 0
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 20 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 420 bytes | 210.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:LieberInstitute/some_repository.git
   1e8499d..52f1850  master -> master
```

And we are done!

<iframe src="https://giphy.com/embed/wzD3nQPA4gqHK" width="480" height="360" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/time-office-wzD3nQPA4gqHK">via GIPHY</a></p>

And I'll get some free beers hehe 🍻😄

> Omg you’re amazing beautiful lord n savior jesus christ

> Your next 10 beers are on me.

> plus 2 for the promotion 😄😇😎🙏😭

To which I replied

> hehe, I’ve simply only have had more practice at this than you (fixing xx’s repos mostly hehe)

> but yeah, backing up is the best thing you can do

> that actually **saved** me from my one `git reset --hard HEAD~1` command that should have `been git reset --soft HEAD~1`

### Misc notes

Note that you might also want to use `git status-size` in some situations.


```bash
## From https://github.com/jtloong/git-status-size
$ git status-size
```

Finally, if you are a [JHPCE](https://jhpce.jhu.edu/) user, I recommend including these lines in your `~/.bashrc` file.


```bash
## Load the git module by default when qrsh/qsub
## thanks to Jiong Yang
if [[ $HOSTNAME == compute-* ]]; then
    echo "Adding LIBD modules"
    module use /jhpce/shared/jhpce/modulefiles/libd
    echo "Loading git"
    module load git
    module load git-status-size/github
    module load git-lfs/2.8.0
    module load rmate/1.5.9 ## macOS users
    module load conda_R/3.6.x ## default R version
fi
```


### Acknowledgments

I greatly appreciate the anonymous user who reached out to me about this issue and had an excellent history of commands which allowed me to figure out a possible solution and then write this blog post (with their permission). We both hope that this information will be useful to ourselves and others in the future.


This blog post was made possible thanks to:

* *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
* *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
* *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>)
* *[sessioninfo](https://CRAN.R-project.org/package=sessioninfo)* <a id='cite-Wickham_2021'></a>(<a href='https://CRAN.R-project.org/package=sessioninfo'>Wickham, Chang, Flight, Müller et al., 2021</a>)

### References

<p><a id='bib-Boettiger_2021'></a><a href="#cite-Boettiger_2021">[1]</a><cite>
C. Boettiger.
<em>knitcitations: Citations for 'Knitr' Markdown Files</em>.
R package version 1.0.12.
2021.
URL: <a href="https://CRAN.R-project.org/package=knitcitations">https://CRAN.R-project.org/package=knitcitations</a>.</cite></p>

<p><a id='bib-Oles_2023'></a><a href="#cite-Oles_2023">[2]</a><cite>
A. Oleś.
<em>BiocStyle: Standard styles for vignettes and other Bioconductor documents</em>.
R package version 2.28.0.
2023.
DOI: <a href="https://doi.org/10.18129/B9.bioc.BiocStyle">10.18129/B9.bioc.BiocStyle</a>.
URL: <a href="https://bioconductor.org/packages/BiocStyle">https://bioconductor.org/packages/BiocStyle</a>.</cite></p>

<p><a id='bib-Wickham_2021'></a><a href="#cite-Wickham_2021">[3]</a><cite>
H. Wickham, W. Chang, R. Flight, K. Müller, et al.
<em>sessioninfo: R Session Information</em>.
R package version 1.2.2.
2021.
URL: <a href="https://CRAN.R-project.org/package=sessioninfo">https://CRAN.R-project.org/package=sessioninfo</a>.</cite></p>

<p><a id='bib-Xie_2017'></a><a href="#cite-Xie_2017">[4]</a><cite>
Y. Xie, A. P. Hill, and A. Thomas.
<em>blogdown: Creating Websites with R Markdown</em>.
Boca Raton, Florida: Chapman and Hall/CRC, 2017.
ISBN: 978-0815363729.
URL: <a href="https://bookdown.org/yihui/blogdown/">https://bookdown.org/yihui/blogdown/</a>.</cite></p>

### Reproducibility


```
## ─ Session info ───────────────────────────────────────────────────────────────────────────────────────────────────────
##  setting  value
##  version  R version 4.3.1 (2023-06-16)
##  os       macOS Ventura 13.4
##  system   aarch64, darwin20
##  ui       X11
##  language (EN)
##  collate  en_US.UTF-8
##  ctype    en_US.UTF-8
##  tz       America/New_York
##  date     2023-07-11
##  pandoc   3.1.5 @ /opt/homebrew/bin/ (via rmarkdown)
## 
## ─ Packages ───────────────────────────────────────────────────────────────────────────────────────────────────────────
##  package       * version    date (UTC) lib source
##  backports       1.4.1      2021-12-13 [1] CRAN (R 4.3.0)
##  bibtex          0.5.1      2023-01-26 [1] CRAN (R 4.3.0)
##  BiocManager     1.30.21    2023-06-10 [1] CRAN (R 4.3.0)
##  BiocStyle     * 2.28.0     2023-04-25 [1] Bioconductor
##  blogdown        1.18       2023-06-19 [1] CRAN (R 4.3.0)
##  bookdown        0.34       2023-05-09 [1] CRAN (R 4.3.0)
##  bslib           0.5.0      2023-06-09 [1] CRAN (R 4.3.0)
##  cachem          1.0.8      2023-05-01 [1] CRAN (R 4.3.0)
##  cli             3.6.1      2023-03-23 [1] CRAN (R 4.3.0)
##  colorout        1.2-2      2023-05-06 [1] Github (jalvesaq/colorout@79931fd)
##  digest          0.6.31     2022-12-11 [1] CRAN (R 4.3.0)
##  evaluate        0.21       2023-05-05 [1] CRAN (R 4.3.0)
##  fastmap         1.1.1      2023-02-24 [1] CRAN (R 4.3.0)
##  generics        0.1.3      2022-07-05 [1] CRAN (R 4.3.0)
##  glue            1.6.2      2022-02-24 [1] CRAN (R 4.3.0)
##  htmltools       0.5.5      2023-03-23 [1] CRAN (R 4.3.0)
##  httr            1.4.6      2023-05-08 [1] CRAN (R 4.3.0)
##  jquerylib       0.1.4      2021-04-26 [1] CRAN (R 4.3.0)
##  jsonlite        1.8.7      2023-06-29 [1] CRAN (R 4.3.0)
##  knitcitations * 1.0.12     2021-01-10 [1] CRAN (R 4.3.0)
##  knitr           1.43       2023-05-25 [1] CRAN (R 4.3.0)
##  lifecycle       1.0.3      2022-10-07 [1] CRAN (R 4.3.0)
##  lubridate       1.9.2      2023-02-10 [1] CRAN (R 4.3.0)
##  magrittr        2.0.3      2022-03-30 [1] CRAN (R 4.3.0)
##  plyr            1.8.8      2022-11-11 [1] CRAN (R 4.3.0)
##  R6              2.5.1      2021-08-19 [1] CRAN (R 4.3.0)
##  Rcpp            1.0.10     2023-01-22 [1] CRAN (R 4.3.0)
##  RefManageR      1.4.0      2022-09-30 [1] CRAN (R 4.3.0)
##  rlang           1.1.1      2023-04-28 [1] CRAN (R 4.3.0)
##  rmarkdown       2.23       2023-07-01 [1] CRAN (R 4.3.0)
##  rstudioapi      0.14       2022-08-22 [1] CRAN (R 4.3.0)
##  sass            0.4.6.9000 2023-05-06 [1] Github (rstudio/sass@f248fe5)
##  sessioninfo   * 1.2.2      2021-12-06 [1] CRAN (R 4.3.0)
##  stringi         1.7.12     2023-01-11 [1] CRAN (R 4.3.0)
##  stringr         1.5.0      2022-12-02 [1] CRAN (R 4.3.0)
##  timechange      0.2.0      2023-01-11 [1] CRAN (R 4.3.0)
##  xfun            0.39       2023-04-20 [1] CRAN (R 4.3.0)
##  xml2            1.3.4      2023-04-27 [1] CRAN (R 4.3.0)
##  yaml            2.3.7      2023-01-23 [1] CRAN (R 4.3.0)
## 
##  [1] /Library/Frameworks/R.framework/Versions/4.3-arm64/Resources/library
## 
## ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```
