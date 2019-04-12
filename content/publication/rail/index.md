+++
title = "Rail-RNA: Scalable analysis of RNA-seq splicing and coverage"
date = "2016-09-03T17:27:55-05:00"

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["A Nellore", "[__L Collado-Torres__](/authors/admin)", "AE Jaffe"," J Alquicira-Hernández", "C Wilks", "J Pritt", "J Morton", "JT Leek", "B Langmead"]

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
publication = "Bioinformatics"
publication_short = ""

# Abstract.
abstract = "Motivation: RNA sequencing (RNA-seq) experiments now span hundreds to thousands of samples. Current spliced alignment software is designed to analyze each sample separately. Consequently, no information is gained from analyzing multiple samples together, and it requires extra work to obtain analysis products that incorporate data from across samples. Results: We describe Rail-RNA, a cloud-enabled spliced aligner that analyzes many samples at once. Rail-RNA eliminates redundant work across samples, making it more efficient as samples are added. For many samples, Rail-RNA is more accurate than annotation-assisted aligners. We use Rail-RNA to align 667 RNA-seq samples from the GEUVADIS project on Amazon Web Services in under 16 hours for US$0.91 per sample. Rail-RNA outputs alignments in SAM/BAM format; but it also outputs (1) base-level coverage bigWigs for each sample; (2) coverage bigWigs encoding normalized mean and median coverages at each base across samples analyzed; and (3) exon-exon splice junctions and indels (features) in columnar formats that juxtapose coverages in samples in which a given feature is found. Supplementary outputs are ready for use with downstream packages for reproducible statistical analysis.We use Rail-RNA to identify expressed regions in the GEUVADIS samples and show that both annotated and unannotated (novel) expressed regions exhibit consistent patterns of variation across populations and with respect to known confounding variables. Availability: Rail-RNA is open-source software available at http://rail.bio."

# Summary. An optional shortened abstract.
summary = "We describe Rail-RNA, a cloud-enabled spliced aligner that analyzes many samples at once. Rail-RNA eliminates redundant work across samples, making it more efficient as samples are added. For many samples, Rail-RNA is more accurate than annotation-assisted aligners."

# Digital Object Identifier (DOI)
doi = "10.1093/bioinformatics/btw575"

# Is this a featured publication? (true/false)
featured = false

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Rail-RNA", "derfinder"]

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["derfinder", "recount2"]

# Links (optional).
url_pdf = "http://bioinformatics.oxfordjournals.org/content/early/2016/09/02/bioinformatics.btw575.full.pdf+html"
url_preprint = "https://www.biorxiv.org/content/10.1101/019067v2"
url_code = ""
url_dataset = ""
url_project = "http://rail.bio"
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# links = [{name = "Custom Link", url = "http://example.org"}]

# Does this page contain LaTeX math? (true/false)
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**Bioinformatics**](https://doi.org/10.1093/bioinformatics/btw575)"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""
+++

<!-- More detail can easily be written here using *Markdown* and $\rm \LaTeX$ math code. -->
