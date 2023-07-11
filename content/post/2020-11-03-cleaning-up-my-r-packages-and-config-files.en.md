---
title: Cleaning up my R packages and config files
author: L. Collado-Torres
date: '2020-11-03'
slug: cleaning-up-my-r-packages-and-config-files
categories:
  - rstats
tags:
  - Bioconductor
subtitle: ''
summary: ''
authors: []
lastmod: '2020-11-03T20:57:43-05:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

Today was an unusual day at work given the US Elections. This meant that I had fewer meetings than what I’ve had lately. Earlier in the day I noticed an email announcing that the Bioconductor 3.13 docker image had been released for the next 6 month development cycle, which was a reminder of the recent [Bioconductor 3.12 release](http://bioconductor.org/news/bioc_3_12_release/). This prompted me to start updating my R packages.

In the past, I’ve updated all my currently installed R packages using the framework I described in a [2017 blog post](http://lcolladotor.github.io/2017/05/04/updating-r/#.X6ICiIhKguU). I remember seeing a tweet by [Hadley Wickham](https://twitter.com/hadleywickham) not so long ago [^1] that for him, a new R version was an opportunity to start with a clean slate. I like having everything I need ready to use, but well, my list of installed R packages was getting pretty long. Given that 4 year windows of time are in our minds, it felt like a good opportunity to clean my house. Or well, my R packages.

Thus, I started writing down which are the packages I want to have installed. At this point for me, that includes several R/Bioconductor packages I’ve made and their dependencies in case I need to work on them to resolve bugs or add new features. My R packages already use many of my favorite R packages, so I took advantage of this in order to avoid having to list every single R package I like using. In order to achieve this, I used the `dependencies = TRUE` argument that you can use with *[remotes](https://CRAN.R-project.org/package=remotes)* and *[BiocManager](https://CRAN.R-project.org/package=BiocManager)*.

``` r
## Install from scratch
if (!requireNamespace("remotes", quietly = TRUE))
    install.packages("remotes")
remotes::install_cran("BiocManager")
BiocManager::version()

## Rprofile packages
remotes::install_github(c(
    "jalvesaq/colorout"
))
remotes::install_cran(c(
    "devtools",
    "usethis"
))

## Main packages
BiocManager::install(c(
    "biocthis",
    "brainflowprobes",
    "derfinder",
    "derfinderPlot",
    "GenomicState",
    "megadepth",
    "recount",
    "recountWorkflow",
    "recount3",
    "regutools",
    "regionReport",
    "spatialLIBD"
), dependencies = TRUE, update = FALSE)
```

Once I had my main packages, I started adding some from LIBD, some from CRAN, and other ones from Bioconductor. You can see the full list at my team’s website under [Config files: R setup; R packages](https://lcolladotor.github.io/bioc_team_ds/config-files.html#r-packages).

I was curious about how these changes affected my list of installed R packages and used my older [2017 blog post](http://lcolladotor.github.io/2017/05/04/updating-r/#.X6ICiIhKguU) code to check this. That resulted in [this list](https://gist.github.com/lcolladotor/d0af9b22e3806af196233655dce54fde) which shows 423 installed R packages and 589 that I used to have installed. I suspect that several of them will come back. For example, I needed to install *[blogdown](https://CRAN.R-project.org/package=blogdown)* to work on this blog post. Some of the 423 packages are new, like *[rsthemes](https://github.com/gadenbuie/rsthemes)* which we recently learned about at the LIBD rstats club.

{{% tweet user="LIBDrstats" id="1312187753371561984" %}}

### Config files

Since I was doing all this work on both my macOS and Windows laptops for my R setup, I also went ahead and cleaned up a bit my configuration files. I have several of them with settings that I recommend others to use. That’s why I wrote a little “chapter” about them on my [team’s website](https://lcolladotor.github.io/bioc_team_ds/config-files.html#config-files). The list includes:

- Software I use (including R and RStudio)
- R packages
- R configuration files such as `~/.Rprofile` and `~/.Renviron`
- Git configuration files `~/.gitconfig` and `~/.gitignore_global`
- JHPCE (linux) configuration files such as `~/.bashrc`, `~/.inputrc`, `~/.bash_profile` and `~/.sge_request`

### Wrapping up

I’m hoping that all this information will be useful to both current and new team members, but it could be useful also to you. Though you might need to adapt some things. Earlier on in my career I learned from how others use configuration files to speed up their work or make their work experience more enjoyable. I’m still learning, but now I have a decent bag of tricks to share too.

Have fun!

<img src="http://lcolladotor.github.io/post/2020-11-03-cleaning-up-my-r-packages-and-config-files/Bag-of-Tricks-1.jpg" width="400" />

[Image source](https://criticalhitgamingsupplies.com/product/bag-of-tricks/)

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

[^1]: I couldn’t find the tweet right now.
