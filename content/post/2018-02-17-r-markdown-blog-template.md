---
title: R markdown blog template
author: L. Collado-Torres
date: '2018-02-17'
categories:
  - rstats
tags:
  - rstats
  - Blog
slug: r-markdown-blog-template
output:
  blogdown::html_page:
    toc: no
    fig_width: 5
    fig_height: 5
---




This blog post is mostly for myself but maybe it's useful to others. It contains my current R markdown blog template. I initially posted this as a question at [StackOverflow](https://stackoverflow.com/questions/48844340/is-it-possible-to-create-a-rmd-file-template-for-the-blogdown-new-post-addin). Then I read how much a burden we put in [Yihui Xie](https://yihui.name/en/2018/02/career-crisis/) and decided that my current setup (copy-pasting) works just fine. In any case using `blogdown` with the RStudio IDE is much simpler than what I used to do in the past with [jekyll](http://lcolladotor.github.io/2013/11/09/new-Fellgernon-Bit-setup-in-Github/) or with even my prior [setup with blogdown](https://github.com/rstudio/blogdown/issues/42).

### Bibliography setup

First I define the citation information I'll need. By the way, I used [FAQ 7](https://yihui.name/knitr/faq/) for showing the R code chunk.

```
    ```{r bibsetup, echo=FALSE, message=FALSE, warning=FALSE}
    ## Load knitcitations with a clean bibliography
    library('knitcitations')
    cleanbib()
    cite_options(hyperlink = 'to.doc', citation_format = 'text', style = 'html')
    
    bib <- c('knitcitations' = citation('knitcitations'),
             'blogdown' = citation('blogdown')[2])
    ```
```





### Post content

This is where I typically start to edit since the bibliography chunk is hidden.


### R image

```
    ```{r 'plot'}
    ## This will create the /post/*_files/ directory
    ## where you can later copy the non-R images you want to use
    ## in the blog post
    plot(1:10, 10:1)
    ```
```

<img src="http://lcolladotor.github.io/post/2018-02-17-r-markdown-blog-template_files/figure-html/plot-1.png" width="480" />

Note that I modified the YAML portion of the post to set the figure width and height. You can also include a table of contents if you want, though it affects the summary of the post. Check the [output format](https://bookdown.org/yihui/blogdown/output-format.html) section of the `blogdown` book for more details <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>), including differences between `.Rmd` and `.Rmarkdown` files. Note that you can also use a `_output.yml` file as described there.

```
output:
  blogdown::html_page:
    toc: no
    fig_width: 5
    fig_height: 5
```

### Custom image syntax

Here I remind myself of different ways I can include external images. Check [blogdown issue 239](https://github.com/rstudio/blogdown/issues/239) for some background information.

Markdown syntax for custom image:

```
![](/post/2018-02-17-r-markdown-blog-template_files/LIBD.jpg)
```

![](http://lcolladotor.github.io/post/2018-02-17-r-markdown-blog-template_files/LIBD.jpg)

HTML syntax for centering image, including a link, and re-sizing the image to a fix width of 200 px.

```
<center>
<a href="http://lcolladotor.github.io/"><img alt = 'some website' width='200' src='/post/2018-02-17-r-markdown-blog-template_files/LIBD.jpg' /></a>
</center>
```


<center>
<a href="http://lcolladotor.github.io/"><img alt = 'some website' width='200' src='http://lcolladotor.github.io/post/2018-02-17-r-markdown-blog-template_files/LIBD.jpg' /></a>
</center>


### Reproducibility


```r
## Reproducibility info
library('devtools')
```

```
## Loading required package: usethis
```

```r
options(width = 120)
session_info()
```

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
##  highr           0.10       2022-12-22 [1] CRAN (R 4.3.0)
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

### References

Citations made with `knitcitations` <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>) and blog built using `blogdown` (<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>).



```r
## Chunk normaly with options:  results = 'asis', echo = FALSE, cache = FALSE
## Print bibliography
bibliography(style = 'html')
```

<p><a id='bib-Boettiger_2021'></a><a href="#cite-Boettiger_2021">[1]</a><cite>
C. Boettiger.
<em>knitcitations: Citations for 'Knitr' Markdown Files</em>.
R package version 1.0.12.
2021.
URL: <a href="https://CRAN.R-project.org/package=knitcitations">https://CRAN.R-project.org/package=knitcitations</a>.</cite></p>

<p><a id='bib-Xie_2017'></a><a href="#cite-Xie_2017">[2]</a><cite>
Y. Xie, A. P. Hill, and A. Thomas.
<em>blogdown: Creating Websites with R Markdown</em>.
Boca Raton, Florida: Chapman and Hall/CRC, 2017.
ISBN: 978-0815363729.
URL: <a href="https://bookdown.org/yihui/blogdown/">https://bookdown.org/yihui/blogdown/</a>.</cite></p>

