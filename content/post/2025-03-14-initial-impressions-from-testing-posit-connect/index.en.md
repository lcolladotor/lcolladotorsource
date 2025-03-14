---
title: Initial impressions from testing Posit Connect
author: L. Collado-Torres
date: '2025-03-14'
slug: initial-impressions-from-testing-posit-connect
categories:
  - rstats
  - LIBD
tags:
  - shiny
  - spatialLIBD
  - iSEE
  - Posit Connect
  - shinyapps.io
subtitle: ''
summary: ''
authors: []
lastmod: '2025-03-14T11:28:38-04:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

Two weeks ago I finished testing [Posit Connect](https://posit.co/products/enterprise/connect/) as a replacement to [shinyapps.io](https://www.shinyapps.io/). At the end of the trial period, I presented my conclusions during a [LIBD rstats club](https://research.libd.org/rstatsclub/) session. Here you can read the [detailed notes](https://docs.google.com/document/d/1CcPwSJiM2aElsQKFXzd1R2jih-Cc6NR5E1MQ_9mYAqA/edit?usp=sharing) and watch the resulting video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/OoVBiO_Oc2k?si=fWbVdcPkx4ilXAA-" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

The video and notes dive more into the technical details and I also performed some live tests. Below I summarize the main points from our use case and solutions we have experience with.

## Our use case

Overall, my team and colleagues at LIBD are in a position where we have:

* Over 75 [`iSEE`](https://bioconductor.org/packages/iSEE/) and [`spatialLIBD`](https://bioconductor.org/packages/spatialLIBD) web apps powered by [`shiny`](https://shiny.rstudio.com/) and hosted on [`shinyapps.io`](https://www.shinyapps.io/).
  * These apps have been deployed by 14 different people so far. That is, we have been able to teach new members or students how to deploy apps: anyone can do so with a bit of training.
* Our apps are typically shared publicly, so we don't really need password-controlled access.
  * We don't share URLs for studies under development assuming that no one will correctly guess the URLs.
* Our data is stored in [`SummarizedExperiment`](https://bioconductor.org/packages/SummarizedExperiment/), [`SingleCellExperiment`](https://bioconductor.org/packages/SingleCellExperiment/), or [`SpatialExperiment`](https://bioconductor.org/packages/SpatialExperiment) objects. The single cell and spatially-resolved transcriptomics data typically involves over 50,000 cells or Visium spots across 20,000 or so genes. Some larger studies are over 100,000 or 200,000 cells/spots. The cells/spots are the columns and the genes are the rows in these large matrices of expression data. Many cells/spots don't have expression data, so the matrices are sparse. For more on these types of objects check the video below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lqxtgpD-heM?si=hnmDYRjdf-MgryNC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

* For spatially-resolved transcriptomics data, `SpatialExperiment` objects also contain images per sample (defined as a Visium capture area). These are typically `lowres` images that are maximum 600 x 600 pixels. One of our largest studies has 120 samples.
  * There are other images that we typically remove from the objects, such as [this case](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/5bbae3e4386cd28222aa29818f2c22e1d60a180d/spatial_hpc/code/01_download_SPE_from_ExperimentHub.R#L26-L35) which saved 3.29 GB of memory by dropping non-essential images in a study with 36 samples. The initial `SpatialExperiment` object used 8.81 GB in memory for [this study](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/5bbae3e4386cd28222aa29818f2c22e1d60a180d/spatial_hpc/code/01_download_SPE_from_ExperimentHub.R#L27).
* The expression matrices are typically saved as `dgCMatrix` objects from the [`Matrix`](https://cran.r-project.org/package=Matrix) package. These are great for storing sparse data if you want it all in memory. However, for our larger studies, we typically just keep one matrix that has the library-size normalized counts (called `logcounts`) and drop the un-normalized `counts`.
  * In the same dataset with 36 samples, this meant another 2.6 GB saved in memory as [shown here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/5bbae3e4386cd28222aa29818f2c22e1d60a180d/spatial_hpc/code/01_download_SPE_from_ExperimentHub.R#L35-L41). This resulted in a reduced `SpatialExperiment` object of 2.92 GB in memory for [this study](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/5bbae3e4386cd28222aa29818f2c22e1d60a180d/spatial_hpc/code/01_download_SPE_from_ExperimentHub.R#L41) containing only the `logcounts` normalized gene expression data and the `lowres` images.
* For larger studies, we can use [`HD5Array`](https://bioconductor.org/packages/HD5Array/) objects to store the expression data on disk and only load the data in memory when needed. 
  * For a dataset with 120 samples, this results in a 505.20 Mb `SpatialExperiment` object in memory that has the `counts`, `lowres` images, 36,601 genes, and 599,034 spots as [shown here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/1f6f4d56c76d476f928ce606c23f2b51923d5a0d/spatialDLPFC_mdd_bpd/code/app.R#L74-L91). The files on disk use about 1.5 GB of space: 1.4 GB for the `.h5` file as [noted here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/1f6f4d56c76d476f928ce606c23f2b51923d5a0d/spatialDLPFC_mdd_bpd/code/app.R#L93-L95).
  * Actually, for this study, we have another `SpatialExperiment` object with `logcounts` and `counts`, no images, 28,965 genes, and 535,248 spots that uses 154.04 Mb in memory as [noted here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/1f6f4d56c76d476f928ce606c23f2b51923d5a0d/spatialDLPFC_mdd_bpd/code/app.R#L32-L49). However, the files on disk grow to use 13 GB of disk space for the `.h5` file as [shown here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/1f6f4d56c76d476f928ce606c23f2b51923d5a0d/spatialDLPFC_mdd_bpd/code/app.R#L51-L53). I believe that's because the `logcounts` which have decimal numbers take much more disk space to store them. This same object as a sparse memory object and with the `lowres` images added used 10.69 GB of memory as [noted here](https://github.com/LieberInstitute/Posit_Connect_shiny_apps/blob/1f6f4d56c76d476f928ce606c23f2b51923d5a0d/spatialDLPFC_mdd_bpd/code/02_sparseMatrix_in_memory_version/app.R#L26-L43).
  * `HDF5Array` is awesome for saving memory, but it can take up a lot of disk space. It's a great resource developed by Hervé Pagès from Bioconductor's core team.
  * For more on `HDF5Array` and compressed data, check this video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/YoBW7IiNzQA?si=jDE9zph2oIurDGx6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

* We have observed that `iSEE` and `spatialLIBD` need more memory than just the one needed for loading the object as reported on the memory usage graphs provided by [`shinyapps.io`](https://www.shinyapps.io/). That's because of some internal operations, and while both packages try to minimize memory duplication, it's best to have more memory than twice the object size to prevent the apps from crashing: if they are unreliable, people won't use them.
  * In practice, we try to deploy objects that use up to 3 GB of memory when using the 8 GB memory instances on [shinyapps.io](https://www.shinyapps.io/).
  
## Use case summary
  
Overall we have been able to use [`shinyapps.io`](https://www.shinyapps.io/) for studies with R objects that use up to 3 GB of memory with sparse memory `dgCMatrix` objects for storing the `logcounts` normalized expression data. In the case of spatially-resolved transcriptomics projects, we only include the `lowres` images. These objects can also be uploaded within the 3 to 5 GB file size limit as [noted in the official shinyapps documentation](https://docs.posit.co/shinyapps.io/guide/applications/). However, we have datasets where this is no longer possible. You either need more memory or the ability to save data in files larger than 5 GB.

## Deployment options

We have considered the following options for deploying our apps:

* AWS-hosted [shiny-server](https://posit.co/products/open-source/shiny-server/)
  * You choose how much disk space and memory you need on a given AWS instance
  * You have to install R yourself and the open source `shiny-server`
  * You can only have 1 app deployed by AWS instance
  * You upload the data and R code for the app yourself
  * For us, a LIBD system admin has dealt with the AWS and `shiny-server` setup, plus the R updates. Then a second person (myself so far) has had to upload the data and keep the R code up to date. In practice, we rarely update this app.
  * Example: <http://spatial.libd.org/spatialLIBD/> which at some point was deployed on an AWS instance with 128 GB of RAM. We wanted to make sure that this app could handle several dozen users.
* [shinyapps.io](https://www.shinyapps.io/)
  * If you have the best account (`Professional`; check their [pricing information](https://www.shinyapps.io/#pricing-anchor)) you can have apps deployed with up to 8 GB of memory and max 3-5 GB disk space.
  * For our apps, we typically configure them to have 1 R process per instance, with 2 max connections per instance. Aka, up to 2 users per instance.
  * Each app can run in up to 10 instances, so you can have up to 20 users per app.
    * You can deploy the same R code and data under two apps (aka two URLs) or more if you want to have even more capacity.
  * Deployment is done via `rsconnect::deployApp()` which has to upload your data every time and install packages too. While compiled R packages have increased the speed of this process, it can easily take 15-30 minutes per app.
  * Example: [libd.shinyapps.io/spatialDLPFC_Visium_Sp09](https://libd.shinyapps.io/spatialDLPFC_Visium_Sp09) from the [spatialDLPFC](https://research.libd.org/spatialDLPFC/#interactive-websites) project.
* [Posit Connect](https://posit.co/products/enterprise/connect/)
  * You can upload data to the server separate from the R code for the apps.
    * This requires `ssh` access, but that's fairly easy to implement.
  * It can auto-sync the R code from GitHub repositories every 15 minutes.
  * It can auto-sync changes to the list of R packages also through GitHub repositories. This involves `manifest.json` files made with `rsconnect::writeManifest()`.
    * It makes it incredibly easy to update many applications at once by just updating the `manifest.json` files.
    * Enables a much faster update process than `shinyapps.io` as we make updates to `spatialLIBD` to add new features or fix bugs.
  * Your server can have 200 GB of disk space and 31 GB of RAM (as the one I tested) or more resources.
    * This unlocks the ability to upload `HDF5Array`-compressed data that has less memory requirements but larger disk space requirements.
    * Note that the server resources are shared among all apps on the server!
      * My understanding is that `Posit Connect` has ways to deal with resources running out on a server, but I haven't tested this feature.

## Conclusions

[![](https://docs.posit.co/helm/rstudio-connect/kubernetes-howto/images/logoPositConnect.svg)](https://posit.co/products/enterprise/connect/)

Overall, I'm hopeful that we'll get long term access to a `Posit Connect` server. It will allow us to deploy our apps with larger datasets and more memory. It will also make it easier to update our apps and keep them in sync with our GitHub repositories. This will be especially useful as we continue to develop new features and fix bugs in our apps. For example, I typically test new `spatialLIBD` features on one dataset. But we now have many datasets each with different properties, and it's hard to test them all. Instead, with `Posit Connect`, I could modify `spatialLIBD`, then easily update several apps on `Posit Connect`, and check them to see if the new features work as expected. This will make it much easier to maintain our apps and keep them up to date.

If I were to start today, I would use the organization that I tested at [github.com/LieberInstitute/Posit_Connect_shiny_apps](https://github.com/LieberInstitute/Posit_Connect_shiny_apps) using only `HDF5Array` objects to take advantage of the memory savings and faster app load times you get with those objects compared to `dgCMatrix` objects (it takes several dozen seconds more to load a ~10 GB object compared to a 500 MB one). With just these changes, I think that our users will be happier with the apps. Simply being able to visualize our largest datasets would be a great win for us.

Of course, I don't have pricing information for `Posit Connect` yet. But we have reached the limits of what the best [`shinyapps.io`](https://www.shinyapps.io/) accounts offer. I believe that other options exist, but I haven't tested them yet. Though from what I've seen, `Posit Connect` works and I'm very confident that we could teach our team members and collaborators on how to use it effectively.

Regardless of where our apps are deployed, we also need to work on a way to document them all and make it easier for others to find them. I'm aware of [`iSEEhub`](https://bioconductor.org/packages/iSEEhub/)'s existence which makes an app that launches [`iSEE`](https://bioconductor.org/packages/iSEE/) apps from data hosted by [`ExperimentHub`](https://bioconductor.org/packages/ExperimentHub/). We might need to make something like an `spatialLIBDhub` for our datasets.
  
PS. The two members from Posit with whom I interacted with for this test were very friendly and helpful. Thanks again!
