---
title: blogdown archetype (template)
author: L. Collado-Torres
date: '2018-03-08'
slug: blogdown-archetype-template
categories:
  - rstats
tags:
  - Blog
  - rstats
header:
  caption: ''
  image: ''
  preview: yes
---



In a recent blog post I [wrote about having a template](http://lcolladotor.github.io/2018/02/17/r-markdown-blog-template/#.WqDOdpPwa50) for *[blogdown](https://CRAN.R-project.org/package=blogdown)* posts. I wanted to know if it was possible to do this and make my life (and others hopefully) easier for writing new blog posts that are ready to go with the features I frequently re-use. 

In my case, I like using *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>) for functions such as `CRANpkg()`, `Biocpkg()` and `Githubpkg()`. I also like using *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>) for citing with `citep()` packages or papers; I use `citation()` and `bib_metadata()` to get the necessary information, respectively. Furthermore, I prefer `devtools::session_info()` <a id='cite-Wickham_2022'></a>(<a href='https://CRAN.R-project.org/package=devtools'>Wickham, Hester, Chang, and Bryan, 2022</a>) over `sessionInfo()` since it provides information of where you got the package, which becomes specially relevant when using packages from GitHub. Finally, I like thanking the creators of the tools I use, which in this case is *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>).

I also like reminding myself how to do some common tasks. Basically, the equivalent of the new R Markdown file you get when using RStudio. In my case, I want to remind myself of the YAML options I frequently use (toc, fig height and width) or how to add screenshots.

