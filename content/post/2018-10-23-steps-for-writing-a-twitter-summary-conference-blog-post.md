---
title: Steps for writing a Twitter summary conference blog post
author: L. Collado-Torres
date: '2018-10-23'
slug: steps-for-writing-a-twitter-summary-conference-blog-post
categories:
  - Conference
  - rstats
tags:
  - ASHG
  - Blog
  - rstats
header:
  caption: ''
  image: ''
  preview: yes
---

I recently wrote several blog posts with many tweets[^1] as a way of taking notes during the [American Society of Human Genetics 2018 conference](http://www.ashg.org/2018meeting/). A few friends asked me how I did this *so fast*. The process can be summarized into the following main steps.

1.  Save links of tweets you want to highlight in your post.
2.  Use a [`hugo`](https://gohugo.io/)-powered blog to obtain the code for embedding tweets easily[^2].
3.  Proofread, edit and post.

### My steps detailed

Here’s the actual process I used.

1.  Identify the conference Twitter hashtag. In my recent case, that was [ASHG18](https://twitter.com/search?q=%23ASHG18).

2.  Create a Google doc or some other simple text file you can access easily from your phone and laptop.

3.  While in a presentation, check the *latest* tweets for the given hashtag. [ASGH18 example](https://twitter.com/search?f=tweets&vertical=default&q=%23ASHG18).

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2010.53.44%20PM.png" width="400" />

4.  Copy the link of any tweet you find interesting. If there are none for the session you are in, consider writing some tweets yourself with the conference hashtag!

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.12.23%20PM.png" width="500" />

5.  Paste the link into your Google doc.

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.10.53%20PM.png" width="500" />

6.  Once the day is over, copy-paste the contents of your Google doc into a text editor that has the ability to find and replace using regular expressions. For example, [TextMate](https://macromates.com/).

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.15.18%20PM.png" width="500" />

7.  Find and replace to create the syntax for embedding tweets. I’ll cover more of this in detail in the next section.

Find:

``` r
https://twitter.com/.*/status/
```

and replace by:

``` r
\n`r blogdown::shortcode("tweet", "
```

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.17.03%20PM.png" width="500" />

Then find:

``` r
\?s=[0-9]*
```

and replace by:

``` r
")`\n
```

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.17.58%20PM.png" width="500" />

Our file now looks like this:

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.18.07%20PM.png" width="500" />

8.  Add any comments you wish, format the headings and proofread.

9.  Make it public and tweet about your post with the conference hashtag!

And you are done! 🙌🏽🎉

### Quick embedding

Note that my blog is powered by *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>) which has the function `blogdown::shortcode()` for embedding tweets. For example, `blogdown::shortcode("tweet", user="lcolladotor", id="1054380320533950464")` generates the `hugo` syntax code which then `hugo` renders into the tweet itself.

{{% tweet user="lcolladotor" id="1054380320533950464" %}}

As an alternative, we can use Twitter itself by copy-pasting the code for embedding the tweet directly from the Twitter app/website. On the top right side menu on the tweet itself, select *Embed Tweet*

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.04.03%20PM.png" width="500" />

then copy-paste the HTML code into your post.

<img src="http://lcolladotor.github.io/post/2018-10-23-steps-for-writing-a-twitter-summary-conference-blog-post_files/Screen%20Shot%202018-10-23%20at%2011.04.28%20PM.png" width="500" />

Here’s the code:

    <blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I just completed my <a href="https://twitter.com/hashtag/ASHG18?src=hash&amp;ref_src=twsrc%5Etfw">#ASHG18</a> survey <a href="https://twitter.com/GeneticsSociety?ref_src=twsrc%5Etfw">@GeneticsSociety</a>. Took a few minutes and most of my feedback wouldn&#39;t stand out. Except that I did use a box to suggest having a webinar with role playing scenarios that exemplify how the code of conduct can be used to diffuse harassment <a href="https://twitter.com/jsdron?ref_src=twsrc%5Etfw">@jsdron</a> <a href="https://t.co/AKZdnGCr25">pic.twitter.com/AKZdnGCr25</a></p>&mdash; 🇲🇽 Dr. Leonardo Collado-Torres (@fellgernon) <a href="https://twitter.com/lcolladotor/status/1054380320533950464?ref_src=twsrc%5Etfw">October 22, 2018</a></blockquote>
    <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

and here is how it looks:

<blockquote class="twitter-tweet" data-lang="en">
<p lang="en" dir="ltr">
I just completed my <a href="https://twitter.com/hashtag/ASHG18?src=hash&amp;ref_src=twsrc%5Etfw">\#ASHG18</a> survey <a href="https://twitter.com/GeneticsSociety?ref_src=twsrc%5Etfw">(**GeneticsSociety?**)</a>. Took a few minutes and most of my feedback wouldn't stand out. Except that I did use a box to suggest having a webinar with role playing scenarios that exemplify how the code of conduct can be used to diffuse harassment <a href="https://twitter.com/jsdron?ref_src=twsrc%5Etfw">(**jsdron?**)</a> <a href="https://t.co/AKZdnGCr25">pic.twitter.com/AKZdnGCr25</a>
</p>
— 🇲🇽 Dr. Leonardo Collado-Torres ((**fellgernon?**)) <a href="https://twitter.com/lcolladotor/status/1054380320533950464?ref_src=twsrc%5Etfw">October 22, 2018</a>
</blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

There might be other ways of doing this that are specific to your blog platform.

I also imagine that it should be possible to *bookmark* the tweets on Twitter and then use an R package to extract your bookmarked tweets from the past 24 hours in order to simplify the process. Maybe this can be done with *[rtweet](https://CRAN.R-project.org/package=rtweet)* although I haven’t dived into it.

### New to `blogdown`?

Check:

- [Emily Zabor’s website tutorial](http://www.emilyzabor.com/tutorials/rmarkdown_websites_tutorial.html#blogs)
- The *[blogdown](https://CRAN.R-project.org/package=blogdown)* (<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>) [book](https://bookdown.org/yihui/blogdown/).
- [Alison Presmanes Hill’s blogdown introduction](https://alison.rbind.io/post/up-and-running-with-blogdown/).

Also, ask around. You might belong to a group or know someone that is willing to host a guest post in their `blogdown` blog. For example:

- [LIBD rstats club](http://research.libd.org/rstatsclub/#.W8_pgBNKg0o)
- [R-Ladies Baltimore](https://rladies-baltimore.github.io/)
- [R-Ladies NYC](http://www.rladiesnyc.org/)

### Acknowledgments

This blog post was made possible thanks to:

- *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
- *[blogdown](https://CRAN.R-project.org/package=blogdown)* (<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
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

[^1]: [ASHG18 day 1 post](http://lcolladotor.github.io/2018/10/16/ashg18-tweet-summary-day-1/#.W8gWEBNKg0o), [day 2](http://lcolladotor.github.io/2018/10/17/ashg18-tweet-summary-day-2/#.W8ggNxNKg0o), [day 3](http://lcolladotor.github.io/2018/10/18/ashg18-tweet-summary-day-3/#.W8mYLxNKg0o), [day 4](http://lcolladotor.github.io/2018/10/19/ashg18-tweet-summary-day-4/#.W8qdTRNKg0o) and [day 5](http://lcolladotor.github.io/2018/10/20/ashg18-tweet-summary-day-5/#.W8t2vhNKg0o).

[^2]: Or any other tool that can get you the embedding code, including the Twitter page itself.
