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
**7.2 Cost Function**\
Penalize the contributions of unnecessary terms by adding 1000Θ<sub>j</sub><sup>2</sup> to cost function\
\
Small values for parameters\
&nbsp; - "Simpler" hypothesis\
&nbsp; - Less prone to ovefitting\
\
Regularization term with regularization parameter λ\
J(Θ) = (1/2m)[∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>-y<sup>(i)</sup>)<sup>2</sup> + **λ∑<sup>n</sup><sub>j=1</sub>Θ<sub>j</sub><sup>2</sup>**]\
&nbsp; *note: we start from j=1 due to convention; including j=0 doesn't really make big change though*\
\
First goal: fit the training set well\
Second goal: keep parameters small\
Regularization works to find the most adequate outcome\
\
If λ is set very large, parameters are penalized and everything is close to 0.\
=> h<sub>Θ</sub>(x) = Θ<sub>0</sub>\
\
\
**7.3 Regularized Linear Regression**\
Gradient descent with regularization:\
Repeat {\
&nbsp; Θ<sub>0</sub> := Θ<sub>0</sub> - α(1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sub>0</sub><sup>(i)</sup>\
&nbsp; Θ<sub>j</sub> := Θ<sub>j</sub> - α{(1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sub>j</sub><sup>(i)</sup> + (λ/m)Θ<sub>j</sub>} (j=1,2,3,...,n)\
&nbsp; Θ<sub>j</sub> := Θ<sub>j</sub>(1-α(λ/m))-α(1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sub>j</sub><sup>(i)</sup>\
&nbsp; }\
(1-α(λ/m)) is slightly less than 1, so as a result, Θ<sub>j</sub> becomes smaller.\
\
Normal equation
Θ = (X<sup>T</sup>X + λ[a matrix that is made by replacing the first element of identity matrix with 0])<sup>-1</sup>X<sup>T</sup>y\
If λ>0, it is proved that the matrix inside the parentheses is always invertible.\
\
\
**7.4 Regularized Logistic Regression**\
Cost function for logistic regression:\
original J(Θ) + (λ/2m)∑<sup>n</sup><sub>j=1</sub>Θ<sub>j</sub><sup>2</sup>\
Same modification for gradient descent\
\



