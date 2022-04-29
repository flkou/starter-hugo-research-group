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

  * Equating is NOT trying to find common metrics.
* **Operationalization**: To find a function y = f(x), transforming test score x from one test to score y from another test.

  * Turning x into standardized $z\_{x}$, which we assume to be the same as $z\_{y}$, then transforming $z_{y}$ to y.
  * Y = $(\frac{σ\_{y}}{σ\_{x}})*(x-{μ\_{X}})+{μ\_{y}}$

    * In comparison, regression function is Y = ${r\_{xy}}\*(\frac{σ\_{y}}{σ\_{x}})\*(x-{μ\_{X}})+{μ_{y}}$
    * Why is there a difference of ${r_{xy}}$?

      * Note that data is paired in Design B (thus allowing for regression analysis), whike data from Design A is not.
* "**Experimental design**"to determine the function y = f(x).

  * Design A: Randomly assign subjects to two forms.
  * Design B: All subjects tested on two form, with counterbalance.