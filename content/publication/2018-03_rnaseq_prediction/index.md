+++
title = "Improving the value of public RNA-seq expression data by phenotype prediction"
date = "2018-03-05T16:45:43-05:00"

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["Shannon SE", "admin", "Jaffe AE", "Leek JT"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference paper
# 2 = Journal article
# 3 = Preprint / Working Paper
# 4 = Report
# 5 = Book
# 6 = Book section
# 7 = Thesis
# 8 = Patent
publication_types = ["2"]

# Publication name and optional abbreviated version.
publication = "Nucleic Acids Research"
publication_short = ""

# Abstract.
abstract = "Background: Publicly available genomic data are a valuable resource for studying normal human variation and disease, but these data are often not well labeled or annotated. The lack of phenotype information for public genomic data severely limits their utility for addressing targeted biological questions. Results: We develop an in silico phenotyping approach for predicting critical missing annotation directly from genomic measurements using, well-annotated genomic and phenotypic data produced by consortia like TCGA and GTEx as training data. We apply in silico phenotyping to a set of 70,000 RNA-seq samples we recently processed on a common pipeline as part of the recount2 project (https://jhubiostatistics.shinyapps.io/recount/). We use gene expression data to build and evaluate predictors for both biological phenotypes (sex, tissue, sample source) and experimental conditions (sequencing strategy). We demonstrate how these predictions can be used to study cross-sample properties of public genomic data, select genomic projects with specific characteristics, and perform downstream analyses using predicted phenotypes. The methods to perform phenotype prediction are available in the phenopredict R package (https://github.com/leekgroup/phenopredict) and the predictions for recount2 are available from the recount R package (https://bioconductor.org/packages/release/bioc/html/recount.html). Conclusion: Having leveraging massive public data sets to generate a well-phenotyped set of expression data for more than 70,000 human samples, expression data is available for use on a scale that was not previously feasible."

# Summary. An optional shortened abstract.
summary = ""

# Digital Object Identifier (DOI)
doi = "10.1093/nar/gky102"

# Is this a featured publication? (true/false)
featured = false

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["recount2"]

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["recount2"]

# Links (optional).
url_pdf = "https://academic.oup.com/nar/advance-article/doi/10.1093/nar/gky102/4920847"
url_preprint = "https://www.biorxiv.org/content/10.1101/145656v1"
url_code = "https://github.com/ShanEllis/phenopredict_usecase"
url_dataset = ""
url_project = "https://github.com/ShanEllis/phenopredict_phenotypes"
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# links = [{name = "Custom Link", url = "http://example.org"}]

# Does this page contain LaTeX math? (true/false)
math = true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**NAR**](https://doi.org/10.1093/nar/gky102)"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

<!-- More detail can easily be written here using *Markdown* and $\rm \LaTeX$ math code. -->

{{% tweet user="jtleek" id="970710268199297024" %}}
{{% tweet user="lcolladotor" id="970899283707924480" %}}
