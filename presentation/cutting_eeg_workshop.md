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

Packages
===
Packages are the way you add features to R. As of today, there are 10754 packages available on the CRAN central repository that cover a huge range of capabilites. Some packages are already installed; we'll download others as we go on.

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

dplyr
===

Piping %>%
===

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
Most statistics commands in R expect data to be *long* format - one observation per row.
spread() and gather() allow simple switching between formats.
tidyr

Summarizing data
===
1. Group data
2. Summarise data


Nested data frames
===
A useful concept from the tidyverse is the nested data frame. A column in a data frame can be a list, and a list can contain data frames. 







```
Error in nest(iris, -Species) : could not find function "nest"
```
