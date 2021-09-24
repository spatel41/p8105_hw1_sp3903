p8105\_hw1\_sp3903
================

# Problem 1

## Creating a dataframe

### Loading tidyverse

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

### Creating a dataframe

``` r
data_frame = tibble(
  x = rnorm(10),
  vec_logical = x > 0,
  vec_char = c("a","b","c","d","e","f","g","h","i","j"),
  vec_factor = factor(c("low","moderate","high","low","moderate","high","low","moderate","high","low"))
)
```

### Finding the means

``` r
library(tidyverse)
mean(pull(data_frame, x))
```

    ## [1] 0.05408967

``` r
mean(pull(data_frame, vec_logical))
```

    ## [1] 0.4

``` r
mean(pull(data_frame, vec_char))
```

    ## Warning in mean.default(pull(data_frame, vec_char)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
mean(pull(data_frame, vec_factor))
```

    ## Warning in mean.default(pull(data_frame, vec_factor)): argument is not numeric
    ## or logical: returning NA

    ## [1] NA

## Means descriptions

  - The mean for the variables x and vec\_logical work because they are
    numeric.
  - The mean for the variables vec\_char and vec\_factor do not work
    because they are character variables.

## Converting charactor and factor variables to numeric

``` r
as.numeric(pull(data_frame, vec_char))
as.numeric(pull(data_frame, vec_factor))
```

# Problem 2

### Loading Package

``` r
data("penguins", package = "palmerpenguins")
```

### Dataset description

  - The data in this dataset include the following variables: species,
    island, bill\_length\_mm, bill\_depth\_mm, flipper\_length\_mm,
    body\_mass\_g, sex, year.
  - The size of the dataset 344 rows and 8 columns.
  - The mean flipper length is 200.9152047
mm.

## Scatterplot

``` r
ggplot(penguins, aes(x = bill_length_mm, y = flipper_length_mm, color=species)) + geom_point()
```

    ## Warning: Removed 2 rows containing missing values (geom_point).

![](template-copy_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

    ## Warning: Removed 2 rows containing missing values (geom_point).