My [first post](http://lcolladotor.github.io/2018/02/17/r-markdown-blog-template/#.WqDOdpPwa50) on this topic is actually rather messy. That's because at that time:

* I didn't know about [hugo archetypes](https://gohugo.io/content-management/archetypes/) which are _template_ files,
* I hadn't even thought of making the [Insert Image addin](http://lcolladotor.github.io/2018/03/07/blogdown-insert-image-addin/#.WqDRmpPwa50).

I went down the rabbit hole of archetypes and *[blogdown](https://CRAN.R-project.org/package=blogdown)*, reported an [issue resulated to this topic](https://github.com/rstudio/blogdown/issues/261) that was in the way of using archetypes for `.Rmd` posts. After some encouragement by Yihui Xie, I ended up fixing this issues in [my first pull request](https://github.com/rstudio/blogdown/pull/263) _ever_ to an RStudio package. The PR also added the `Archetype` option to the _New Post_ RStudio addin (which I used right now ^^). 

<img src="http://lcolladotor.github.io/post/2018-03-08-blogdown-archetype-template_files/Screen Shot 2018-03-08 at 1.05.13 AM.png" alt="new post addin with archetype option" width="400"/>

### Creating my *[blogdown](https://CRAN.R-project.org/package=blogdown)* archetype (template)

To make my archetype (template) for blog posts I looked at the GitHub repo for the theme I'm using. It contains an `archetypes` directory with several files. I just looked at the one called `post.md` (check it [here](https://github.com/gcushen/hugo-academic/blob/master/archetypes/post.md)) and copied it from `themes/hugo-academic/archetypes/post.md` to `archetypes/post.md`. Next I added my favorite R code below the last `+++` mark. You can check out the final version [here](https://github.com/lcolladotor/hugoblog/blob/master/archetypes/post.md). Below I display the version at the time of writing this blog post (I'm using a `.txt` extension otherwise the embedded gist doesn't look good, but you want it to end in `.md`).

<script src="https://gist.github.com/lcolladotor/c3e141e033306299d0946a76e71f2967.js"></script>

I couldn't get the archetype to respect some of the YAML that *[blogdown](https://CRAN.R-project.org/package=blogdown)* adds, but well, that's a single copy-paste I have to do now (if I actually decide to use the custom YAML options which are only for `.Rmd` posts).

I encourage you to make your own *[blogdown](https://CRAN.R-project.org/package=blogdown)* archetype (template). At least it should remind you to include reproducibility information which matters whenever any R code is involved.


### Acknowledgments


This blog post was made possible thanks to:

* *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* (<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
* *[blogdown](https://CRAN.R-project.org/package=blogdown)* (<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
* *[devtools](https://CRAN.R-project.org/package=devtools)* (<a href='https://CRAN.R-project.org/package=devtools'>Wickham, Hester, Chang, and Bryan, 2022</a>)
* *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* (<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>)

Yihui Xie also talked about my first PR in [his blog](https://yihui.name/en/2018/02/bite-sized-pull-requests/).

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

<p><a id='bib-Wickham_2022'></a><a href="#cite-Wickham_2022">[3]</a><cite>
H. Wickham, J. Hester, W. Chang, and J. Bryan.
<em>devtools: Tools to Make Developing R Packages Easier</em>.
R package version 2.4.5.
2022.
URL: <a href="https://CRAN.R-project.org/package=devtools">https://CRAN.R-project.org/package=devtools</a>.</cite></p>

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
##  callr           3.7.3      2022-11-02 [1] CRAN (R 4.3.0)
##  cli             3.6.1      2023-03-23 [1] CRAN (R 4.3.0)
##  colorout        1.2-2      2023-05-06 [1] Github (jalvesaq/colorout@79931fd)
##  crayon          1.5.2      2022-09-29 [1] CRAN (R 4.3.0)
##  devtools      * 2.4.5      2022-10-11 [1] CRAN (R 4.3.0)
##  digest          0.6.31     2022-12-11 [1] CRAN (R 4.3.0)
##  ellipsis        0.3.2      2021-04-29 [1] CRAN (R 4.3.0)
##  evaluate        0.21       2023-05-05 [1] CRAN (R 4.3.0)
##  fastmap         1.1.1      2023-02-24 [1] CRAN (R 4.3.0)
##  fs              1.6.2      2023-04-25 [1] CRAN (R 4.3.0)
##  generics        0.1.3      2022-07-05 [1] CRAN (R 4.3.0)
##  glue            1.6.2      2022-02-24 [1] CRAN (R 4.3.0)
##  htmltools       0.5.5      2023-03-23 [1] CRAN (R 4.3.0)
##  htmlwidgets     1.6.2      2023-03-17 [1] CRAN (R 4.3.0)
##  httpuv          1.6.11     2023-05-11 [1] CRAN (R 4.3.0)
##  httr            1.4.6      2023-05-08 [1] CRAN (R 4.3.0)
##  jquerylib       0.1.4      2021-04-26 [1] CRAN (R 4.3.0)
##  jsonlite        1.8.7      2023-06-29 [1] CRAN (R 4.3.0)
##  knitcitations * 1.0.12     2021-01-10 [1] CRAN (R 4.3.0)
##  knitr           1.43       2023-05-25 [1] CRAN (R 4.3.0)
##  later           1.3.1      2023-05-02 [1] CRAN (R 4.3.0)
##  lifecycle       1.0.3      2022-10-07 [1] CRAN (R 4.3.0)
##  lubridate       1.9.2      2023-02-10 [1] CRAN (R 4.3.0)
##  magrittr        2.0.3      2022-03-30 [1] CRAN (R 4.3.0)
##  memoise         2.0.1      2021-11-26 [1] CRAN (R 4.3.0)
##  mime            0.12       2021-09-28 [1] CRAN (R 4.3.0)
##  miniUI          0.1.1.1    2018-05-18 [1] CRAN (R 4.3.0)
##  pkgbuild        1.4.2      2023-06-26 [1] CRAN (R 4.3.0)
##  pkgload         1.3.2      2022-11-16 [1] CRAN (R 4.3.0)
##  plyr            1.8.8      2022-11-11 [1] CRAN (R 4.3.0)
##  prettyunits     1.1.1      2020-01-24 [1] CRAN (R 4.3.0)
##  processx        3.8.2      2023-06-30 [1] CRAN (R 4.3.0)
##  profvis         0.3.8      2023-05-02 [1] CRAN (R 4.3.0)
##  promises        1.2.0.1    2021-02-11 [1] CRAN (R 4.3.0)
##  ps              1.7.5      2023-04-18 [1] CRAN (R 4.3.0)
##  purrr           1.0.1      2023-01-10 [1] CRAN (R 4.3.0)
##  R6              2.5.1      2021-08-19 [1] CRAN (R 4.3.0)
##  Rcpp            1.0.10     2023-01-22 [1] CRAN (R 4.3.0)
##  RefManageR      1.4.0      2022-09-30 [1] CRAN (R 4.3.0)
##  remotes         2.4.2      2021-11-30 [1] CRAN (R 4.3.0)
##  rlang           1.1.1      2023-04-28 [1] CRAN (R 4.3.0)
##  rmarkdown       2.23       2023-07-01 [1] CRAN (R 4.3.0)
##  rstudioapi      0.14       2022-08-22 [1] CRAN (R 4.3.0)
##  sass            0.4.6.9000 2023-05-06 [1] Github (rstudio/sass@f248fe5)
##  sessioninfo     1.2.2      2021-12-06 [1] CRAN (R 4.3.0)
##  shiny           1.7.4      2022-12-15 [1] CRAN (R 4.3.0)
##  stringi         1.7.12     2023-01-11 [1] CRAN (R 4.3.0)
##  stringr         1.5.0      2022-12-02 [1] CRAN (R 4.3.0)
##  timechange      0.2.0      2023-01-11 [1] CRAN (R 4.3.0)
##  urlchecker      1.0.1      2021-11-30 [1] CRAN (R 4.3.0)
##  usethis       * 2.2.1      2023-06-23 [1] CRAN (R 4.3.0)
##  vctrs           0.6.3      2023-06-14 [1] CRAN (R 4.3.0)
##  xfun            0.39       2023-04-20 [1] CRAN (R 4.3.0)
##  xml2            1.3.4      2023-04-27 [1] CRAN (R 4.3.0)
##  xtable          1.8-4      2019-04-21 [1] CRAN (R 4.3.0)
##  yaml            2.3.7      2023-01-23 [1] CRAN (R 4.3.0)
## 
##  [1] /Library/Frameworks/R.framework/Versions/4.3-arm64/Resources/library
## 
## ──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```
