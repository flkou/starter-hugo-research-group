---
title: Discriminant validity in SEM
date: 2022-03-14T13:28:20.918Z
draft: false
featured: false
tags:
  - Method
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
According to Fornell & Larcker ([1981](https://doi.org/10.1177/002224378101800104)), one way to evaluate discriminant validity in SEM is to compare the squared correlation between two constructs and their respective AVEs. The rationale is that the latent construct should explain more variance than the covariance between constructs.

```r
library(lavaan)
cfamodel <- ''
cfafit <- cfa(cfamodel, dta)
semTools::reliability(cfafit) # AVE
cor <- lavInspect(cfafit,"cor.lv")
round(cor^2,2) # squared correlation
```

In addition, we can estimate the 95% CI for each correlations between constructs, to see if they include 1.

```
summary(cfafit, ci=T)
```