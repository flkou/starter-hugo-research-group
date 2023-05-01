---
title: Mixed Effect Models in R
date: 2023-05-01T03:19:45.493Z
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
U﻿sing the lme4 package (lmerTest package to provide testing):

```r
library(lme4); library(lmerTest)

# Visualization
ggplot(data = dta, aes(x = X, y = Y, group = ID))+
stat_smooth(method = 'lm', se = F, color = 'lightgray') +
geom_point(size = 1) +
labs(x = 'X', y = 'Y', title = 'ID')

# ICC(1), ICC(2)
multilevel::ICC1(aov(X ~ ID, data=dta))
multilevel::ICC2(aov(X ~ ID, data=dta))
multilevel::rwg(dta$X, dta$ID,
                ranvar = (npoints*npoints-1)/12)

# Separate regressions for each group
lmList(Y ~ X | ID, data=dta)

# Group mean centering (CWC: centering within cluster)
misty::center(dta$X, type = "CWC", cluster = dta$ID)

# Mixed effect model
m0 <- lmer(Y ~ 1 + X + (1 + X | ID), data=dta)
summary(m0)

# Testing the signifance of random effect
m1 <- update(m0, . ~ . - ( 1 | ID ) )
anova(m0, m1)

# Diagnostics
qqmath(~ ranef(m0, condVar = T)$ID, type = c('p', 'g', 'r'),
       pch = '.',xlab = '常態分位數', ylab = '隨機效果分位數')
qqmath(~ resid(m0, scale = T), type = c('p', 'g', 'r'), pch = '.',
       xlab = '標準化常態分位數', ylab = '標準化殘差')
```

To add:  Pseudo R-squared, interaction plot, grand mean centering



\***What to do if the model does not converge?** Brauer & Curtin (2017) in their paper provided a "List of 20 Remedies That Can be Used to Achieve Convergence of LMEMs"

Brauer, M., & Curtin, J. J. (2018). [Linear mixed-effects models and the analysis of nonindependent data: A unified framework to analyze categorical and continuous independent variables that vary within-subjects and/or within-items](https://doi.org/10.1037/met0000159). Psychological Methods, 23(3), 389.