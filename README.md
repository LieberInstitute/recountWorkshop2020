
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Human RNA-seq data from recount2 and related packages

<!-- badges: start -->

[![Lifecycle:
stable](https://img.shields.io/badge/lifecycle-stable-brightgreen.svg)](https://www.tidyverse.org/lifecycle/#stable)
[![BioC
status](http://bioconductor.org/shields/build/release/workflows/recountWorkflow.svg)](http://bioconductor.org/checkResults/release/workflows-LATEST/recountWorkflow/)
[![R build
status](https://github.com/LieberInstitute/recountWorkshop2020/workflows/R-CMD-check-bioc/badge.svg)](https://github.com/LieberInstitute/recountWorkshop2020/actions)
<!-- badges: end -->

<img src="https://raw.githubusercontent.com/LieberInstitute/recountWorkshop2020/master/inst/vignettes/Figure1.png" width="800px" />

## Instructor

[Leonardo Collado-Torres](http://lcolladotor.github.io/)

  - [GitHub](https://github.com/lcolladotor)
  - [Twitter](https://twitter.com/fellgernon)
  - [Email](mailto:lcolladotor@gmail.com)

## Workshop Description

The recount2 project re-processed RNA sequencing (RNA-seq) data on over
70,000 human RNA-seq samples spanning a variety of tissues, cell types
and disease conditions. Researchers can easily access these data via the
`recount` Bioconductor package, and can quickly import gene, exon,
exon-exon junction and base-pair coverage data for uniformly processed
data from the SRA, GTEx and TCGA projects in R for analysis. This
workshop will include an overview of the recount2 project as well as
methods and tools that have been to improve it since 2017. The overview
will be followed by a hands-on session where you will dive into
`recount` and related packages along the lines of the [recount
workflow](http://bioconductor.org/packages/release/workflows/html/recountWorkflow.html).
We will also cover new related packages such as
[`GenomicState`](http://bioconductor/packages/GenomicState).

In more detail, this workshop will cover different use cases of the
`recount` package, including downloading and normalizing data,
processing and cleaning relevant phenotype data (including
`recount-brain`), performing differential expression (DE) analyses using
other Bioconductor packages. The workshop will also cover how to use the
base-pair coverage data for annotation-agnostic DE analyses and for
visualizing coverage data for features of interest. After taking this
workshop, attendees will be ready to enhance their analyses by
leveraging RNA-seq data from 70,000 human samples.

[recount2 website](https://jhubiostatistics.shinyapps.io/recount/),
[recount package](http://bioconductor.org/packages/recount),
[paper](http://www.nature.com/nbt/journal/v35/n4/full/nbt.3838.html),
[recount
workflow](http://bioconductor.org/packages/release/workflows/html/recountWorkflow.html).

Prior editions:
[Bioc2017](https://github.com/LieberInstitute/recountWorkshop),
[BioC2019](https://github.com/LieberInstitute/recountWorkshop2019).

## Pre-requisites

  - Basic knowledge of R syntax
  - Basic knowledge of RNA-seq or gene expression data
  - Familiarity with `SummarizedExperiment`
    [vignette](http://bioconductor.org/packages/release/bioc/vignettes/SummarizedExperiment/inst/doc/SummarizedExperiment.html)
  - Familiarity with the `RangedSummarizedExperiment` class

## Workshop Participation

Students are expected to ask questions during the recount2 overview
presentation and to bring their own laptop so they can follow the
hands-on portion of the workshop.


The slides for the workshop are available through [speakerdeck](https://speakerdeck.com/lcolladotor/human-rna-seq-data-from-recount2-and-related-packages).

<script async class="speakerdeck-embed" data-id="78092f5c558242f1aa3085d9abc9c061" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

You can download a Docker image with
all the workshop files using:

``` bash
docker run -e PASSWORD=bioc2020 -p 8787:8787 -d --rm lcollado/recountworkshop2020
```

Then, log in to RStudio at <http://localhost:8787> using username
`rstudio` and password `bioc2020`. Note that on Windows you need to
provide your localhost IP address like `http://191.163.92.108:8787/` -
find it using `docker-machine ip default` in Docker’s terminal.

To see the vignette on RStudio’s window (from the docker image), run
`browseVignettes(package = "recountWorkshop2020")`. Click on one of the
links, “HTML”, “source”, “R code”. In case of `The requested page was
not found` error, add `help/` to the URL right after the hostname, e.g.,
<http://localhost:8787/help/library/recountWorkshop2020/doc/recount-workshop.html>.
This is a [known
bug](https://github.com/rocker-org/rocker-versioned/issues/178).

### *Bioconductor* packages used

`SummarizedExperiment`, `recount`, `GenomicRanges`, `DESeq2`,
`derfinder`, `regionReport` are among the packages that will be
explicitly covered.

### Time outline

| Activity                                                                 | Time  |
| ------------------------------------------------------------------------ | ----- |
| recount2 project overview                                                | 10m   |
| accessing gene count data with recount                                   | 15m   |
| Gene-level analysis with recount2 and recount-brain                      | 15m   |
| Un-annotated transcriptome methods overview: `derfinder`, `GenomicState` | 5 min |
| the future: recount3                                                     | 5m    |

Total: a 50-55 minute session.

## Workshop goals and objectives

### Learning goals

  - Understand the publicly data available via the recount2 project
    beyond gene counts
  - Identify how recount2 data could be useful for your RNA-seq projects
    and how you can use it
  - Describe the annotation-agnostic methods powered by recount2 that
    complement other RNA-seq analysis pipelines

### Learning objectives

  - Re-analyze public RNA-seq data using the recount Bioconductor
    package
  - Recognize how to access the different types of data hosted by
    recount2
  - Locate resources that enhance recount2 such as recount-brain,
    `derfinder`, and `GenomicState`

## Installation instructions

Get the latest stable `R` release from
[CRAN](http://cran.r-project.org/). Then install `recountWorkshop2020`
using from [GitHub](https://github.com/) with the following code:

``` r
if (!requireNamespace("BiocManager", quietly = TRUE)) {
    install.packages("BiocManager")
}

BiocManager::install("LieberInstitute/recountWorkshop2020")
```

## Citation

Below is the citation output from using `citation('recount` in R. Please
run this yourself to check for any updates on how to cite **recount**.

``` r
print(citation("recount")[2], bibtex = TRUE)
#> 
#> Collado-Torres L, Nellore A, Jaffe AE (2017). "recount workflow:
#> Accessing over 70,000 human RNA-seq samples with Bioconductor [version
#> 1; referees: 1 approved, 2 approved with reservations]."
#> _F1000Research_. doi: 10.12688/f1000research.12223.1 (URL:
#> https://doi.org/10.12688/f1000research.12223.1), <URL:
#> https://f1000research.com/articles/6-1558/v1>.
#> 
#> A BibTeX entry for LaTeX users is
#> 
#>   @Article{,
#>     title = {recount workflow: Accessing over 70,000 human RNA-seq samples with Bioconductor [version 1; referees: 1 approved, 2 approved with reservations]},
#>     author = {Leonardo Collado-Torres and Abhinav Nellore and Andrew E. Jaffe},
#>     year = {2017},
#>     journal = {F1000Research},
#>     doi = {10.12688/f1000research.12223.1},
#>     url = {https://f1000research.com/articles/6-1558/v1},
#>   }
```

Please note that the `recount` was only made possible thanks to many
other R and bioinformatics software authors, which are cited either in
the vignettes and/or the paper(s) describing this package.

## Code of Conduct

Please note that the `recountWorkshop2020` project is released with a
[Contributor Code of
Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html).
By contributing to this project, you agree to abide by its terms.

## Development tools

  - Continuous code testing is possible thanks to [GitHub
    actions](https://www.tidyverse.org/blog/2020/04/usethis-1-6-0/)
    through *[usethis](https://CRAN.R-project.org/package=usethis)*,
    *[remotes](https://CRAN.R-project.org/package=remotes)*,
    *[sysreqs](https://github.com/r-hub/sysreqs)* and
    *[rcmdcheck](https://CRAN.R-project.org/package=rcmdcheck)*
    customized to use [Bioconductor’s docker
    containers](https://www.bioconductor.org/help/docker/) and
    *[BiocCheck](https://bioconductor.org/packages/3.11/BiocCheck)*.
  - Code coverage assessment is possible thanks to
    [codecov](https://codecov.io/gh) and
    *[covr](https://CRAN.R-project.org/package=covr)*.
  - The [documentation
    website](http://LieberInstitute.github.io/recountWorkshop2020) is
    automatically updated thanks to
    *[pkgdown](https://CRAN.R-project.org/package=pkgdown)*.
  - The code is styled automatically thanks to
    *[styler](https://CRAN.R-project.org/package=styler)*.
  - The documentation is formatted thanks to
    *[devtools](https://CRAN.R-project.org/package=devtools)* and
    *[roxygen2](https://CRAN.R-project.org/package=roxygen2)*.

For more details, check the `dev` directory.

This package was developed using
*[biocthis](https://github.com/lcolladotor/biocthis)*.
