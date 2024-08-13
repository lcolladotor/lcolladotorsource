---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Integrating gene expression and imaging data across Visium capture areas with visiumStitched"
subtitle: ''
summary: ''
authors:
- nickeagles
- Svitlana V. Bach
- Madhavi Tippani
- Prashanthi Ravichandran
- Yufeng Du
- Ryan A. Miller
- Thomas M. Hyde
- Stephanie C. Page
- Keri Martinowich
- admin
tags: ["spatial", "spatialLIBD"]
categories: []
date: '2024-08-08'
lastmod: ''
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2024.08.08.607222)'
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: ["spatial"]
publishDate: ''
publication_types:
- '3'
abstract: "**Background** Visium is a widely-used spatially-resolved transcriptomics assay available from 10x Genomics. Standard Visium capture areas (6.5mm by 6.5mm) limit the survey of larger tissue structures, but combining overlapping images and associated gene expression data allow for more complex study designs. Current software can handle nested or partial image overlaps, but is designed for merging up to two capture areas, and cannot account for some technical scenarios related to capture area alignment.

**Results** We generated Visium data from a postmortem human tissue sample such that two capture areas were partially overlapping and a third one was adjacent. We developed the R/Bioconductor package visiumStitched, which facilitates stitching the images together with Fiji (ImageJ), and constructing SpatialExperiment R objects with the stitched images and gene expression data. visiumStitched constructs an artificial hexagonal array grid which allows seamless downstream analyses such as spatially-aware clustering without discarding data from overlapping spots. Data stitched with visiumStitched can then be interactively visualized with spatialLIBD.

**Conclusions** visiumStitched provides a simple, but flexible framework to handle various multi-capture area study design scenarios. Specifically, it resolves a data processing step without disrupting analysis workflows and without discarding data from overlapping spots. visiumStiched relies on affine transformations by Fiji, which have limitations and are less accurate when aligning against an atlas or other situations. visiumStiched provides an easy-to-use solution which expands possibilities for designing multi-capture area study designs."
publication: '*bioRxiv*'
doi: 10.1101/2024.08.08.607222
links:
- name: Preprint
  url: https://doi.org/10.1101/2024.08.08.607222
- name: Code
  url: https://github.com/LieberInstitute/visiumStitched_brain
- name: Bioconductor
  url: https://github.com/LieberInstitute/visiumStitched
---

{{% tweet user="lcolladotor" id="1823057993249996915" %}}
