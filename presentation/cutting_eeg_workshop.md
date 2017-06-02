Analysing EEG data in R
========================================================
author: Matt Craddock
date: 19 June 2017
autosize: true

About R
===
<p>
Free
Massive community
</p>

What you can and can't do
===

## Can
- Every statistic you can think of
- 
***
## Can't
- Most signal processing
- Source-analysis
- Time-frequency analysis

RStudio
===

Integrated development environment!
- Package manager
- Projects
- Notebooks
- Github integration

How to import data
===
From Matlab 
- .mat and .set files are HDF5 format.
- can be read directly
- a bit cumbersome, may be easier to convert to csv

From Python
- csv
- feather

The Tidyverse
===

Set of integrated packages
- ggplot2
- dplyr
- purr
- pipes


Data frames
========================================================


```r
head(iris)
```

```
  Sepal.Length Sepal.Width Petal.Length Petal.Width Species
1          5.1         3.5          1.4         0.2  setosa
2          4.9         3.0          1.4         0.2  setosa
3          4.7         3.2          1.3         0.2  setosa
4          4.6         3.1          1.5         0.2  setosa
5          5.0         3.6          1.4         0.2  setosa
6          5.4         3.9          1.7         0.4  setosa
```
Converting between wide and long format
===
Spread() and gather()

Nested data frames
===

How to select data
===

Plotting
===

# ggplot2()

Mixed-effects modelling
===

Frequentist approach
- Linear mixed-effects models
-- lme4

Bayesian
- brms/rstanarm/Stan

lme4 syntax
===

dv ~ fixed_effects + (random_slopes|random_effecta)
dv ~ iv1 + (1 + iv1|id)
dv ~ iv1 + iv2 + iv1:iv2 + (iv1 + iv2 + iv1:iv2|id)
dv ~ iv1*iv2 + (iv1*iv2|id)

Can have multiple random effects
dv ~ iv1*iv2 + (iv1*iv2|Sub_id) + (iv1*iv2|object)

Mass Univariate Statistics
===


```r
library(purrr)
```

Machine learning
===

Caret

