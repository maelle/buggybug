
# buggybug

<!-- badges: start -->
<!-- badges: end -->

The goal of buggybug is to explore https://github.com/r-lib/pkgdown/issues/2145

``` r
library(rsample)
library(mlbench)
data(LetterRecognition)
lobstr::obj_size(LetterRecognition)
#> 2,644,640 B
set.seed(35222)
boots <- bootstraps(LetterRecognition, times = 50)
lobstr::obj_size(boots)
#> 6,686,776 B
# Object size per resample
lobstr::obj_size(boots)/nrow(boots)
#> 133,735.5 B
# Fold increase is <<< 50
as.numeric(lobstr::obj_size(boots)/lobstr::obj_size(LetterRecognition))
#> [1] 2.528426
```
