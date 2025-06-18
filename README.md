# growthcurver: owen's version

This helpful package by [Kathleen Sprouffske](https://github.com/sprouffske/growthcurver) relies on the Cairo graphics library, which doesn't work for me.
All I've done is change the graphics device for the plotting part of the `SummarizeGrowthByPlate` function.
If you use this, don't forget to cite the [paper describing the original package](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-016-1016-7)!

To install this version, run the following code in R:
```R
devtools::install_github("owenfhale/growthcurver")
```

# growthcurver:

[![Travis-CI Build Status](https://travis-ci.org/sprouffske/growthcurver.svg?branch=master)](https://travis-ci.org/sprouffske/growthcurver)

Growthcurver is an R package that fits growth curve data to a standard form of the logistic equation common in ecology and evolution whose parameters (the growth rate, the initial population size, and the carrying capacity) provide meaningful population-level information with straight-forward biological interpretation. 

You can install the latest released version from CRAN from within R with
  ```R
  install.packages("growthcurver")
  ````

You can install the latest development version from github with
  ```R
  # install devtools first if you don't already have the package
  install.packages("devtools")

  # then install growthcurver
  devtools::install_github("sprouffske/growthcurver")
  ```

The paper describing Growthcurver is available [here](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-016-1016-7).

## Using growthcurver

The easiest way to get started with growthcurver is to work through the examples in the vignette. In the vignette, you can find information on

* What your input data should look like
* How to use growthcurver to get summary metrics on a single growth curve sample
* How to use growthcurver to get summary metrics on an entire plate of growth curves
* What those metrics mean and some best practices for quality control

You can find the vignette [here](https://CRAN.R-project.org/package=growthcurver/vignettes/Growthcurver-vignette.html).

## A simple working example

This code loads the `growthcurver` package and some sample data. Then, it calls `SummarizeGrowth` to do the analysis. 
```R
library(growthcurver)                    # load the package
d <- growthdata                          # load some sample, simulated data
gc_fit <- SummarizeGrowth(d$time, d$A1)  # do the analysis
plot(gc_fit)                             # plot your data and the best fit
gc_fit                                   # view some returned metrics
```


