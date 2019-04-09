+++
title = "RNA-seq samples beyond the known transcriptome with derfinder available via recount2"

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date = 2017-05-20T12:30:00
date_end = 2017-05-20T12:30:00
all_day = false

# Schedule page publish date (NOT talk date).
publishDate = ""

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["admin"]

# Location of event.
location = "San Diego, CA, US"

# Name of event and optional event URL.
event = "SOBP 2017"
event_url = "https://www.sobp.org/i4a/pages/index.cfm?pageid=3560"

# Abstract. What's your talk about?
abstract = "Background. Differential expression analysis of RNA sequencing (RNA-seq) data typically relies on reconstructing transcripts or counting reads that overlap known gene structures. We previously introduced an intermediate statistical approach called differentially expressed region (DER) finder that seeks to identify contiguous regions of the genome showing differential expression signal at single base resolution without relying on existing annotation or potentially inaccurate transcript assembly. The first step is to align the RNA-seq reads to the genome which is costly and requires a solid computing infrastructure. Methods. We implemented the DER finder approach in a R software package called derfinder which  provides a computationally efficient bump-hunting approach to identify DERs that permits genome-scale analyses in a large number of samples. Using the Rail-RNA aligner we aligned  over 70,000 human RNA-seq samples and summarized the results at the gene, exon, exon-exon junction and base pair-level coverage levels. Results. We used derfinder to identify over 50,000 regions of the genome that are differentially expressed throughout the lifespan of the human brain with strong signal in non-exonic sections of the genome. We also developed the recount R software package that provides access to over 70,000 RNA-seq samples grouped in 2,041 projects. Conclusions. The recount resource can be used for different levels of RNA-seq differential expression analysis without having the costly computational infrastructure for the alignment step. derfinder can be used with recount data or your own private data to perform annotation-agnostic RNA-seq analyses."

# Summary. An optional shortened abstract.
summary = "Showcasing how derfinder and recount2 can be used together to perform annotation-agnostic RNA-seq analyses at SOBP2017"

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
url_slides = "https://speakerdeck.com/lcolladotor/sobp-2017"

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

<!--

{{% alert note %}}
Click on the **Slides** button above to view the built-in slides feature.
{{% /alert %}}


Slides can be added in a few ways:

- **Create** slides using Academic's *Slides* feature and link using `url_slides` parameter in the front matter of the talk file
- **Upload** an existing slide deck to `static/` and link using `url_slides` parameter in the front matter of the talk file
- **Embed** your slides (e.g. Google Slides) or presentation video on this page using [shortcodes](https://sourcethemes.com/academic/docs/writing-markdown-latex/).

Further talk details can easily be added to this page using *Markdown* and $\rm \LaTeX$ math code.

-->
