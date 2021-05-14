+++
title = "Reproducible RNA-seq analysis with recount2"

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date = 2017-06-27T13:30:00
date_end = 2017-06-27T13:30:00
all_day = false

# Schedule page publish date (NOT talk date).
publishDate = ""

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["admin"]

# Location of event.
location = "Chicago, IL, US"

# Name of event and optional event URL.
event = "ICSA 2017"
event_url = "http://bioinfo.stats.northwestern.edu/~icsa/index.php"

# Abstract. What's your talk about?
abstract = "In the past decade high-throughput RNA sequencing (RNA-seq) has become the dominant method for studying gene expression. Commonly, researchers generate RNA-seq data to perform a differential expression analysis by either reconstructing transcripts or counting reads that overlap known gene structures. Previously we introduced an intermediate statistical approach called differential expressed region (DER) finder that identifies contiguous regions of the genome showing differential expression signal at single base resolution in an annotation-agnostic manner (Collado-Torres et al, 2017, NAR). These three different approaches all require aligning the RNA-seq data against the reference genome. While over 2,000 projects are publicly available via the Sequence Read Archive (SRA) it is computationally intensive to re-analyze the RNA-seq data in a homogenous way. Using Rail-RNA (Nellore et al, 2016, Bioinformatics) we aligned over 70,000 human RNA-seq samples and created summaries at the gene, exon, exon-exon junction and base pair coverage levels which are available via the recount2 resource at https://jhubiostatistics.shinyapps.io/recount/ and the recount Bioconductor package (Collado-Torres, Nellore et al, 2017, Nature Biotechnology). The data from the recount2 resource can be used for different levels of RNA-seq differential expression analysis while bypassing the costly computational step of alignment. The data from recount2 can be used to predict phenotype information that is otherwise impractical to obtain for all SRA human projects. In recount2 we also provide data for the Genotype-Expression Tissue project (GTEx) and The Cancer Genome Atlas (TCGA) which have richer metadata and can be used for developing new methods and testing them before applying them to the SRA data. We expect that recount2 will be very useful for the genomics community and in particular for the statistical community by fostering the development of new methods, just like ReCount (Frazee et al, 2011, Bioinformatics) played a roll in the development of DESeq2, voom and metagenomeSeq among other methods."

# Summary. An optional shortened abstract.
summary = "recount2 overview for the ICSA 2017 conference"

# Is this a featured talk? (true/false)
featured = false

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["recount2", "derfinder"]

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Optional filename of your slides within your talk folder or a URL.
url_slides = "https://speakerdeck.com/lcolladotor/icsa-2017"

# Projects (optional).
#   Associate this talk with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["recount2", "derfinder"]

# Links (optional).
url_pdf = ""
url_video = ""
url_code = ""

# Demo talk page uses LaTeX math.
math = false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Right"
+++

<script async class="speakerdeck-embed" data-id="19261ec55356439bb1742241fe29aee9" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>


