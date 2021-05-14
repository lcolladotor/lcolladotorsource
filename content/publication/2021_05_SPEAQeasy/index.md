---
title: "SPEAQeasy: a scalable pipeline for expression analysis and quantification for R/Bioconductor-powered RNA-seq analyses"
authors:
- "Nicholas J. Eagles"
- "Emily E. Burke"
- "Jacob Leonard"
- "Brianna K. Barry"
- "Joshua M. Stolz"
- "Louise Huuki"
- "BaDoi N. Phan"
- "Violeta Larios Serrato"
- "Everardo Gutiérrez-Millán"
- "Israel Aguilar-Ordoñez"
- "Andrew E. Jaffe"
- "admin"

date: "2021-05-01T00:00:00Z"
doi: "10.1186/s12859-021-04142-3"

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: "*BMC Bioinformatics*"
publication_short: ""

abstract: "__Background__. RNA sequencing (RNA-seq) is a common and widespread biological assay, and an increasing amount of data is generated with it. In practice, there are a large number of individual steps a researcher must perform before raw RNA-seq reads yield directly valuable information, such as differential gene expression data. Existing software tools are typically specialized, only performing one step–such as alignment of reads to a reference genome–of a larger workflow. The demand for a more comprehensive and reproducible workflow has led to the production of a number of publicly available RNA-seq pipelines. However, we have found that most require computational expertise to set up or share among several users, are not actively maintained, or lack features we have found to be important in our own analyses. __Results__. In response to these concerns, we have developed a Scalable Pipeline for Expression Analysis and Quantification (SPEAQeasy), which is easy to install and share, and provides a bridge towards R/Bioconductor downstream analysis solutions. SPEAQeasy is portable across computational frameworks (SGE, SLURM, local, docker integration) and different configuration files are provided (http://research.libd.org/SPEAQeasy/). __Conclusions__. SPEAQeasy is user-friendly and lowers the computational-domain entry barrier for biologists and clinicians to RNA-seq data processing as the main input file is a table with sample names and their corresponding FASTQ files. The goal is to provide a flexible pipeline that is immediately usable by researchers, regardless of their technical background or computing environment."

# Summary. An optional shortened abstract.
summary:

tags:
- BrainSeq
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: 'https://doi.org/10.1186/s12859-021-04142-3'
url_code: 'https://github.com/LieberInstitute/SPEAQeasy'
url_dataset: 'https://github.com/LieberInstitute/SPEAQeasy-example'
url_poster: ''
url_project: ''
url_slides: 'http://research.libd.org/SPEAQeasy/'
url_source: ''
url_video: ''
url_preprint: 'https://www.biorxiv.org/content/10.1101/2020.12.11.386789v1'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**BMC Bioinformatics**](https://doi.org/10.1186/s12859-021-04142-3)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: ["BrainSeq"]

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

<!--

{{% alert note %}}
Click the *Cite* button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /alert %}}

{{% alert note %}}
Click the *Slides* button above to demo Academic's Markdown slides feature.
{{% /alert %}}

Supplementary notes can be added here, including [code and math](https://sourcethemes.com/academic/docs/writing-markdown-latex/).
-->