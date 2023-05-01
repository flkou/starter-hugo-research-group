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


```

N﻿ote: The current method does not provide pseudo R-squared