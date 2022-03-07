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

  * quantitative vs. categorical response
  * some methods can be used for both, e.g., K-NN & boosting
* **Assessing Model Accuracy**

  * a common measure: mean squared error (MSE)

    * MSE = $\frac{1}{n}Σ(yᵢ-\hat{f}(xᵢ))^2$
    * goal: minimal test MSE, rather than training MSE
    * overfitting: too flexible model resulting in larger test MSE
* **Bias-Variance Trade-Off**

  * MSE = $E\[y − \hat{f}(X)]^2$ = $Var(\hat{f}(x))+\[Bias(\hat{f}(x))]^2+Var(ϵ)$
  * variance: how much $\hat{f}(x)$ would change when different training data is used
  * bias: error when model is applied to real-life problems
  * generally, more flexible methods result in less bias & more variance
  * mathematical [derivation](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff#Derivation) for the trade-off relationship
* **In the Classification Setting**

  * error rate: $\frac{1}{n}Σ(yᵢ≠\hat{yᵢ})$
  * Bayes classifier "assigns each observation to the most likely class,  given its predictor values"

    * Bayes decision boundary
    * Bayes error rate = 1 - E(MaxP(Y = j|X))

      * analogous to  the irreducible error
    * Bayes classifier is not possible in real world
  * K-nearest neighbors (KNN) classifier:

    * maximizes P(Y = j|X = x) = $\frac{1}{K}Σ(I(yᵢ = j))$
    * $\frac{1}{K}$ corresponds to model flexibility

      * low K: low bias but high variance
      * high K: low-variance but high-bias