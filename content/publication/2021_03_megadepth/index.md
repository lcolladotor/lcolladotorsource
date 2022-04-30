---
title: "Megadepth: efficient coverage quantification for BigWigs and BAMs"
authors:
- "Christopher Wilks"
- "Omar Ahmed"
- "Daniel N Baker"
- "David Zhang"
- "admin"
- "Ben Langmead"

date: "2021-03-08T00:00:00Z"
doi: "10.1093/bioinformatics/btab152"

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: "*Oxford Bioinformatics*"
publication_short: ""

abstract: "__Motivation__. A common way to summarize sequencing datasets is to quantify data lying within genes or other genomic intervals. This can be slow and can require different tools for different input file types. __Results__.
Megadepth is a fast tool for quantifying alignments and coverage for BigWig and BAM/CRAM input files, using substantially less memory than the next-fastest competitor. Megadepth can summarize coverage within all disjoint intervals of the Gencode V35 gene annotation for more than 19 000 GTExV8 BigWig files in approximately 1 h using 32 threads. Megadepth is available both as a command-line tool and as an R/Bioconductor package providing much faster quantification compared to the rtracklayer package. __Availability and implementation__: https://github.com/ChristopherWilks/megadepth, https://bioconductor.org/packages/megadepth."

# Summary. An optional shortened abstract.
summary:

tags:
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://doi.org/10.1093/bioinformatics/btab152'
url_code: 'https://bioconductor.org/packages/megadepth'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://github.com/ChristopherWilks/megadepth'
url_video: ''
url_preprint: 'https://www.biorxiv.org/content/10.1101/2020.12.17.423317v1'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Oxford Bioinformatics**](https://doi.org/10.1093/bioinformatics/btab152)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

<!--

{{% callout note %}}
Click the *Cite* button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Click the *Slides* button above to demo Academic's Markdown slides feature.
{{% /callout %}}

Supplementary notes can be added here, including [code and math](https://sourcethemes.com/academic/docs/writing-markdown-latex/).
-->