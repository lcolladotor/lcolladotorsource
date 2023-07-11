---
title: blogdown Insert Image addin
author: L. Collado-Torres
date: '2018-03-07'
slug: blogdown-insert-image-addin
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




Have you ever tried inserting an image into a *[blogdown](https://CRAN.R-project.org/package=blogdown)* post? Maybe you have, or maybe you tried and gave up. Lets first review the _hard_ way before getting to the solution I contributed.

### The _hard_ way

The process involves copying the target image to the static directory that corresponds to the *[blogdown](https://CRAN.R-project.org/package=blogdown)* post. Lets say that your post is called `2018-03-07-my-new-post.Rmd` and lives at `content/post/`, so it's full path is `content/post/2018-03-07-my-new-post.Rmd`. When you run the RStudio *[blogdown](https://CRAN.R-project.org/package=blogdown)* addin _Serve Site_, behind curtains the directory `static/post/2018-03-07-my-new-post_files` is created and inside it you can find the images made by your R code: likely at `static/post/2018-03-07-my-new-post_files/figure_html`.

So far everything is working! But now you want to add a screenshot or some other image to your blog post. Lets say that your image is `~/Desktop/screenshot.jpg`. Your `~/Desktop` directory is not part of your *[blogdown](https://CRAN.R-project.org/package=blogdown)* directory and well, simply put, your website won't find the image. We need to put it in a location that will be made public by `hugo`. That is, we need to put it inside `static/post/2018-03-07-my-new-post_files` (or anywhere inside `static`, but we like to keep things tidy!). 

Ok, so we copy our screenshot file `~/Desktop/screenshot.jpg` and save it as `static/post/2018-03-07-my-new-post_files/screenshot.jpg`. The next time we render our site and publish it, the figure will be available in the web. But it's still not part of our *[blogdown](https://CRAN.R-project.org/package=blogdown)* post.

So we need to use either the Markdown or HTML syntax for adding the image. Maybe your initial thought is to use:

```
![](screenshot.jpg)
```

Except that __will not__ work. We need to use almost all the path (just remove `static`) as shown below:

```
![](/post/2018-03-07-my-new-post_files/screenshot.jpg)
```

If you want to edit the height or width, then you need to use the HTML syntax. Something like:

```
<img alt = 'my new screenshot' width='200' src='/post/2018-03-07-my-new-post_files/screenshot.jpg' />
```


#### _hard way_ notes

You could have also used `knitr::include_graphics()` and let *[blogdown](https://CRAN.R-project.org/package=blogdown)* copy it to the final location in `static` and link to it appropriately. However, you would have to keep your original images organized in a way that won't bother `hugo`. 

Another option that I used for a while, even in the days when my blog was based on Jekyll, is to render the figures yourself and copy the directory with the figures, plus mess around with how they are linked from R. Details [here](https://github.com/lcolladotor/markdown-redcarpet.tmbundle/commit/f043c056ff620299843e9d8ea34144f478aa7965). Not something I recommend doing now.

### _Insert Image_ addin: aka, the _easy_ way

If you are using *[blogdown](https://CRAN.R-project.org/package=blogdown)*, you most likely (you _should_ if you can) are using [RStudio](https://www.rstudio.com/products/rstudio/download/) and the great *[blogdown](https://CRAN.R-project.org/package=blogdown)* addins: _New Post_ and _Serve Site_. I just recently started using them in the past few days and looking at the code I realized that it should be possible to make an addin that lets you:

1. select a target image,
1. copies the target image to the appropriate location under `static`,
1. gives you the correct code for linking the image.

Yihui Xie [loved the idea](https://github.com/rstudio/blogdown/issues/269) (I think it's fair to say that ^^) and helped me polish it in the [pull request](https://github.com/rstudio/blogdown/pull/272) that implements it. He then refined the code even [more](https://github.com/rstudio/blogdown/commit/7355a94edc62dd9ffe3792c1103f1536b9c67406)!

### Features of the _Insert Image_ addin

The final features, at least as implemented in *[blogdown](https://CRAN.R-project.org/package=blogdown)* version 0.5.7 are:

* Select an image from anywhere in your computer.
* Automatically generate a candidate final location for your image under `static`, which you can edit. Useful if you want to rename the final figure.
* Allow specifying the alternate description of the image (`alt`), height and width.
* If the target image file exists, a dynamic menu shows up that asks you whether to overwrite it or not.
* The final syntax is Markdown unless a width or height are used, in which case it uses HTML code.

Yihui Xie [hinted](https://github.com/rstudio/blogdown/pull/272) at other possible future features, which maybe you can help implement.

### Using the _Insert Image_ addin


#### Step 1: install appropriate *[blogdown](https://github.com/rstudio/blogdown)* version

First of all, at the time of writing this post, you need the development version of *[blogdown](https://github.com/rstudio/blogdown)*. You can install it with:


```r
## Check if you have version 0.5.7 or newer
## I actually used version 0.5.9 for this blog post
packageVersion('blogdown')

## If not, then get it!
##### If necessary:
## install.packages('devtools')
devtools::install_github('rstudio/blogdown')
```

You also need an up to date version of [RStudio](https://www.rstudio.com/products/rstudio/download/) and I recommend also using [R 3.4.x](https://cran.r-project.org/) (or newer if you are reading this in the future). Re-start RStudio so it loads the new version of *[blogdown](https://github.com/rstudio/blogdown)*.

#### Step 2: open the _Insert Image_ addin

Second, go to the _Addins_ menu in the top section of the RStudio window and select the _Insert Image_ *[blogdown](https://github.com/rstudio/blogdown)* addin.

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-07 at 11.47.37 PM.png" alt="insert image addin screenshot" width="400"/>

#### Step 3: choose figure and inputs

So far the _Insert Image_ addin looks like this:

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-07 at 11.58.44 PM.png" alt="addin without input" width="400"/>

So lets go head and select an image we want to upload. In my case, I chose an image that already exists.

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-08 at 12.00.01 AM.png" alt="" width="400"/>

You can rename the figure if you want, and if it doesn't exist, the _overwrite_ option goes away.

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-08 at 12.01.06 AM.png" alt="modified image file" width="400"/>

#### Step 4: hit done!

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-08 at 12.02.28 AM.png" alt="hit go" width="400"/>

Lets go ahead and click `done`! Our text window in RStudio will insert the appropriate code for linking the image. In this case, it's the following code:

```
<img src="/post/2018-03-07-blogdown-insert-image-addin_files/screenshot.png" alt="final image" width="400"/>
```

and this is the image:

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/screenshot.png" alt="final image" width="400"/>

#### Optional step 5

Now use the _Serve Site_ addin and check if you like your images. You might want to change the height/widths or alternate text. You could also wrap the HTML/Markdown code around it for linking to a website.

You can also delete your original images, if for example, they are cluttering your `~/Desktop`.

### Conclusions

I hope that you will find this new addin as useful as I'm finding it, or even more. Plus hopefully this blog post gives you an idea of the difficulties before this addin existed. Also, I want to thank Yihui Xie for guiding me, I've learnt quite a bit recently. Though I will still use `<-` assignment operator for my own code hehe.

### Acknowledgments


This blog post was made possible thanks to:

* *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
* *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
* *[devtools](https://CRAN.R-project.org/package=devtools)* <a id='cite-Wickham_2022'></a>(<a href='https://CRAN.R-project.org/package=devtools'>Wickham, Hester, Chang, and Bryan, 2022</a>)
* *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>)

as well as Yihui Xie's help and encouragement in the [form of a signed sticker](https://yihui.name/en/2018/02/bite-sized-pull-requests/) and the _Great Hacker_ title ^^. He also wrote [a blog post](https://yihui.name/en/2018/03/second-pull-request/) about the _Insert Image_ addin.

<img src="http://lcolladotor.github.io/post/2018-03-07-blogdown-insert-image-addin_files/Screen Shot 2018-03-08 at 12.12.07 AM.png" alt="great hacker signed sticker" width="400"/>



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
