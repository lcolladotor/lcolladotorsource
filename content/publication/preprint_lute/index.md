---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "lute: estimating the cell composition of heterogeneous tissue with varying cell sizes using gene expression"
subtitle: ''
summary: ''
authors:
- Sean K. Maden
- lahuuki
- Sang Ho Kwon
- admin
- Kristen R. Maynard
- Stephanie C. Hicks
tags: ["deconvolution"]
categories: []
date: '2024-04-04'
lastmod: ''
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2024.04.04.588105)'
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
abstract: "Relative cell type fraction estimates in bulk RNA-sequencing data are important to control for cell composition differences across heterogenous tissue samples. Current computational tools estimate relative RNA abundances rather than cell type proportions in tissues with varying cell sizes, leading to biased estimates. We present lute, a computational tool to accurately deconvolute cell types with varying sizes. Our software wraps existing deconvolution algorithms in a standardized framework. Using simulated and real datasets, we demonstrate how lute adjusts for differences in cell sizes to improve the accuracy of cell composition. Software is available from https://bioconductor.org/packages/lute."
publication: '*bioRxiv*'
doi: 10.1101/2024.04.04.588105
links:
- name: Preprint
  url: https://doi.org/10.1101/2024.04.04.588105
- name: Code
  url: https://github.com/LieberInstitute/deconvo_lute-paper
- name: Bioconductor
  url: https://bioconductor.org/packages/lute
---

{{% tweet user="MadenSean" id="1782465272840167522" %}}
