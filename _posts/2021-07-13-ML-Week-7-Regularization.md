---
title: "ML Week 7 Regularization"
date: 2021-07-13
categories: Regularization
---
**7.1 Solving the Problem of Overfitting**\
Algorithm doesn't fit the training sample\
=> underfitting\
=> algorithm has strong preconception/high bias: goes biasedly neglecting the data\
\
If we carelessly add more polynomial terms, the algorithm has high variance i.e. *overfitting*\
Overfitting: if we have too many features, the learned hypothesis may fit the training set very well, but fail to generalize to new examples\
\
How to solve overfitting?\
&nbsp; 1. reduce number of features
&nbsp; &nbsp; &nbsp; - manually select which features to keep\
&nbsp; &nbsp; &nbsp; - model selection algorithm \
&nbsp; &nbsp; &nbsp; side effect: throws away useful info\
&nbsp; 2. regularization\
&nbsp; &nbsp; &nbsp; - keep all the features, but reduce magnitude/values of parameters Θ\
&nbsp; &nbsp; &nbsp; - works well when we have a lot of featrues, each of which contributes a bit to predicting y\
\
\
**7.2 
