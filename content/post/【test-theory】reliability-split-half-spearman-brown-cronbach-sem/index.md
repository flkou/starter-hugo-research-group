---
title: "【Test Theory】Reliability: Split-Half, Spearman-Brown, Cronbach, & SEM"
date: 2022-03-01T08:15:34.057Z
draft: false
featured: false
tags:
  - Test Theory
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
### Split-Half Reliability

* two halves may not be parallel
* coefficient depends on the grouping of items

### Spearman-Brown

* shorter tests are generally less reliable
* formula: $\frac{nr}{1+(n-1)r}$, $\frac{2r}{1+r}$ when n = 2 (i.e., split-half)

### Cronbach’s Alpha (or tau-equivalent reliability)

* mean of all possible split-half coefficients, corrected by Spearman-Brown
* correlation coefficients between split-halves = reliability coefficient = $\frac{σ\_{T}^2}{σ\_{X}^2}$
* formula: ($\frac{N}{N-1}$)(1-$\frac{Σσ\_{i}^2}{σ\_{X}^2}$) = ($\frac{N}{N-1}$)($\frac{σ\_{X}^2-Σσ\_{i}^2}{σ_{X}^2}$)

  * number of items: N
  * vairance of item i: $Σσ_{i}^2$
  * variance of total scores: $σ_{X}^2$
* alternative formula (Cho, [2016](https://doi.org/10.1177/1094428116656239), p. 13): $\frac{N^{2}\frac{ΣΣσ\_{i, j}}{N(N-1)}}{σ\_{X}^2}$ = ($\frac{N}{N-1}$)($\frac{ΣΣσ\_{i, j}}{σ\_{X}^2}$) = $\frac{σ\_{T}^2}{σ\_{X}^2}$ (i≠j)

  * $σ\_{X}^2$ = Σσ\_{i}^2 + ΣΣσ_{i, j}
  * variance explained by inter-item covariance is $σ_{T}^2$
  * variance not explained by inter-item covariance, which is $Σ(σ\_{i}^2-\frac{ΣΣσ\_{i, j}}{N(N-1)})$, is $σ_{e}^2$
* Cronbach's alpha is derived under the assumption of tau-equivalence

$\frac{}{}$

σ^2