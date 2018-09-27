
<!-- README.md is generated from README.Rmd. Please edit that file -->
lamme
=====

The goal of lamme is to implement log-analytic methods for testing and esitmating multiplicative effects.

Installation
------------

You can install lamme from github with:

``` r
# install.packages("devtools")
devtools::install_github("QMmmmLiu/lamme")
```

Example
-------

This is a basic example which shows you how to solve a common problem:

``` r
library(lamme)
data("schoene")
attach(schoene)
abc(post_HRT,group,pre_HRT)
#> $ancova
#> [1] 759.9898
#> 
#> $ancohet
#> [1] 761.6763
#> 
#> $`ancova-l`
#> [1] 746.6123
#> 
#> $lancova
#> [1] 743.1558
lanova(post_HRT,group)
#> 
#> Call:
#> lm(formula = (log(y) ~ factor(g)))
#> 
#> Residuals:
#>    Min     1Q Median     3Q    Max 
#> 0.7498 0.8936 0.9903 1.0931 1.5362 
#> 
#> Coefficients:
#>                       Estimate (log-scale) s.e.     t value    Pr(>|t|)
#> (Intercept)          2.471e+02        2.386e-02   2.309e+02  1.481e-113
#> factor(g)treatment   9.489e-01        3.439e-02  -1.526e+00   1.309e-01
#>                          2.5 %  97.5 %
#> (Intercept)          2.356e+02 259.122
#> factor(g)treatment   8.861e-01   1.016
#> 
#> Residual standard error: 0.1546 on 79 degrees of freedom
#> Multiple R-squared:  0.02864,    Adjusted R-squared:  0.01635 
#> F-statistic:  2.33 on 1 and 79 DF,  p-value: 0.1309
lancova(post_HRT,group,pre_HRT)
#> 
#> Call:
#> lm(formula = (log(y) ~ log(x) + factor(g)))
#> 
#> Residuals:
#>    Min     1Q Median     3Q    Max 
#> 0.7474 0.9404 0.9858 1.0541 1.3438 
#> 
#> Coefficients:
#>                      Estimate (log-scale) s.e.    t value   Pr(>|t|)
#> (Intercept)         4.056e+00        3.631e-01  3.856e+00  2.353e-04
#> x                   7.400e-01        6.533e-02  1.133e+01  3.811e-18
#> factor(g)treatment  9.563e-01        2.129e-02 -2.098e+00  3.919e-02
#>                         2.5 % 97.5 %
#> (Intercept)         1.969e+00  8.358
#> x                   6.099e-01  0.870
#> factor(g)treatment  9.166e-01  0.998
#> 
#> Residual standard error: 0.09569 on 78 degrees of freedom
#> Multiple R-squared:  0.6327, Adjusted R-squared:  0.6233 
#> F-statistic: 67.19 on 2 and 78 DF,  p-value: < 2.2e-16
```

For detailed illustration, use `vignettes("lamme-vignette")`.
