---
title: "Detection of pathogenic splicing events from RNA-sequencing data using dasper"
authors:
- "David Zhang"
- "Regina H. Reynolds"
- "Sonia Garcia-Ruiz"
- "Emil K Gustavsson"
- "Sid Sethi"
- "Sara Aguti"
- "Ines A. Barbosa"
- "Jack J. Collier"
- "Henry Houlden"
- "Robert McFarland"
- "Francesco Muntoni"
- "Monika Oláhová"
- "Joanna Poulton"
- "Michael Simpson"
- "Robert D.S. Pitceathly"
- "Robert W. Taylor"
- "Haiyan Zhou"
- "Charu Deshpande"
- "Juan A. Botia"
- "admin"
- "Mina Ryten"

date: "2021-03-29T00:00:00Z"
doi: "10.1101/2021.03.29.437534"

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

abstract: Although next-generation sequencing technologies have accelerated the discovery of novel gene-to-disease associations, many patients with suspected Mendelian diseases still leave the clinic without a genetic diagnosis. An estimated one third of these patients will have disorders caused by mutations impacting splicing. RNA-sequencing has been shown to be a promising diagnostic tool, however few methods have been developed to integrate RNA-sequencing data into the diagnostic pipeline. Here, we introduce dasper, an R/Bioconductor package that improves upon existing tools for detecting aberrant splicing by using machine learning to incorporate disruptions in exon-exon junction counts as well as coverage. dasper is designed for diagnostics, providing a rank-based report of how aberrant each splicing event looks, as well as including visualization functionality to facilitate interpretation. We validate dasper using 16 patient-derived fibroblast cell lines harbouring pathogenic variants known to impact splicing. We find that dasper is able to detect pathogenic splicing events with greater accuracy than existing LeafCutterMD or z-score approaches. Furthermore, by only applying a broad OMIM gene filter (without any variant-level filters), dasper is able to detect pathogenic splicing events within the top 10 most aberrant identified for each patient. Since using publicly available control data minimises costs associated with incorporating RNA-sequencing into diagnostic pipelines, we also investigate the use of 504 GTEx fibroblast samples as controls. We find that dasper leverages publicly available data effectively, ranking pathogenic splicing events in the top 25. Thus, we believe dasper can increase diagnostic yield for a pathogenic splicing variants and enable the efficient implementation of RNA-sequencing for diagnostics in clinical laboratories.

# Summary. An optional shortened abstract.
summary:

tags:
- recount2
featured: false

# links:
# - name: ""
#   url: ""
url_pdf: ''
url_code: 'https://bioconductor.org/packages/dasper'
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: 'http://dzhang32.github.io/dasper/'
url_source: 'https://github.com/dzhang32/dasper'
url_video: ''
url_preprint: 'https://www.biorxiv.org/content/10.1101/2021.03.29.437534v1'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**bioRxiv**](https://doi.org/10.1101/2021.03.29.437534)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: ["recount2"]

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

{{% tweet user="lcolladotor" id="1312140968796151810" %}}