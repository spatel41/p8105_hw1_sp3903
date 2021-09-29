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

    ## [1] -0.08603134

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

  - The mean for the variables x and vec\_logical run without errors
    because they are numeric.
  - The mean for the variables vec\_char and vec\_factor do not work
    because they are character variables.

## Converting charactor and factor variables to numeric

``` r
as.numeric(pull(data_frame, vec_char))
as.numeric(pull(data_frame, vec_factor))
```

When converting the vec\_char variable to numeric, there is a NA’s
introduced by coercion warning message. When converting the vec\_factor
to numeric, R produces a mean by adding values to each of the three
factors. This provides context as to how R converts factors into numeric
values.

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
  - The range of flipper length is (172, 231) mm.
  - The mean flipper length is 200.9152047 mm.
  - The variance of the flipper length is 197.7317916
mm.

## Scatterplot

``` r
ggplot(penguins, aes(x = bill_length_mm, y = flipper_length_mm, color = species)) + geom_point()
```

    ## Warning: Removed 2 rows containing missing values (geom_point).

![](template-copy_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

    ## Warning: Removed 2 rows containing missing values (geom_point).

This scatterplot displays the flipper length in mm by the bill length in
mm. The colors indicate the species of penguins.
