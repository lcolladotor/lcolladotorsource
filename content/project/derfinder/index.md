+++
# Project title.
title = "derfinder"

# Date this page was created.
date = 2013-04-19T00:00:00

# Project summary to display on homepage.
summary = "Annotation-agnostic methods for gene expression data"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["derfinder", "bulk"]

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
links = [{icon_pack = "fab", icon="twitter", name="#derfinder", url = "https://twitter.com/search?q=%23derfinder&src=typed_query"}, {icon_pack = "fab", icon = "r-project", name = "Bioconductor", url = "https://bioconductor.org/packages/derfinder"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**NAR**](https://doi.org/10.1093/nar/gkw852)"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

The goal of my Ph.D. with [Jeff Leek](http://jtleek.com/) and [Andrew Jaffe](http://aejaffe.com/) at JHBSPH was to develop statistical methods and software that enable researchers to differentiate the sources of variation observed in RNA-seq while minimizing the dependance on known annotation. This allows researchers to correct for technological variation and study the biological variation driving their phenotype of interest. This work lead to the development of the `derfinder` and `regionReport` Bioconductor packages. We then applied these methods to further our understanding of neuropsychiatric disorders using the Lieber Institute for Brain Development human brains collection.

