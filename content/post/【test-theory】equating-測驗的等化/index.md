---
title: 【Test Theory】Equating (測驗的等化)
date: 2022-04-29T01:12:39.564Z
draft: false
featured: false
tags:
  - Test Theory
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
* **Purpose**: Comparing scores from different forms of an exam.

  * Equating is NOT trying to find common metrics. It's trying to equate scores from different metrics.
* **Operationalization**: To find a function y = f(x), transforming test score x from one test to score y from another test.

  * Turning x into standardized $z\_{x}$, which we assume to be the same as $z\_{y}$, then transforming $z_{y}$ to y.
  * Y = $(\frac{σ\_{y}}{σ\_{x}})*(x-{μ\_{X}})+{μ\_{y}}$

    * In comparison, regression function is Y = ${r\_{xy}}\*(\frac{σ\_{y}}{σ\_{x}})\*(x-{μ\_{X}})+{μ_{y}}$
    * Why is there a difference of ${r_{xy}}$?

      * Note that data is paired in Design B (thus allowing for regression analysis), whike data from Design A is not.
      * ${r\_{xy}}$ is a manifest of "regression toward the mean". The "predicted y" will have a smaller variance (by ${r\_{xy}^2}$), thus harder to score high and low, leading to a concern of fairness.
* "**Experimental design**"to determine the function y = f(x).

  * Design A: Randomly assign subjects to two forms.
  * Design B: All subjects tested on two form, with counterbalance.
  * Design C: Subjects assigned to two forms (i.e., x & y) nonrandomly, while all subjects are subjected to a second common test (i.e., z). The common test score is used to equate the scores on two forms.
* In **Design C**:

  * ${z\_{x|z}}$ and ${z\_{y|z}}$ are assumed to be the same, and used for euqating.
  * Restriction of range may be present. ${r\_{xz}}$ and ${r\_{yz}}$ are influenced. However, regression coefficients can be used.
  * Assumption: X-Z & Y-Z relationships the same in subpopulations & total population.
  * The exact formula can be found in Angoff's (1971) writing, or Crocker & Algina's (1986) book.
* All mentioned above are "linear equating". What's the shortcomings of this method, as compared to "(equi)percentile equating"?
* How and when are designs A, B, C used in real world settings?
* Note: all symbols above should have been written as estimates (in samples), rather than parameters.

Angoff, W. H. (1971). Scales, norms, and equivalent scores. In RL Thorndike (Ed.), *Educational measurement*. American council on education.\
Crocker, L., & Algina, J. (1986). Equating scores from different different tests. In  *Introduction to classical and modern test theory*. Holt, Rinehart and Winston.