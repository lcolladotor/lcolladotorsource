---
title: The evolution of my academic career as seen through posters and talks thanks
  to hugo academic 4.1
author: L. Collado-Torres
date: '2019-04-10'
slug: the-evolution-of-my-academic-career-as-seen-through-posters-and-talks-thanks-to-hugo-academic-4-1
categories:
  - Web
  - rstats
tags:
  - Academia
  - Website
header:
  caption: ''
  image: ''
  preview: yes
---

The [`hugo-academic`](https://github.com/gcushen/hugo-academic) theme which powers my website is active and frequently updated. I don’t update my website that frequently anymore, but I recently found about many of their changes when I made the [CDSB website](https://comunidadbioinfo.github.io/).

{{% tweet user="CDSBMexico" id="1114003433755959296" %}}

One of the new features that I liked quite a bit was the ability to have landing pages for each person in your team. I wanted to improve my website’s section [describing the people I’ve mentored](http://lcolladotor.github.io/#mentoring) so I decided to update my personal website too. Once I started this process, I realized that talks and publications had drastically changed. You could now have an image per talk or publication, add tags to them and link them to projects. Furthermore, I noticed that I hadn’t uploaded all my posters nor the slides for all my talks. So this whole process of updating my website took quite a bit of time! All this new information is also reflected on my [CV](http://lcolladotor.github.io/#cv) now.

### The end result: alumni

First of all, I really like how the section [describing the people I’ve mentored](http://lcolladotor.github.io/#mentoring) looks now. You can see the faces of the alumni and navigate to a page describing them in more detail.

<img src="http://lcolladotor.github.io/post/2019-04-10-the-evolution-of-my-academic-career-as-seen-through-posters-and-talks-thanks-to-hugo-academic-4-1_files/Screen%20Shot%202019-04-10%20at%2011.33.54%20AM.png" width="700" />

For example, check [Amy Peterson](http://lcolladotor.github.io/authors/apeterson/#.XK4NIetKi50)’s landing page which includes links to all her profiles I know about. I was also able to add some pictures of a key event with her: her MPH capstone final presentation.

<img src="http://lcolladotor.github.io/post/2019-04-10-the-evolution-of-my-academic-career-as-seen-through-posters-and-talks-thanks-to-hugo-academic-4-1_files/Screen%20Shot%202019-04-10%20at%2011.35.08%20AM.png" width="700" />

### My academic career

In this new version of my website you can also quickly take a look at my academic career by browsing through my [talks](http://lcolladotor.github.io/talk/#.XK4Nr-tKi50) and [publications (papers, posters and a book chapter)](http://lcolladotor.github.io/publication/#.XK4N2OtKi50). The papers are fancier, but the [posters](http://lcolladotor.github.io/publication/#0) and the talks tell you a more detailed story of how I’ve advanced through my career so far with in progress talks and posters showing some ideas, many of which we discareded in the end. For example, you can look at the [poster I presented at BioC2010](http://lcolladotor.github.io/publication/poster2010bioc/#.XK4OUOtKi50) which is when I met Rafa and Ingo from JHU Biostat. Through the posters and talks you can see how the [`derfinder` project](http://lcolladotor.github.io/project/derfinder/#.XK4PJOtKi50) came to be and culminated in the [publication describing the software](http://lcolladotor.github.io/publication/derfinder/#.XK4PLetKi50), which was my main Ph.D. project. I like how all the talks and posters related to `derfinder` can easily be found through the [project](http://lcolladotor.github.io/project/derfinder/#.XK4PJOtKi50) page. The talks now include my [Ph.D. defense talk](http://lcolladotor.github.io/talk/defense2016/#.XK4PiOtKi50) 🙌🏽✌🏽.

You can also see how the templates I used for making [talks](http://lcolladotor.github.io/talk/#.XK4RFetKi50) evolved through time starting with my [joint undergrad project](http://lcolladotor.github.io/talk/fagos2008/#.XK4OnOtKi50) with [Sur Herrera-Paredes](https://twitter.com/sur_hp). You can find some presentaitons made with Beamer, others with `knitr` (before `rmarkdown` existed), some with RStudio presentations, as well as different PowerPoint templates.

Overall, I’m very happy with my new website and I hope that you enjoy browsing through my academic career. I’ll use it to movitate others by showing them that we all start somewhere and it takes time and effort to grow.

### Some code for udpating to hugo academic 4.1.0

If you are updating your `hugo-academic` website you should be prepared to spend a significant amount of time if you want to include all the details I included. It took me most of my Saturday, Monday afternoon, and several hours on Tuesday to update mine. Here’s some code I used in this process that might be helpful to you.

``` r
## I copied my lcolladotorsource/content/talk files to ~/Downloads/ugh-talks
## then I made a new directory named after the initial .md files
## I made this process easier when updating my publications
## (see further below)
p_ori <- '~/Downloads/ugh-talks/'
p_new <- '/users/lcollado/Dropbox/code/lcolladotorsource/content/talk'
f <- dir(p_ori)
ff <- gsub('.md', '', f)


## For testing
# i <- 1

for(i in seq_len(length(f))) {

    f_initial <- file.path(p_ori, f[i])
  f_new <- file.path(p_new, ff[i], 'index.md')
  
  initial <- readLines(f_initial)
  new <- readLines(f_new)
  
  ## For a set of tags present in the previous version of hugo-academic
  ## I was using and the latest one, I found the initial strings
  ## such that I could find and replace the text.
  ## I also made sure to delete that info on the previous version
  ## so I could inspect rapidly if there was any information
  ## on the old version that I hadn't transfered to the new version.
  ## This typically involved some custom urls whose syntax is now
  ## different.
  for(j in c('location', 'abstract ', 'event_url', 'url_video', 'url_slides', 'title', 'url_pdf', 'event ', 'math')) {
    ## for debugging:
    # print(j)
    patt <- paste0('^', j)
    cont <- initial[grep(patt, initial)]
    initial[grep(patt, initial)] <- ''
    stopifnot(length(grep(patt, new)) > 0)
    # print(length(cont))
    new[grep(patt, new)] <- cont
  }
  
  ## For times I had to do this manually
  ## since the names for these tags changed
  j <- 'time_start'
  patt <- paste0('^', j)
  cont <- initial[grep(patt, initial)]
  initial[grep(patt, initial)] <- ''
  new[grep('^date ', new)] <- gsub('time_start', 'date', cont)
  
  ## and the end time wasn't always there
  cont2 <- initial[grep('^time_end', initial)]
  cont2 <- gsub('time_end', 'date_end', cont2)
  if(length(cont2) == 0) cont2 <- gsub('time_start', 'date_end', cont) else initial[grep('^time_end', initial)] <- ""
  new[grep('^date_end ', new)] <- cont2
  
  ## Similarly, the short version of the abstract now has
  ## a different name
  j <- 'abstract_short'
  patt <- paste0('^', j)
  cont <- initial[grep(patt, initial)]
  initial[grep(patt, initial)] <- ''
  new[grep('^summary', new)] <- gsub('abstract_short', 'summary', cont)
  
  ## Replace the old and new files with the updated versions ^^
  writeLines(initial, f_initial)
  writeLines(new, f_new)
}




### Publications

## Again, I moved the original files elsewhere
## and I copied the exampleSite/content/publication/clothing-search
## directory

## I then edited the clothing-search/index.md file
## a little bit before copying it to all the new folders below

p_ori <- '~/Downloads/ugh/'
p_new <- '/users/lcollado/Dropbox/code/lcolladotorsource/content/publication'
f <- dir(p_ori)
ff <- gsub('.md', '', f)


for(i in seq_len(length(f))) {
  
  
  ## Create the new directories from R
  ## coping my modified template publication using the
  ## clothing-search example
  system(paste('cp -R', file.path(p_new, 'clothing-search'), file.path(p_new, ff[i])))
  
  
  
  f_initial <- file.path(p_ori, f[i])
  f_new <- file.path(p_new, ff[i], 'index.md')
  
  initial <- readLines(f_initial)
  new <- readLines(f_new)
  
  ## Update tags just like I did for the talks
  for(j in c('title ', 'date ', 'math ', 'publication ', 'abstract ', 'url_pdf', 'url_project', 'url_dataset', 'url_video', 'url_slides', 'url_code', 'authors ')) {
    #print(j)
    patt <- paste0('^', j)
    cont <- initial[grep(patt, initial)]
    initial[grep(patt, initial)] <- ''
    stopifnot(length(grep(patt, new)) > 0)
    #print(length(cont))
    new[grep(patt, new)] <- cont
  }
  
  writeLines(initial, f_initial)
  writeLines(new, f_new)

}
```

``` bash
## I used imagemagick a few times to create the featured.jpg files
convert eurobioc2010-Bacterial-Collado.pdf[0] featured.jpg

## Other times I created those images by taking screenshots
## and then reducing the size to a max width/height of 1000 pixels
## to reduce the file sizes a bit
```

### Acknowledgments

This blog post was made possible thanks to:

- *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
- *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
- *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>)
- *[sessioninfo](https://CRAN.R-project.org/package=sessioninfo)* <a id='cite-Wickham_2021'></a>(<a href='https://CRAN.R-project.org/package=sessioninfo'>Wickham, Chang, Flight, Müller et al., 2021</a>)

### References

<p>
<a id='bib-Boettiger_2021'></a><a href="#cite-Boettiger_2021">\[1\]</a><cite>
C. Boettiger.
<em>knitcitations: Citations for ‘Knitr’ Markdown Files</em>.
R package version 1.0.12.
2021.
URL: <a href="https://CRAN.R-project.org/package=knitcitations">https://CRAN.R-project.org/package=knitcitations</a>.</cite>
</p>
<p>
<a id='bib-Oles_2023'></a><a href="#cite-Oles_2023">\[2\]</a><cite>
A. Oleś.
<em>BiocStyle: Standard styles for vignettes and other Bioconductor documents</em>.
R package version 2.28.0.
2023.
DOI: <a href="https://doi.org/10.18129/B9.bioc.BiocStyle">10.18129/B9.bioc.BiocStyle</a>.
URL: <a href="https://bioconductor.org/packages/BiocStyle">https://bioconductor.org/packages/BiocStyle</a>.</cite>
</p>
<p>
<a id='bib-Wickham_2021'></a><a href="#cite-Wickham_2021">\[3\]</a><cite>
H. Wickham, W. Chang, R. Flight, K. Müller, et al.
<em>sessioninfo: R Session Information</em>.
R package version 1.2.2.
2021.
URL: <a href="https://CRAN.R-project.org/package=sessioninfo">https://CRAN.R-project.org/package=sessioninfo</a>.</cite>
</p>
<p>
<a id='bib-Xie_2017'></a><a href="#cite-Xie_2017">\[4\]</a><cite>
Y. Xie, A. P. Hill, and A. Thomas.
<em>blogdown: Creating Websites with R Markdown</em>.
Boca Raton, Florida: Chapman and Hall/CRC, 2017.
ISBN: 978-0815363729.
URL: <a href="https://bookdown.org/yihui/blogdown/">https://bookdown.org/yihui/blogdown/</a>.</cite>
</p>

### Reproducibility

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
