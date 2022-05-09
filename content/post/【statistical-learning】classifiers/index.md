---
title: 【Statistical Learning】Classifiers
date: 2022-05-09T12:59:53.956Z
draft: false
featured: false
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---


```r
# Ref: An Introduction to Statistical Learning (2e)
# Goal is to use Lag1 and Lag2 to predict Direction
library(ISLR2) # Dataset Smarket is from this package
dta.Train <- Smarket[Smarket$Year<2005, ]
dta.Test <- Smarket[Smarket$Year==2005, ]

# Logistic Regression
glm.fits <- glm(
  Direction~Lag1+Lag2,
  data = dta.Train, family = binomial)
summary(glm.fits)
glm.probs <- predict(glm.fits, dta.Test, type = "response") # Making prediction using Smarket
plot(density(glm.probs))
glm.pred <- rep("Down", length(glm.probs)); glm.pred[glm.probs > .5] = "Up" # Possibility to prediction
table(glm.pred, dta.Test$Direction) # Confusion matrix
mean(glm.pred == dta.Test$Direction) # Accuracy = 48% (slightly worse than random guessing)
pROC::roc(dta.Test$Direction ~ glm.probs, plot = TRUE, print.auc = TRUE) # AUC = .520
epicalc::lroc(glm.fits)

# Linear Discriminant Analysis
print(lda.fit <- MASS::lda(Direction~Lag1+Lag2, data = dta.Train))
lda.pred <- predict(lda.fit, dta.Test) # class is the prediction; x is the discriminant
plot(ifelse(lda.pred$class=="Down", 0, 1)~lda.pred$x)
plot(lda.pred$posterior[,2]~lda.pred$x) # x, the linear discriminant
table(lda.pred$class, dta.Test$Direction)
mean(lda.pred$class == dta.Test$Direction) # Accuracy = 55%
table(lda.pred$class)
sum(lda.pred$posterior[, 1] >= .5); sum(lda.pred$posterior[, 1] <= .5) # The default threshold
sum(lda.pred$posterior[, 1] >= .51); sum(lda.pred$posterior[, 1] <= .51) # A new threshold
pROC::roc(dta.Test$Direction ~ lda.pred$posterior[,1], plot = TRUE, print.auc = TRUE) # AUC = .558

# Quadratic Discriminant Analysis
print(qda.fit <- MASS::qda(Direction~Lag1+Lag2, data = dta.Train))
qda.pred <- predict(qda.fit, dta.Test)
mean(qda.pred$class == dta.Test$Direction) # Accuracy = 59%
pROC::roc(dta.Test$Direction ~ qda.pred$posterior[,1], plot = TRUE, print.auc = TRUE) # AUC = .562

# Naive Bayes Classifier
print(nb.fit <- e1071::naiveBayes(Direction~Lag1+Lag2, data = dta.Train))
nb.class <- predict(nb.fit, dta.Test)
nb.pred <- predict(nb.fit, dta.Test, type = "raw")
mean(nb.class == dta.Test$Direction) # Accuracy = 59%
pROC::roc(dta.Test$Direction ~ nb.pred[,1], plot = TRUE, print.auc = TRUE) # AUC = .563

# K-Nearest Neighbors (KNN)
train.X <- cbind(dta.Train$Lag1, dta.Train$Lag2)
test.X <- cbind(dta.Test$Lag1, dta.Test$Lag2)
set.seed(1) # For reproducibility
knn.pred <- class::knn(train.X, test.X, dta.Train$Direction, k = 3, prob=TRUE)
table(knn.pred, dta.Test$Direction)
mean(knn.pred == dta.Test$Direction) # Accuracy = 53%
knn.prob <- attr(knn.pred, "prob")
knn.prob <- 2*ifelse(knn.pred == "Down", 1-knn.prob, knn.prob) - 1
pROC::roc(dta.Test$Direction ~ knn.prob, plot = TRUE, print.auc = TRUE) # AUC = .529
```