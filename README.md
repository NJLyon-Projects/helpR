
<!-- README.md is generated from README.Rmd. Please edit that file -->

<img src = "inst/images/helpR_hex.png" align = "right" width = "15%"/>

# `helpR`

<!-- badges: start -->

[![R-CMD-check](https://github.com/njlyon0/helpR/workflows/R-CMD-check/badge.svg)](https://github.com/njlyon0/helpR/actions)
<!-- badges: end -->

`helpR` is an R package where the only unifying theme of the functions
is honestly just that I wrote them. That said, there are some useful
functions for **data wrangling** and **plotting** in particular though
functions for other purposes are also included. I’ll add functions to
this package as I write more orphan scripts that I hope others might
find useful so stay tuned!

## Installation

You can install the development version of helpeR from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("njlyon0/helpR")
```

## Current `helpR` Functions

-   **`num_chk`**: Checks a column that *should* contain only
    **numeric** values for any entries that would be coerced to NA if
    `as.numeric` is run

    -   An extension of this function is **`multi_num_chk`** that
        accepts a vector of columns to check at the same time

-   **`date_chk`**: Checks a column that *should* contain only **date**
    values for any entries that would be coerced to NA if `as.Date` is
    run

    -   An extension of this function is **`multi_date_chk`** that
        accepts a vector of columns to check at the same time

-   **`date_format_guess`**: Checks a column containing multiple
    ambiguous date formats and identifies its best guess for the format
    each date is in (e.g., ‘dd/mm/yyyy’ versus ‘yyyy/dd/mm’, etc.)

-   **`diff_chk`**: Compares two vectors and identifies what elements
    are found in the first but not the second (i.e., *lost* components)
    and what elements are found in the second but not the first (i.e.,
    *gained* components)

    -   This use-case is more oblique but I find it useful when I’m
        checking which columns are in the data before versus after a
        significant wrangling step to make sure no columns are
        lost/gained unexpectedly

-   **`nms_ord`**: Creates a Non-Metric Multi-Dimensional Scaling (NMS)
    ordination with base R. Requires the disimilarity matrix returned by
    `vegan::metaMDS`

-   **`pcoa_ord`**: Creates a Principal Coordinates Analysis (PCoA)
    ordination with base R. Requires the distance matrix returned by
    `ape::pcoa`

-   **`read_edi`**: Reads in data tables and metadata of a data package
    hosted by the Environmental Data Initiative (EDI) based on the PASTA
    identifier

-   **`rmd_export`**: Allows knitting of a specified R Markdown file
    locally and simultaneously to a specified Google Drive folder.
    *NOTE:* you must authorize R to work with Google Drive by using
    `googldrive::drive_auth` for this function to work

-   **`array_melt`**: “Flattens” an array of dimensions X, Y, and Z into
    a dataframe containing columns `x`, `y`, `z`, and `value` where
    `value` is whatever was stored in the array at those coordinates

## Looking Ahead

More functions are likely to be developed and housed within this package
but I find myself using these perennially for quick wrangling checks and
exploratory graphing respectively so it seemed worthwhile to pivot these
into a true package.

Feel free to post ideas for future functions as [an
issue](https://github.com/njlyon0/helpR/issues) on this repository and
I’ll do my best to build them!
