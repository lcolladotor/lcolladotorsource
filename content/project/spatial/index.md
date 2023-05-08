+++
# Project title.
title = "spatial"

# Date this page was created.
date = 2020-02-29T00:00:00

# Project summary to display on homepage.
summary = "Human brain spatial transcriptomics work using Visium from 10x Genomics"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["spatial"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
links = [{icon_pack = "fab", icon="twitter", name="#Visium_SPG_AD", url = "https://twitter.com/search?q=%23Visium_SPG_AD&src=typed_query"}, {icon_pack = "fab", icon="twitter", name="#spatialDLPFC", url = "https://twitter.com/search?q=%23spatialDLPFC&src=typed_query"}, {icon_pack = "fab", icon="twitter", name="#spatialLIBD", url = "https://twitter.com/search?q=%23spatialLIBD&src=typed_query"}, {name = "spatialLIBD shiny app", url = "http://spatial.libd.org/spatialLIBD"}, {icon_pack = "fab", icon = "r-project", name = "Bioconductor", url = "https://bioconductor.org/packages/spatialLIBD"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**bioRxiv**](https://www.biorxiv.org/content/10.1101/2020.02.28.969931v1)"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

In February 2020 we published the [first pre-print](https://www.biorxiv.org/content/10.1101/2020.02.28.969931v1) using the 10x Genomics Visium platform for spatial transcriptomics. For this project we created the [`spatialLIBD`](https://bioconductor.org/packages/spatialLIBD) Bioconductor package and started developing new analytical methods for this type of data. Given that we shared all the data and code when we posted the pre-print, by the time [the peer-reviewed publication](https://doi.org/10.1038/s41593-020-00787-0) was made public in February 2021, others had already used our dataset to develop and showcase their methods. For example, [`BayesSpace`](http://bioconductor.org/packages/BayesSpace)'s [pre-print](https://doi.org/10.1101/2020.09.04.283812) was posted on September 2020, prior to their own June 2021 [peer-reviewed publication](https://doi.org/10.1038/s41587-021-00935-2). We are now using `BayesSpace` in our projects. This is an example of how open science and open access accelerate science.

{{< tweet user="lcolladotor" id="1233661576433061888" >}}

{{< tweet user="PardoBree" id="1388253938391175173" >}}

{{< tweet user="lahuuki" id="1626686409313763328" >}}

{{< tweet user="sanghokwon17" id="1650589385379962881" >}}
