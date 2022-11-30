
<!-- README.md is generated from README.Rmd. Please edit that file -->

# wrapped

This package contains source code for reading your Music (as in, the
Apple Music app) listening data into a tidy data frame. I used the
output as a starting point for a Wrapped-like analysis of what I listen
to. :)

## Installation

You can install wrapped from
[GitHub](https://github.com/simonpcouch/wrapped) with:

``` r
# install.packages("devtools")
devtools::install_github("simonpcouch/wrapped")
```

## Usage

The package contains one function, `wrap_library()`, which takes a path
to an `.xml` file and a year, and outputs a tidy data frame.

``` r
wrap_library("Library.xml", 2022L)
```

The `.xml` file should be the output of navigating to:

    Music > File > Library > Export Library

It also contains a data frame, `wrapped`, which is the (slightly
modified) output of running this function on my own library:

``` r
library(wrapped)

wrapped
#> # A tibble: 594 × 8
#>       id track_title          artist      album genre date_added skip_…¹ play_…²
#>    <int> <chr>                <chr>       <chr> <chr> <date>       <dbl>   <dbl>
#>  1 11452 Bag Of You           Mahalia     Bag … R&B/… 2022-11-11       3     102
#>  2 11040 The Internet         Violet Ski… If I… Indi… 2022-08-04       2      87
#>  3 11041 Settle               Violet Ski… If I… Indi… 2022-08-04       2      87
#>  4 11170 Half My Life         Violet Ski… Lone… Pop   2022-09-08       4      80
#>  5 11317 The Problem Song     Valley      The … Indi… 2022-10-08      NA      79
#>  6 10976 WASTE TIME           Gwen Bunn   PHASE R&B/… 2022-07-21       3      74
#>  7 10899 Good Things          Ken Yates   Ceru… Sing… 2022-06-04       1      61
#>  8 11268 pennies (voice memo) Tiny Habits penn… Sing… 2022-10-01       1      51
#>  9 11169 When I Come Home     Violet Ski… Lone… Pop   2022-09-08       1      50
#> 10 10907 Small Doses          Ken Yates   Ceru… Sing… 2022-06-04      NA      49
#> # … with 584 more rows, and abbreviated variable names ¹​skip_count, ²​play_count
```
