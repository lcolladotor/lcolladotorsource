+++
# Project title.
title = "espacial"

# Date this page was created.
date = 2020-02-29T00:00:00

# Project summary to display on homepage.
summary = "Transcriptómica espacial del cerebro humano utilizando Visium de 10x Genomics"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["spatial", "HumanPilot", "spatialLIBD", "VistoSeg", "spatialDLPFC", "Visium_SPD_AD"]

# Optional external URL for project (replaces project detail page).
external_link = ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = ""
url_slides = ""
url_video = ""
url_code = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
links = [{icon_pack = "fab", icon="twitter", name="#Visium_SPG_AD", url = "https://twitter.com/search?q=%23Visium_SPG_AD&src=typed_query"}, {icon_pack = "fab", icon="twitter", name="#spatialDLPFC", url = "https://twitter.com/search?q=%23spatialDLPFC&src=typed_query"}, {icon_pack = "fab", icon="twitter", name="#spatialLIBD", url = "https://twitter.com/search?q=%23spatialLIBD&src=typed_query"}, {name = "Aplicación shiny de spatialLIBD", url = "http://spatial.libd.org/spatialLIBD"}, {icon_pack = "fab", icon = "r-project", name = "spatialLIBD en Bioconductor", url = "https://bioconductor.org/packages/spatialLIBD"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**bioRxiv**](https://www.biorxiv.org/content/10.1101/2020.02.28.969931v1)"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

En febrero de 2020, publicamos la [primera versión preliminar](https://www.biorxiv.org/content/10.1101/2020.02.28.969931v1) utilizando la plataforma 10x Genomics Visium para transcriptómica espacial. Para este proyecto, creamos el paquete de Bioconductor [`spatialLIBD`](https://bioconductor.org/packages/spatialLIBD) y comenzamos a desarrollar nuevos métodos analíticos para este tipo de datos. Dado que compartimos todos los datos y el código cuando publicamos la preimpresión, cuando [la publicación revisada por pares](https://doi.org/10.1038/s41593-020-00787-0) y se hizo pública en febrero de 2021, otros ya habían utilizado nuestro conjunto de datos para desarrollar y mostrar sus métodos. Por ejemplo, [`BayesSpace`](http://bioconductor.org/packages/BayesSpace) [preimpresión](https://doi.org/10.1101/2020.09.04.283812) se publicó en septiembre de 2020, antes a su propia [publicación revisada por pares](https://doi.org/10.1038/s41587-021-00935-2) de junio de 2021. Ahora estamos usando `BayesSpace` en nuestros proyectos. Este es un ejemplo de cómo la ciencia abierta y el acceso abierto aceleran la ciencia.

{{< tweet user="lcolladotor" id="1233661576433061888" >}}

{{< tweet user="PardoBree" id="1388253938391175173" >}}

{{< tweet user="lahuuki" id="1626686409313763328" >}}

{{< tweet user="sanghokwon17" id="1650589385379962881" >}}
