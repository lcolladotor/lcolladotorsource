---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Benchmark of cellular deconvolution methods using a multi-assay reference dataset from postmortem human prefrontal cortex"
subtitle: ''
summary: ''
authors:
- lahuuki
- "Kelsey D. Montgomery __*__"
- Sang Ho Kwon
- Sophia Cinquemani
- nickeagles
- daianna21
- Sean K. Maden
- Joel E. Kleinman
- Thomas M. Hyde
- Stephanie C. Hicks
- "Kristen R. Maynard &dagger;"
- admin
tags: ["deconvolution"]
categories: []
date: '2024-02-09'
lastmod: ''
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2024.02.09.579665)'
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: ["deconvolution"]
publishDate: ''
publication_types:
- '3'
abstract: "**Background** Cellular deconvolution of bulk RNA-sequencing (RNA-seq) data using single cell or nuclei RNA-seq (sc/snRNA-seq) reference data is an important strategy for estimating cell type composition in heterogeneous tissues, such as human brain. Computational methods for deconvolution have been developed and benchmarked against simulated data, pseudobulked sc/snRNA-seq data, or immunohistochemistry reference data. A major limitation in developing improved deconvolution algorithms has been the lack of integrated datasets with orthogonal measurements of gene expression and estimates of cell type proportions on the same tissue sample. Deconvolution algorithm performance has not yet been evaluated across different RNA extraction methods (cytosolic, nuclear, or whole cell RNA), different library preparation types (mRNA enrichment vs. ribosomal RNA depletion), or with matched single cell reference datasets.

**Results** A rich multi-assay dataset was generated in postmortem human dorsolateral prefrontal cortex (DLPFC) from 22 tissue blocks. Assays included spatially-resolved transcriptomics, snRNA-seq, bulk RNA-seq (across six library/extraction RNA-seq combinations), and RNAScope/Immunofluorescence (RNAScope/IF) for six broad cell types. The Mean Ratio method, implemented in the DeconvoBuddies R package, was developed for selecting cell type marker genes. Six computational deconvolution algorithms were evaluated in DLPFC and predicted cell type proportions were compared to orthogonal RNAScope/IF measurements.

**Conclusions** Bisque and hspe were the most accurate methods, were robust to differences in RNA library types and extractions. This multi-assay dataset showed that cell size differences, marker genes differentially quantified across RNA libraries, and cell composition variability in reference snRNA-seq impact the accuracy of current deconvolution methods."
publication: '*bioRxiv*'
doi: 10.1101/2024.02.09.579665
links:
- name: Preprint
  url: https://doi.org/10.1101/2024.02.09.579665
- name: Code
  url: https://github.com/LieberInstitute/Human_DLPFC_Deconvolution
- name: Bioconductor
  url: https://github.com/LieberInstitute/DeconvoBuddies
---

{{% tweet user="lahuuki" id="1779902215328608480" %}}
