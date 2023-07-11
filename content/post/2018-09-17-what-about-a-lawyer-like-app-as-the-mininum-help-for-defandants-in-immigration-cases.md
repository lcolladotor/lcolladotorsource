---
title: What about a lawyer-like app as the minimum help for defendants in immigration
  cases?
author: L. Collado-Torres
date: '2018-09-17'
slug: what-about-a-lawyer-like-app-as-the-mininum-help-for-defandants-in-immigration-cases
categories:
  - Ideas
tags:
  - politics
  - Prediction
  - Diversity
header:
  caption: ''
  image: ''
  preview: yes
---

Today I attended the special panel discussion event at JHSPH called [“Separated: Children Separation at the Border A Health and Human Rights Perspective”](http://hopkinshumanitarianhealth.org/news-events/events/separated-child-separation-at-the-border-a-health-and-human-rights-perspect). It got my mind racing and here’s an idea. It’s likely (definitely) incomplete, but maybe it’ll get others to think on related ideas.

<img src="http://lcolladotor.github.io/post/2018-09-17-what-about-a-lawyer-like-app-as-the-mininum-help-for-defandants-in-immigration-cases_files/ChildSepBorder.jpg" width="500" />
[Image source](http://hopkinshumanitarianhealth.org/news-events/events/separated-child-separation-at-the-border-a-health-and-human-rights-perspect)

### Panel summary

The panel was composed by:

- [Colleen Kraft](https://twitter.com/ColleenKraft), President, American Academy of Pediatrics
- [Eric Schwartz](https://twitter.com/EricSchwartzRI), President, Refugee International
- George Escobar, Chief of Program and Services, [CASA de Maryland](https://wearecasa.org/who-we-are/)
- [Paul Spiegel](https://twitter.com/pbspiegel), Director, Center for Humanitarian Health

I missed the first 30 minutes or so but I still got to listen to most of it. The panel members presented many facts and here are some that will be relevant to the idea I have:

- Child separation is just one of the consequences of the current’s administration immigration policies implemented and enforced by the Department of Justice (ultimately headed by Jeff Sessions, the US Attorney General).
- The US is the only country (to the panel’s members knowledge) with a child separation policy.
- Due to empathy many individuals across political lines reacted against child separation.
- The US immigration system won’t really change much even if Democrats get elected. Obama did deport over 2 million individuals, though he prioritized *criminals*[^1].
- Arrested immigrants are not required by law to have representation (a lawyer) provided by the government[^2].
- Minors (say 3 year old children) with no lawyers are being highlighted in the media.
- Immigration cases where the defendants have lawyers drastically improve[^3] the odds for the defendants.
- Immigration judges are human.
- Immigration judges typically used to (or maybe still do) try to give time for a minor to get a lawyer.
- Immigration judges are *alledgely*[^4] being pressured to meet quotas in the range of 700 to 1,000 cases by year under the current administration. Thus judges sometimes have to close cases in a couple of hours.
- Immigration judges now basically have 2 options for closing a case: order deportation or (I’m missing the correct term) *free* the defendant.

At the end the panel members highlighted that *we* should take some type of action[^5] but that we should consider the consequences of our suggested policy changes. They also mentioned that we should take advantage of this moment (child separation got everyone’s attention) to raise the profile of the other problems with the current immigration policies.

### My way of taking action: here’s an idea

I’m by no means an immigration expert. My way of taking action is to share ideas, like [I’ve done in the past](http://lcolladotor.github.io/2017/01/25/An-alternative-to-the-Mexico-US-wall-where-the-US-would-gain-millions-of-dollars/#.W6BV4v5Kg0o), that might be incomplete, unrealistic or even super flawed, but that hopefully motivate others.

The bare bones version of my idea was: what if immigrants could have an *automatic* (programmed) lawyer and translator during their hearings? This would not be a replacement for actually having lawyers (say those provided by local governments or NGOs as George Escobar mentioned) but would raise the minimum bar for those immigrants who currently have their cases processed with no lawyers at all.

### Getting into the details

Imagine that we could get our hands on dozens/hundreds/thousands? of transcripts of immigration court hearings where we have the following information:

- what the judge said
- what the government’s lawyer said
- what the defendant’s lawyer said (either to the judge or to the defendant)
- what the defendant said

Just like a script for a play. We would additionally need a table with court hearing metadata such as:

- Outcome: deportation, being *freed* (term?).
- Date of the hearing.
- State where the hearing occurred.

Then using machine learning (maybe with deep learning methods) process the text and try to determine potential suggestions an actual defendant’s lawyer would give to its defendant or respond to the judge/government’s lawyer. It might not always get things right, but I imagine that it would be better than the current state of affairs.

The automatic lawyer would need then to work as say a phone app that listens to what others are saying in the room. Say have 3 icons with one per person present (judge, defendant, gov’s lawyer). Then the defendant presses each button when each person is talking. The app then shows some 1 to say 3 suggested responses (with translations)[^6] and responds for the defendant in English once the defendant chooses an option (or goes with the top one).

### Implementing an initial version of the app

I think that large computing companies like Amazon, Microsoft and Google would be willing to provide some compute credits on their clouds for the initial version of the algorithm that is *listening* to the court hearing and then provides suggestions. Think of this as the “suggested text” you get nowadays when typing emails on Gmail or text messages. Maybe these companies have programs where you can apply to have some of their engineers help you for a certain number of hours.

I think that one big initial challenge would be to get that collection of transcripts from immigration court hearings where defendant lawyer(s) were present.

I also imagine that automated lawyers are not allowed currently in courts. But compared to providing human lawyers in all immigration cases, this change might be more *realistic* to pass as a law.

I also imagine that some phone companies might be willing to provide some refurbished phones that only have this app installed and are kept safe in the immigration courts. And well, satisfy any security requirements the government has.

### Improving the app

Lets say that you get that alpha version of the app working. If we had volunteer lawyers annotate the transcripts with some information about the intent behind what each person said (it could start with just 3 options: negative, positive, neutral from the perspective of the defendant) that could maybe help the algorithm that processes the transcripts.

If we also had more detailed court hearing metadata such as:

- Location of the court (I imagine a that a few judges work in each court)
- Demographics of the defendants: like which country or even region of the country where they come from, whether the defendant has any family support, etc
- Category information for the court hearing (maybe cases can be grouped into a few categories)

then I imagine that the app would be able to have more personalized experience, like re-adjust the suggestions based on which court you are located at and adapt the translations to the Spanish version the defendant is most familiar with (we say *buddy* in so many different ways as shown below).

<img src="http://lcolladotor.github.io/post/2018-09-17-what-about-a-lawyer-like-app-as-the-mininum-help-for-defandants-in-immigration-cases_files/bromap.png" width="500" />

[Image source](https://www.facebook.com/pictoline/photos/a.1611821172410355.1073741828.1598399590419180/1623937737865365/?type=1&fref=nf)

The app could also be connected to remote human immigration lawyers than can intervene remotely when the suggestions algorithm doensn’t know what to do. Maybe this could be part of some social service that immigration lawyers (regardless of their personal political preferences) could do as some elective during their formation.

### Doing some convincing

I think that you could try to get support for this automatic immigration lawyer by arguing that:

- It’s better than no lawyer.
- It’s cheaper than having lawyers for all cases.
- Improves processing times on average (ideally) such that immigration judges can fulfill their quotas (here I’m hoping that it reduces the rate at which cases are closed with deportation orders).
- Is more humane than having a minor with no help. Though I hope that immigration judges would still try to give time for children to secure a lawyer.
- Might be implemented earlier (years earlier?) than changes in immigration law requiring that all defendants have a human lawyer in immigration cases.
- If human lawyers can help through the app, then it also increases the number of jobs for immigration lawyers.

This idea has potentially many flaws because like any system, people on both sides will try to game it. This is where having a large set of transcripts would be useful as well as continuous updates to the algorithm such that gaming the system actually becomes hard.

As you can see, this is just an idea, or a collection of them around one theme. It would need serious work to implement.

### Acknowledgments

Do you want to listen to the whole panel discussion? From this tweet it looks like the recording will be available online:

{{% tweet user="JohnsHopkinsSPH" id="1041732455865171972" %}}

This blog post was made possible thanks to:

- *[BiocStyle](https://bioconductor.org/packages/3.17/BiocStyle)* <a id='cite-Oles_2023'></a>(<a href='https://bioconductor.org/packages/BiocStyle'>Oleś, 2023</a>)
- *[blogdown](https://CRAN.R-project.org/package=blogdown)* <a id='cite-Xie_2017'></a>(<a href='https://bookdown.org/yihui/blogdown/'>Xie, Hill, and Thomas, 2017</a>)
- *[devtools](https://CRAN.R-project.org/package=devtools)* <a id='cite-Wickham_2022'></a>(<a href='https://CRAN.R-project.org/package=devtools'>Wickham, Hester, Chang, and Bryan, 2022</a>)
- *[knitcitations](https://CRAN.R-project.org/package=knitcitations)* <a id='cite-Boettiger_2021'></a>(<a href='https://CRAN.R-project.org/package=knitcitations'>Boettiger, 2021</a>)

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
<a id='bib-Wickham_2022'></a><a href="#cite-Wickham_2022">\[3\]</a><cite>
H. Wickham, J. Hester, W. Chang, and J. Bryan.
<em>devtools: Tools to Make Developing R Packages Easier</em>.
R package version 2.4.5.
2022.
URL: <a href="https://CRAN.R-project.org/package=devtools">https://CRAN.R-project.org/package=devtools</a>.</cite>
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

[^1]: George Escobar mentioned that they protested the fact that a DUI labeled someone as a criminal, but well, Trump has gone beyond DUIs arrested many individuals with no criminal history.

[^2]: George Escobar highlighted that one path of action is to convince local governments to fund/provide lawyers to these individuals.

[^3]: I don’t know by how much.

[^4]: Information has leaked about this but I guess that it’s not completely public info.

[^5]: Could be with your vote, helping members in your community that are affected, improving how we translate research into terms everyone understands, improving the education about the violent reality many are trying to escape by coming to the US, approaching local governments, etc.

[^6]: The app could show the text but also should *read* the translations since very young children will very likely not know how to read. I think that the app should never assume that the defendant knows how to read.
