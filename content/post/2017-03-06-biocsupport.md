---
title: How to ask for help for Bioconductor packages
author: L. Collado-Torres
date: '2017-03-06'
categories:
  - rstats
tags:
  - Help
slug: 'How-to-ask-for-help-for-Bioconductor-packages'
---


{{% alert note %}}
tl;dr Please post your question at the Bioconductor support website https://support.bioconductor.org/ and check the posting guide http://www.bioconductor.org/help/support/posting-guide/. It's important that you provide reproducible code and information about your R session.
{{% /alert %}}

Recently I have been getting more questions about several packages I maintain. It's great to see more interest from users, but at the same time most questions lack the information I need to help the users. I have also gotten most of the questions via email, which is why I am writing this post. As of today, I will no longer answer questions related to my Bioconductor packages via personal emails. This might sound harsh, but hopefully the rest of this post will convince you that it's the best thing to do. You might also be interested in the basics of using [derfinder](http://bioconductor.org/packages/release/bioc/vignettes/derfinder/inst/doc/derfinder-quickstart.html#basics), [regionReport](http://bioconductor.org/packages/release/bioc/vignettes/regionReport/inst/doc/regionReport.html#basics) or [recount](http://bioconductor.org/packages/release/bioc/vignettes/recount/inst/doc/recount-quickstart.html#basics), among others.

The Bioconductor project is a community project and it benefits from users interacting in public venues. When a user asks a question at the [Bioconductor support website](https://support.bioconductor.org/), they are providing information that future users might be interested in. That is, the user (__U1__) is contributing information to the overall documentation around the Bioconductor package they are asking a question about. Ideally, a new user (__U2__) can then read through the question U1 wrote, check the solution, and move on. This is one of the main reasons why we (developers) want questions to be well documented. There are a couple of quick things that U1 can check that will make their question much more useful to the community.

<center>
<a href="http://www.bioconductor.org/help/support/posting-guide/"><img alt = 'shinycsv landing' width='600' src='http://lcolladotor.github.io/figs/2017-03-06-bioc-support/question.png' /></a>
</center>

## Session information

One of the strengths of Bioconductor is that all the packages have vignettes and lots of documentation. The packages are also checked regularly and must pass some tests. That also means that packages can change frequently, at least more frequently than CRAN packages. There's also the added complexity that at any given point in time there is a release branch and a development branch. This means that there are many variables and saying that you are using the "latest version" doesn't mean much to the developer. All of this information and more is part of the _R session information_. That is why I and others request users to post their session information. It's very easy to get, simply run the following code:


    ## Install devtools if needed
    # install.packages('devtools')
    
    ## Reproducibility info
    library('devtools')
    options(width = 120)
    session_info()

The output might be too long to post in the [Bioconductor support website](https://support.bioconductor.org/). The easy solution is to save the information you want displayed in a [gist](https://gist.github.com/). Then simply add the gist link in your question. Note that you need to have the link under "text" formatting and not "code".

## Code to reproduce the error

If U1 includes the session information, their question will be pretty good, but not ideal yet. Many of the questions I've been asked do not include code for me to figure out the exact steps of what they were doing. A lot of times I can infer pieces of what they were doing from their description of the problem. But doing so takes quite a bit of my time and effort, and is still not perfect. Now imagine that U2 is reading through the question: they would probably get lost!

There is a wide range of things that U1 could have done. To help the developer, the best thing is for the user to include the code that lead to the error. The code should include how the data was loaded, so that the developer can run it themselves and check in more detail what went wrong. This means providing a small subset of the data or using some publicly available data.

I realize that writing code that reproduces the error is not easy. But it helps a lot for learning more about R and Bioconductor. I can tell you that I went through the same process, and in my experience you can find out what you are doing wrong by writing the reproducible code.


## Extra

Here are some other tips that are useful.

* If you run `traceback()` immediately after getting the error and include the output in your question, that would be great. It makes it easier to check at what point the code failed and produced the error. 
* Recently when I ask questions myself, I include the "non-evaluated code" (clean code in your script) and "evaluated code" (think of the R console: a mix of code and output). The non-evaluated code makes it easier for others to copy-paste the code into their R session without having to deal with any formatting issues ([example](https://github.com/leekgroup/recount/issues/8#issue-210124094)).
* If you encounter a new error, post a new question instead of "replying" to the first one.
* Introduce yourself.
* Be polite.


By now you should be ready to post some great questions! Thanks for contributing to the Bioconductor community.


### Want more?

Check other [@jhubiostat](https://twitter.com/jhubiostat) student and alumni blogs at [Bmore Biostats](http://bmorebiostat.com/) as well as topics on [#rstats](https://twitter.com/search?q=%23rstats).
