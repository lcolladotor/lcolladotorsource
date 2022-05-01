+++
title = "Flexible expressed region analysis for RNA-seq with derfinder"
date = "2016-09-26T00:00:00"

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["[__L Collado-Torres__](/authors/admin)", "A Nellore", "AC Frazee", "C Wilks", "MI Love", "B Langmead", "RA Irizarry", "JT Leek", "AE Jaffe"]

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
publication_short = "NAR"

# Abstract.
abstract = "Differential expression analysis of RNA sequencing (RNA-seq) data typically relies on reconstructing transcripts or counting reads that overlap known gene structures. We previously introduced an intermediate statistical approach called differentially expressed region (DER) finder that seeks to identify contiguous regions of the genome showing differential expression signal at single base resolution without relying on existing annotation or potentially inaccurate transcript assembly. We present the derfinder software that improves our annotation-agnostic approach to RNA-seq analysis by: (i) implementing a computationally efficient bump-hunting approach to identify DERs that permits genome-scale analyses in a large number of samples, (ii) introducing a flexible statistical modeling framework, including multi-group and time-course analyses and (iii) introducing a new set of data visualizations for expressed region analysis. We apply this approach to public RNA-seq data from the Genotype-Tissue Expression (GTEx) project and BrainSpan project to show that derfinder permits the analysis of hundreds of samples at base resolution in R, identifies expression outside of known gene boundaries and can be used to visualize expressed regions at base-resolution. In simulations, our base resolution approaches enable discovery in the presence of incomplete annotation and is nearly as powerful as feature-level methods when the annotation is complete. derfinder analysis using expressed region-level and single base-level approaches provides a compromise between full transcript reconstruction and feature-level analysis. The package is available from Bioconductor at www.bioconductor.org/packages/derfinder."

# Summary. An optional shortened abstract.
summary = "derfinder analysis using expressed region-level and single base-level approaches provides a compromise between full transcript reconstruction and feature-level analysis. The package is available from Bioconductor."

# Digital Object Identifier (DOI)
doi = "10.1093/nar/gkw852"

# Is this a featured publication? (true/false)
featured = false

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["derfinder"]

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["derfinder"]

# Links (optional).
url_pdf = "http://nar.oxfordjournals.org/content/early/2016/09/29/nar.gkw852.full.pdf+html"
url_preprint = "http://biorxiv.org/content/early/2016/05/19/015370"
url_code = "https://github.com/leekgroup/derSupplement"
url_dataset = ""
url_project = "http://leekgroup.github.io/derSupplement/"
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
links = [{name = "Bioconductor", url = "http://bioconductor.org/packages/derfinder"}]

# Does this page contain LaTeX math? (true/false)
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**NAR**](http://nar.oxfordjournals.org/content/early/2016/09/29/nar.gkw852.full.pdf+html)"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

<!-- More detail can easily be written here using *Markdown* and $\rm \LaTeX$ math code. -->

{{% tweet user="jtleek" id="568489985428590593" %}}
