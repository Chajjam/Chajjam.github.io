---
title: "ML Lecture 10 Advice for Applying Machine Learning"
date: 2021-07-16
categories: Machine_Learning
---
**10.1 Deciding What to Try Next**\
Debugging a learning algorithm:
Suppose you have implemented regularized linear regression to predict housing prices.\
However, when you test your hypothesis on a new set of houses, you find that it makes unacceptably large errors in its predictions.\
What should you try next?\
&nbsp;- get more training examples (sometimes doesn't help)\
&nbsp;- try smaller sets of features to prevent overfitting\
&nbsp;- try getting additional features\
&nbsp;- try adding polynomial feataures (x<sub>1</sub><sup>2</sup>,x<sub>2</sub><sup>2</sup>, x<sub>1</sub>x<sub>2</sub>,etc.)\
&nbsp;- try increasing/decreasing λ\
&nbsp;=> It is not a good idea to randomly pick one of these\
\
Machine learning diagnostic:\
A test that you can run to gain insight what is/isn't working with a learning algorithm, and gain guidance as to how best to improve its performance.\
\
\
**10.2 Evaluating a hypothesis**\
How to tell overfitting?\
=> low error in train set, high error in test set\
\
Misclassification error (0/1 misclassification error):\
err(h<sub>Θ</sub>(x),y) = 1 if (h<sub>Θ</sub>(x)≥0.5 && y=0) or (h<sub>Θ</sub>(x)<0.5 && y=1) / 0 otherwise\
Test Error = (1/m<sub>test</sub>)∑<sup>m<sub>test</sub></sup><sub>i=1</sub>err(h<sub>Θ</sub>(x<sub>test</sub><sup>(i)</sup>),y<sub>test</sub><sup>(i)</sup>)\
\
\
**10.3 Model Selection and Train/Validation/Test Sets**\
Model selection\
d = degree of polynomial\
Among several different degrees of polynomial, we can choose the least error one.\
Then, how well does the model generalize?
Measuring error J<sub>test</sub>(Θ<sup>(5)</sup>)\
Problem: J<sub>test</sub>(Θ<sup>(5)</sup>) is likely to be an optimistic estimate of generalization error. \
=> split into [60% training set], [20% cross validation set (CV)], [20% test set]\
=> test hypothesis from test set to cross validation set\
\
&nbsp;1. optimize the parameters using the training set for each polynomial degree\
&nbsp;2. find the polynomial degree d with the least error using cv set\
&nbsp;3. estimate the generalization error using the test set\
\
\
**10.4 Diagnosing Bias vs. Variance**\
High bias (underfit): both J<sub>cv</sub> and J<sub>test</sub> are high\
High variance (overfit): J<sub>cv</sub> is high and J<sub>test</sub> is low\
\
\
**10.5 Regularization and Bias/Variance**\
large λ: high bias (underfit)\
intermediate λ: just right\ 
small λ: high variance (overfit)\
\
Set λ 0, 0.01, 0.02, 0.04, 0.08 ... 10 (ex)\
=> find parameters
=> compute CV error
=> see how well does it fit to test set
\
\
**10.6 Learning Curves**\
If training set is small, train error is small, but CV error is big.\
\
High bias: train error and CV error meets at high error\
=> getting more training data is not helpful\
\
High variance: large gap between train error and CV error
=> getting more training data is likely to help\
\
\
**10.7 Deciding What to Do Next Revisited**\
&nbsp;- get more training examples => *fixes high variance*\
&nbsp;- try smaller sets of features to prevent overfitting => *fixes high variance*\
&nbsp;- try getting additional features => *fixes high bias*\
&nbsp;- try adding polynomial feataures (x<sub>1</sub><sup>2</sup>,x<sub>2</sub><sup>2</sup>, x<sub>1</sub>x<sub>2</sub>,etc.) => *fixes high bias*\
&nbsp;- try decreasing λ => *fixes high bias*\
&nbsp;- try increasing λ => *fixes high variance*\
\
Neural networks and overfitting\
"small" neural networks: fewer parameters, more prone to underfitting, computationally cheaper\
"large" neural networks: more parameters, more prone to overfitting, computationally more expensive, use regularization to address overfitting\
\
using a single hidden layer is default, but try with train/CV/test sets if needed
