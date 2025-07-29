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
date: '2025-05-01'
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
- '2'
abstract: "**Background**: Relative cell type fraction estimates in bulk RNA-sequencing data are important to control for cell composition differences across heterogenous tissue samples. While there exist algorithms to estimate the cell type proportions in tissues, a major challenge is the algorithms can show reduced performance if using tissues that have varying cell sizes, such as in brain tissue. In this way, without adjusting for differences in cell sizes, computational algorithms estimate the relative fraction of RNA attributable to each cell type, rather than the relative fraction of cell types, leading to potentially biased estimates in cellular composition. Furthermore, these tools were built on different frameworks with non-uniform input data formats while addressing different types of systematic errors or unwanted bias. **Results**: We present _lute_, a software tool to accurately deconvolute cell types with varying sizes. Our package _lute_ wraps existing deconvolution algorithms in a flexible and extensible framework to enable easy benchmarking and comparison of existing deconvolution algorithms. Using simulated and real datasets, we demonstrate how _lute_ adjusts for differences in cell sizes to improve the accuracy of cell composition. **Conclusions**: Our software (https://bioconductor.org/packages/lute) can be used to enhance and improve existing deconvolution algorithms and can be used broadly for any type of tissue containing cell types with varying cell sizes."
publication: '*BMC Genomics*'
doi: 10.1186/s12864-025-11508-x
links:
- name: Preprint
  url: https://doi.org/10.1101/2024.04.04.588105
- name: Code
  url: https://github.com/LieberInstitute/deconvo_lute-paper
- name: Bioconductor
  url: https://bioconductor.org/packages/lute
---

{{% tweet user="MadenSean" id="1782465272840167522" %}}
