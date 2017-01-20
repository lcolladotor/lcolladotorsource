+++
image = ""
publication_short = "NAR"
math = false
image_preview = ""
url_slides = ""
highlight = true
selected = true
url_project = "http://leekgroup.github.io/derSupplement/"
abstract_short = "derfinder analysis using expressed region-level and single base-level approaches provides a compromise between full transcript reconstruction and feature-level analysis. The package is available from Bioconductor."
url_pdf = "http://nar.oxfordjournals.org/content/early/2016/09/29/nar.gkw852.full.pdf+html"
date = "2016-09-15T00:00:00"
url_dataset = ""
authors = ["__L Collado-Torres__", "A Nellore", "AC Frazee", "C Wilks", "MI Love", "B Langmead", "RA Irizarry", "JT Leek", "AE Jaffe"]
abstract = "Differential expression analysis of RNA sequencing (RNA-seq) data typically relies on reconstructing transcripts or counting reads that overlap known gene structures. We previously introduced an intermediate statistical approach called differentially expressed region (DER) finder that seeks to identify contiguous regions of the genome showing differential expression signal at single base resolution without relying on existing annotation or potentially inaccurate transcript assembly. We present the derfinder software that improves our annotation-agnostic approach to RNA-seq analysis by: (i) implementing a computationally efficient bump-hunting approach to identify DERs that permits genome-scale analyses in a large number of samples, (ii) introducing a flexible statistical modeling framework, including multi-group and time-course analyses and (iii) introducing a new set of data visualizations for expressed region analysis. We apply this approach to public RNA-seq data from the Genotype-Tissue Expression (GTEx) project and BrainSpan project to show that derfinder permits the analysis of hundreds of samples at base resolution in R, identifies expression outside of known gene boundaries and can be used to visualize expressed regions at base-resolution. In simulations, our base resolution approaches enable discovery in the presence of incomplete annotation and is nearly as powerful as feature-level methods when the annotation is complete. derfinder analysis using expressed region-level and single base-level approaches provides a compromise between full transcript reconstruction and feature-level analysis. The package is available from Bioconductor at www.bioconductor.org/packages/derfinder."
publication_types = ["0"]
url_code = "https://github.com/leekgroup/derSupplement"
publication = "Nucleic Acids Research"
title = "Flexible expressed region analysis for RNA-seq with derfinder"
url_video = ""

[[url_custom]]
    name = "Bioconductor"
    url = "http://bioconductor.org/packages/derfinder"

[[url_custom]]
    name = "Pre-print"
    url = "http://biorxiv.org/content/early/2016/05/19/015370"
+++
