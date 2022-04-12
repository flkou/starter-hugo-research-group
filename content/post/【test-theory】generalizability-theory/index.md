---
title: 【Test theory】Generalizability Theory
date: 2022-04-12T08:54:27.785Z
draft: false
featured: false
tags:
  - Test Theory
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
* **Universe** (of measurements): A set of extensive measurement conditions (e.g. different times, forms, or subscales)
* **Generalizability (G) study**: To assess the extent to which a sample of measurements generalizes to a universe of measurements.
* **Decision (D) study**: To use test score to make decisions.
* **Facet**: A set of measurement conditions. Similar to a factor in ANOVA.
* **Universe score**: average of measurements in the universe.
* **Generalizability coefficient**

  * Definition 1: universe score variance / expected observed score variance
  * Defenition 2: squared correlation between universe & observed scores
* **Estimation** of generalizability coefficient (in a G study):

  * Assuming that measurement conditions (e.g., raters) in both the G & D study is representative in the universe, thus the *average* observed score variance (across conditions) = the *expected* observed score variance.
  * Then, ANOVA can be used to partition variance into three sources:

    * $σ_{p}^2$: the variance of the examinees' universe scores
    * $σ_{i}^2$: the variance of the condition (e.g., rater) effect
    * $σ_{e}^2$: the variance of residual, including (intra-condition) measurement error *plus* the inter-condition disagreement

      * caution: this source of variance is present in all mean squares (MS). for instance, MS(P) = $σ\_{e}^2 + n\_{i}σ_{p}^2$
  * After variances have been partitioned, calculate generalizability coefficient = $\frac{σ_{p}^2}{*average* observed score variance}$

    * the formula of averageobserved score variance depends on the study design (e.g., number of facets, whether conditions are crossed and/or nested)