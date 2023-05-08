+++
# Project title.
title = "derfinder"

# Date this page was created.
date = 2013-04-19T00:00:00

# Project summary to display on homepage.
summary = "Métodos agnósticos a la anotación para datos de expresión génica"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["derfinder"]

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
links = [{icon_pack = "fab", icon="twitter", name="#derfinder", url = "https://twitter.com/search?q=%23derfinder&src=typed_query"}, {icon_pack = "fab", icon = "r-project", name = "Bioconductor", url = "https://bioconductor.org/packages/derfinder"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your project's folder. 
[image]
  # Caption (optional)
  caption = "Image credit: [**NAR**](https://doi.org/10.1093/nar/gkw852)"
  
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

El objetivo de mi Ph.D. con [Jeff Leek](http://jtleek.com/) y [Andrew Jaffe](http://aejaffe.com/) en JHBSPH fue desarrollar métodos estadísticos y software que permitan a los investigadores diferenciar las fuentes de variación observadas en RNA-seq mientras se minimiza la dependencia de la anotación conocida. Esto permite a los investigadores corregir la variación tecnológica y estudiar la variación biológica que impulsa su fenotipo de interés. Este trabajo condujo al desarrollo de los paquetes de bioconductores `derfinder` y `regionReport`. Luego aplicamos estos métodos para mejorar nuestra comprensión de los trastornos neuropsiquiátricos utilizando la colección de cerebros humanos del Lieber Institute for Brain Development.
