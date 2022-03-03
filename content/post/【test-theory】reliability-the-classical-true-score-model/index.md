---
title: "【Test theory】Reliability: the Classical True Score Model"
date: 2022-03-03T08:52:34.925Z
draft: false
featured: false
tags:
  - Test Theory
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
**Reliability**: “Degree of Consistency”

**Classical Test Theory** (Spearman, 1904):

* X = T + e

  * Tᵢ = E(Xᵢ) for person i

    * Xᵢ is a random variable with expected value of Tᵢ
  * eᵢ = Xᵢ - Tᵢ for person i

    * E(eᵢ) = 0 since E(Xᵢ) = Tᵢ
* Assumptions (at the populational level):

  * (unsystematic) measurement errors are random
  * mean error of measurement is zero
  * true scores & errors are uncorrelated
  * errors on different tests are uncorrelated
* $σ\_{X}^2 = σ\_{T}^2 + σ_{e}^2$
* Reliabliity index = $\frac{σ\_{T}}{σ\_{X}}$

  * is the correlation coefficient between X and T
  * cor(X,T) = $\frac{Σ(X{i}-μX)(T{i}-μT)}{Nσ\_{X}σ\_{T}}$ = $\frac{Σ(T{i}-μT)^2}{Nσ\_{X}σ\_{T}}$ + $\frac{Σ(T{i}-μT)(e{i}-μe)}{Nσ\_{X}σ\_{T}}$ = $\frac{σ\_{T}^2}{σ\_{X}σ\_{T}}$ = $\frac{σ\_{T}}{σ_{X}}$\
    (substituting X for T+e)
  * reliabliity index = $\sqrt{reliability \ coefficient}$
* Reliability coefficient = $\frac{σ\_{T}^2}{σ\_{X}^2}$

  * is the correlation between scores on parallel tests
  * parallel tests:

    * same true score for all examinee on all items (& thus on both tests)
    * error variance equal for the two forms
  * reliability coefficient = (reliabliity index)^2
* cor(X, T) > cor(scores on parallel tests)