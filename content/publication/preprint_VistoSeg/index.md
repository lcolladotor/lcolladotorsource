---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "VistoSeg: processing utilities for high-resolution Visium/Visium-IF images for spatial transcriptomics data"
subtitle: ''
summary: ''
authors:
- Madhavi Tippani
- Heena R. Divecha
- Joseph L. Catallini II
- Sang Ho Kwon
- Lukas M. Weber
- Abby Spangler
- Andrew E. Jaffe
- Stephanie C. Hicks
- Keri Martinowich
- admin
- "Stephanie C. Page &dagger;"
- "Kristen R. Maynard &dagger;"
tags: ["spatial", "VistoSeg", "spatialDLPFC"]
categories: []
date: '2022-05-13'
lastmod: ''
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2021.08.04.452489)'
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
abstract: "__Background__: Spatial transcriptomics is a next-generation sequencing technology that combines the strengths of transcriptome-wide RNA-sequencing with histological imaging to generate spatial maps of gene expression in intact tissue sections. The 10x Genomics Visium and Visium-Immunofluorescence (Visium-IF) platforms are widely available commercial technologies for quantifying spatially-resolved gene expression. These technologies directly couple gene expression with high resolution histological or immunofluorescence images that contain rich morphological information about the tissue section. However, extracting and integrating image features with gene expression data remains challenging. __Results__: Using MATLAB, we developed VistoSeg, which is a pipeline to process, analyze, and interactively visualize the high-resolution images from the 10x Genomics Visium and Visium-IF platforms. The output from VistoSeg can then be integrated with the spatial-molecular information in downstream analyses using common programming languages, such as R or Python. __Conclusion__: VistoSeg provides user-friendly tools for integrating image-derived metrics from histological and immunofluorescent images with spatially-resolved gene expression data. This integrated approach can advance our understanding of the transcriptional landscape within tissue architecture. VistoSeg is freely available at http://research.libd.org/VistoSeg/. __Impact Statement__: Technologies for measuring gene activity levels, referred to as gene expression, have been evolving over decades and are the core of the transcriptomics subfield within genomics. The first report describing individual cell gene expression is from 2009 and as a method it became commercially available in 2014. While single cell transcriptomics increased our resolution beyond homogenate tissue, the advent of spatial transcriptomics technologies and commercial availability of spatial gene expression platforms, such as Visium, has facilitated studying gene expression in anatomical context. Visium measures local gene expression within the histological organization of single 6.5 mm2 cryosection of tissue. Spatially-resolved transcriptomics provides a new challenge: integrating spatial gene expression with high resolution tissue images (brightfield histology or fluorescent antibody staining). VistoSeg image processing software is compatible with both Visium and Visium-IF from 10x Genomics, which are spatially-resolved transcriptomics assays employing histological and immunofluorescent images, respectively. From these images, the number of cells, identity of cell types, and other image-derived markers can be obtained for thousands of 2,375 µm2 spots, where genome-wide gene expression is also measured. VistoSeg provides tools that enable processing these images in the context of gene expression maps to integrate these two high dimensional data types, and thus help unlock the new frontier in transcriptomics."
publication: '*bioRxiv*'
doi: 10.1101/2021.08.04.452489
links:
- name: Preprint
  url: https://www.biorxiv.org/content/10.1101/2021.08.04.452489v2
- name: Code
  url: https://github.com/LieberInstitute/VistoSeg
- name: Documentation
  url: http://research.libd.org/VistoSeg/
---

{{< tweet user="MadhaviTippani" id="1423734212729921536" >}}
