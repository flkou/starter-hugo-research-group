---
title: 【Statistical Learning】What is Statistical Learning?
date: 2022-03-07T07:54:11.857Z
summary: ""
draft: false
featured: false
tags:
  - Statistical Learning
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
* **Y = f(X) + ϵ**

  * statistical learning = estimating f()

    * prediction
    * inference
* **$E(Y − \hat{Y} )^2$ = $E\[f(X) + ϵ − \hat{f}(X)]^2$ = $\[f(X) − \hat{f}(X)]^2 + Var(ϵ)$**

  * reducible error & irreducible error
* **Parametric Methods**

  * make assumption about the functional form of f, then fit or train the model
  * model flexibility & overfitting
* **Nonparametric Methods**

  * do not make explicit assumptions about the functional form of f
  * since the estimation is not reduced to a small set of parameters, large number of observations is required
  * example: thin-plate spline
* **Trade-off between flexibility and interpretability**
* **Supervised Versus Unsupervised Learning**

  * supervised: observations (x) with associated response measurement (y)

    * e.g., regression
  * unsupervised: observations (x) w/o associated response measurement (y)

    * e.g., cluster analysis
  * semi-supervised: when some x have associated y, and others don't
* **Regression Versus Classification**

  *