---
title: "SpatialExperiment: infrastructure for spatially resolved transcriptomics data in R using Bioconductor"
authors:
- "Dario Righelli __*__"
- "Lukas M. Weber __*__"
- "Helena L. Crowell __*__"
- "bpardo"
- "admin"
- "Shila Ghazanfar"
- "Aaron T. L. Lun,"
- "tephanie C. Hicks &dagger;"
- "Davide Risso &dagger;"

date: "2021-01-27T00:00:00Z"
doi: "10.1101/2021.01.27.428431"

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: "*bioRxiv*"
publication_short: ""

abstract: "__Motivation__. Spatially resolved transcriptomics is a new set of technologies to measure gene expression for up to thousands of genes at near-single-cell, single-cell, or sub-cellular resolution, together with the spatial positions of the measurements. Analyzing combined molecular and spatial information has generated new insights about biological processes that manifest in a spatial manner within tissues. However, to efficiently analyze these data, specialized data infrastructure is required, which facilitates storage, retrieval, subsetting, and interfacing with downstream tools. __Results__. Here, we describe SpatialExperiment, a new data infrastructure for storing and accessing spatially resolved transcriptomics data, implemented within the Bioconductor framework in the R programming language. SpatialExperiment extends the existing SingleCellExperiment for single-cell data from the Bioconductor framework, which brings with it advantages of modularity, interoperability, standardized operations, and comprehensive documentation. We demonstrate the structure and user interface with examples from the 10x Genomics Visium and seqFISH platforms. SpatialExperiment is extendable to alternative technological platforms measuring expression and to new types of data modalities, such as spatial immunofluorescence or proteomics, in the future. We also provide access to example datasets and visualization tools in the STexampleData, TENxVisiumData, and ggspavis packages. __Availability and Implementation__. SpatialExperiment is freely available from Bioconductor at https://bioconductor.org/packages/SpatialExperiment. The STexampleData, TENxVisiumData, and ggspavis packages are available from GitHub and will be submitted to Bioconductor."

# Summary. An optional shortened abstract.
summary:

tags:
- spatial
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: ''
url_code: 'https://bioconductor.org/packages/SpatialExperiment'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://github.com/drighelli/SpatialExperiment'
url_video: ''
url_preprint: 'https://www.biorxiv.org/content/10.1101/2021.01.27.428431v1'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2021.01.27.428431)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: ["spatial"]

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