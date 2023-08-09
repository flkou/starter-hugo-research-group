---
title: Centering Options in Multilevel Models
date: 2023-08-09T14:33:48.595Z
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
* When the focus is a level-1 predictor, or interaction or higher order terms involving only level-1 variables (including the case of polynomial regression): Group-mean center the level-1 predictor. 

  * Rationale: to remove between-group variations. 
* When the focus is a level-2 predictor, or interaction or higher order terms involving only level-1 variables: Grand mean-center the level-2 predictor, and grand mean-center the level-1 covariates. 

  * Rationale: if the level-1 covariates are group-mean centered, it will become orthogonal with level-2 variables, thus not partialled out.
* For cross-level interaction: Group mean-center the level-1 predictor, and grand-mean center the level-2 predictor.

**R﻿eference**:

Enders, C. K., & Tofighi, D. (2007). Centering predictor variables in cross-sectional multilevel models: a new look at an old issue. Psychological methods, 12(2), 121.

Tsai, C. Y., Kim, J., Jin, F., Jun, M., Cheong, M., & Yammarino, F. J. (2022). Polynomial regression analysis and response surface methodology in leadership research. The Leadership Quarterly, 33(1), 101592.