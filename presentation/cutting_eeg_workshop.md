Analysing EEG data in R
========================================================
author: Matt Craddock
date: 19 June 2017
autosize: true

About R
===

1. Free, open source
2. Massive community


RStudio
===

Integrated development environment!
- Package manager
- Projects
- Notebooks
- Github integration

Packages
===
Packages are the way you add features to R. As of today, there are 10754 packages available on the CRAN central repository that cover a huge range of capabilites. Some packages are already installed; we'll download others as we go on.

R Basics
===

- Vectors
- Lists
- Data frames
- Functions

Vectors
===

Lists
===

Data frames
===


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

Functions
===

Commands that perform some kind of operation, usually on some data that is passed to.

```
mean <- function(x) {
  mean(x)
}
```
Get help on any function using ?function_name.


Assign the output of functions to variables using the ```<-``` operator.


Assignment
===

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


```r
library(tidyverse)
```





ggplot2
===
![plot of chunk unnamed-chunk-2](cutting_eeg_workshop-figure/unnamed-chunk-2-1.png)

Piping %>%
===
Allows code to be read from left-to-right


```r
tmp_var <- iris
tmp_var$
```


```r
tmp_var <- iris %>%
  select(Petal.Length) 
```

Converting between wide and long format
===
Many statistics commands in R expect data to be *long* format - one observation per row.
spread() and gather() allow simple switching between formats.
tidyr

Summarizing data
===
1. Group data
2. Summarise data


Nested data frames
===
A useful concept from the tidyverse is the nested data frame. A column in a data frame can be a list, and a list can contain data frames. 


```r
nest(iris,-Species)
```

```
# A tibble: 3 x 2
     Species              data
      <fctr>            <list>
1     setosa <tibble [50 x 4]>
2 versicolor <tibble [50 x 4]>
3  virginica <tibble [50 x 4]>
```


How to select data
===

Mixed-effects modelling
===

Frequentist approach
- Linear mixed-effects models
-- lme4

Bayesian
- brms/rstanarm/Stan

lme4 syntax
===

* dv ~ fixed_effects + (random_slopes|random_effects)
* dv ~ iv1 + (1 + iv1|id)
* dv ~ iv1 + iv2 + iv1:iv2 + (iv1 + iv2 + iv1:iv2|id)
* dv ~ iv1*iv2 + (iv1*iv2|id)

Can have multiple random effects
* dv ~ iv1*iv2 + (iv1*iv2|Sub_id) + (iv1*iv2|object)

Mass Univariate Statistics
===


```r
library(purrr)
```

Machine learning
===

Caret

