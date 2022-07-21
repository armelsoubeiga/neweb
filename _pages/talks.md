---
title: "Tech Transfert"
permalink: /talks/
author_profile: true
---

{% include base_path %}

## web scraping with R

I wrote a book on web scraping with R. It's a pretty practical book with hands-on projects. It covers:

- Scrapers for web 1.0 & web 2.0
- 8 practical scraping projects with or without APIs
- Scraper automation on local and cloud
- Web mining & crawling
- Implementation of crawler & scraper robots

<div align="center">

<img src="https://raw.githubusercontent.com/armelsoubeiga/neweb/main/images/techtransfert/ebook.jpg"  height="300px"/>
<br/><br/>

[Amazon-ebook](https://www.amazon.com/dp/B0B6YD45B1) | [Amazon-paperback](https://www.amazon.com/dp/B0B6YWXVZ7)

</div>

## BayesPostEst

[![R build status](https://github.com/ShanaScogin/BayesPostEst/workflows/R-CMD-check/badge.svg)](https://github.com/ShanaScogin/BayesPostEst/actions)
[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/BayesPostEst)](https://CRAN.R-project.org/package=BayesPostEst)
[![Codecov test coverage](https://codecov.io/gh/ShanaScogin/BayesPostEst/branch/master/graph/badge.svg)](https://codecov.io/gh/ShanaScogin/BayesPostEst?branch=master)

I am a developer of the [BayesPostEst](https://cran.r-project.org/package=BayesPostEst) R package for generating postestimation quantities of interest from Bayesian models. The package contains functions for producing regression tables, plotting predicted probabilities, calculating first differences, creating coefficient plots, and many other quantities. You can view the [Journal of Open Source Software](https://joss.theoj.org/) article for the package [here](https://doi.org/10.21105/joss.01722).

{% include gallery %}

To install the latest release on CRAN:

```r
install.packages("BayesPostEst")
```

The latest [development version](https://github.com/ShanaScogin/BayesPostEst) on GitHub can be installed with:

```r
library(remotes)
install_github("ShanaScogin/BayesPostEst")
```

You can try out the `mcmcCoefPlot` function from the package in the interactive R console below:

# RWmisc

[![R build status](https://github.com/jayrobwilliams/RWmisc/workflows/R-CMD-check/badge.svg)](https://github.com/jayrobwilliams/RWmisc/actions)
[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/RWmisc)](https://CRAN.R-project.org/package=RWmisc)
[![codecov](https://codecov.io/gh/jayrobwilliams/RWmisc/branch/master/graph/badge.svg)](https://codecov.io/gh/jayrobwilliams/RWmisc)

I've collected convenience functions that I've written to address issues I frequently confront in my work into a personal R package called [RWmisc](https://CRAN.R-project.org/package=RWmisc). It includes functions for:

- Managing multiple different projections for cross-national spatial data
- Converting latitude-longitude data in archaic forms (degrees, minutes, seconds)
- Correcting for overlapping polygons when aggregating raster data to polygons
- My custom minimal ggplot2 theme

![](/images/spatial_weighting.png)

To install the latest release on CRAN:

```r
install.packages("RWmisc")
```

The latest [development version](https://github.com/jayrobwilliams/RWmisc) on GitHub can be installed with:

```r
library(remotes)
install_github("jayrobwilliams/RWmisc")
```

# Other resources

I also have a number of other software resources focused on making computation and academic life easier:

- [The template](https://github.com/jayrobwilliams/JobMarket) I use for my academic job market materials
    - Fill in school/position information in one file and it populates to all statements
    - Generate summary statistics from teaching evaluations and integrate into statements
    - Combine multiple teaching evaluations into a single portfolio document
    - Do all of this programmatically with GNU Make!
- [The template](https://github.com/jayrobwilliams/UNC-Dissertation-Template) I used for my dissertation
    - This satisfied the formatting requirements at UNC in 2019
    - Some tweaking likely required to use at another institution or in the future
- [Scripts](https://github.com/jayrobwilliams/Teaching) that I use to save time on various teaching-related tasks like grading
- [Functions](https://github.com/jayrobwilliams/ComputerVision) for extracting still frames from videos and information from images in Python using OpenCV
- [Compiling OpenCV](/files/html/OpenCV_Install.html) from source for Anaconda virtual environments instead of Homebrew ones or system Python installations
