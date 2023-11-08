
<!-- README.md is generated from README.Rmd. Please edit that file -->

# countmissing

<!-- badges: start -->
<!-- badges: end -->

The goal of countsallmissing is to create a new data frame that
summarizes the number of missing values for all columns in a given data
set “data” per level of column “group”. This provides a high level
overview of the data set.

## Installation

You can install the development version of countmissing like so:

``` r
# install.packages("devtools")
devtools::install_github("https://github.com/stat545ubc-2023/assignment-b2-cynthiaachung/tree/main", ref = "0.1.0")
```

## Usage

This example computes the number of missing values in the `airquality`
dataset grouped by the `cyl` column.

``` r
library(countmissing)
count_all_missing_by_group(airquality, Month)
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```

This example has the same output as the last example, but shows off an
alternative way of invoking the `count_all_missing_by_group()`: piping
the dataset into the function.

``` r
airquality |> count_all_missing_by_group(Month) 
#> # A tibble: 5 × 6
#>   Month Ozone Solar.R  Wind  Temp   Day
#>   <int> <int>   <int> <int> <int> <int>
#> 1     5     5       4     0     0     0
#> 2     6    21       0     0     0     0
#> 3     7     5       0     0     0     0
#> 4     8     5       3     0     0     0
#> 5     9     1       0     0     0     0
```
