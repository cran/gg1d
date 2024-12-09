
<!-- README.md is generated from README.Rmd. Please edit that file -->

# gg1d <a href="https://selkamand.github.io/gg1d/"><img src="man/figures/logo.png" align="right" height="120" alt="gg1d website" /></a>

<!-- badges: start -->

[![R-CMD-check](https://github.com/selkamand/gg1d/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/selkamand/gg1d/actions/workflows/R-CMD-check.yaml)
[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
[![Codecov test
coverage](https://codecov.io/gh/selkamand/gg1d/branch/main/graph/badge.svg)](https://app.codecov.io/gh/selkamand/gg1d?branch=main)
![GitHub Issues or Pull
Requests](https://img.shields.io/github/issues-closed/selkamand/gg1d)
[![code
size](https://img.shields.io/github/languages/code-size/selkamand/gg1d.svg)](https://github.com/selkamand/gg1d)
![GitHub last
commit](https://img.shields.io/github/last-commit/selkamand/gg1d)
<!-- badges: end -->

Effortlessly visualize all columns in a data frame with vertically
aligned plots and automatic plot selection based on variable type. Plots
are fully interactive, and custom tooltips can be added.

**Why 1 dimensional plots?**

To understand trends in your data, especially correlative relationships
between 2 or more features, it can be useful to densely stack visual
representations of each feature vertically, regardless of data type. By
unifying the $x$-axis across each plot, **gg1d** turns a series of 1D
plots into an $n\text{-dimensional}$ visualization where
$n = \text{number of columns in dataset}$. Note the key idea of gg1d is
to ‘preserve the individual.’ **gg1d** does **NOT** plot distributions
of properties, but rather each value of a feature for each
subject/observation in the dataset.

gg1d can be used for exploratory data analysis (EDA) or to produce
publication quality graphics summarizing a dataset.

## Installation

``` r
install.packages("gg1d")
```

### Development Version

You can install the development version of gg1d from
[GitHub](https://github.com/) with:

``` r
if (!require("remotes"))
    install.packages("remotes")

remotes::install_github("selkamand/gg1d")
```

## Quick Start

For examples of interactive gg1d plots see the [gg1d
gallery](https://selkamand.github.io/gg1d/articles/gallery.html)

``` r
# Load library
library(gg1d)

# Read data
path_gg1d <- system.file("example.csv", package = "gg1d")
df <- read.csv(path_gg1d, header = TRUE, na.strings = "")

# Plot data, sort by Glasses
gg1d(
  df,
  col_id = "ID",
  col_sort = "Glasses",
  interactive = FALSE,
  verbose = FALSE,
  options = gg1d_options(legend_nrow = 2)
)
```

<img src="man/figures/README-example-1.png" width="100%" />

## Customise Colours

Customise colours by supplying a named list to the `palettes` argument

``` r
gg1d(
  df,
  col_id = "ID",
  col_sort = "Glasses",
  palettes = list("EyeColour" = c(
    Brown = "rosybrown4",
    Blue = "steelblue",
    Green = "seagreen"
  )),
  interactive = FALSE,
  verbose = FALSE,
  options = gg1d_options(legend_nrow = 2)
)
```

<img src="man/figures/README-customise_colours-1.png" width="100%" />

## Community Contributions

All types of contributions are encouraged and valued. See our [guide to
community
contributions](https://selkamand.github.io/gg1d/CONTRIBUTING.html) for
different ways to help.
