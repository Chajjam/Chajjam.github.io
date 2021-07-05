---
title: "ML Week 2 Linear Regression"
date: 2021-06-26
categories: Linear_Regression
---
**2.1 Linear Regression with One Variable: Model Representation**\
\
Notation:\
&nbsp; m = Number of training examples\
&nbsp; x = input variable/features\
&nbsp; y = output variable/target variable\
&nbsp; (x, y) = one training example\
&nbsp; (x<sup>(i)</sup>, y<sup>(i)</sup>) = ith training example\
\
Housing Prices example\
Training set\
&nbsp; 1 Size in feet^2 (x)\
&nbsp; 2 Price ($) in 1000's (y)\
\
Training set -(feed)-> Learning algorithm -> hypothesis(h)\
hypothesis: size of house(x) -> h -> estimated price(y)\
=> h maps from x's to y's\
\
How do we represent h?\
h<sub>Θ</sub>(x) = h(x) = Θ<sub>0</sub> + Θ<sub>1</sub>x\
=> predicting a straight line function\
=> Linear regression with one variable\
&nbsp; = Univariate linear regression\
\
\
**2.2 Cost Function**\
\
h<sub>Θ</sub>(x) = h(x) = Θ<sub>0</sub> + Θ<sub>1</sub>x\
&nbsp; Θ<sub>i's</sub>: parameters of the model\
We can choose many different parameters\
=> How to choose the best parameters?\
\
Idea: choose Θ<sub>0</sub>, Θ<sub>1</sub> so that h<sub>Θ</sub>(x) is close to y for our training examples (x,y)\
=> changing parameters, we need to minimize differences betwwen h(x) and y\
=> minimize (1/2m)∑<sub>i=1</sub><sup>m</sup>(h(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>\
&nbsp; m: size of training samples\
\
By convention, we define cost function as\
J(Θ<sub>0</sub>,Θ<sub>1</sub>) = (1/2m)∑<sub>i=1</sub><sup>m</sup>(h(x<sup>(i)</sup>) - y<sup>(i)</sup>)<sup>2</sup>\
= Squared Error Cost Function\
\
\
**2.3 Cost Function Intuition I**\
\
Simplifed Version\
Hypothesis: h<sub>Θ</sub>(x) = Θ<sub>1</sub>x\
Parameter: Θ<sub>1</sub>\
Cost Function: J(Θ<sub>1</sub>) = (1/2m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)<sup>2</sup>\
\
Goal: minimize J(Θ<sub>1</sub>)\
\
Hypothesis function: for fixed parameter, this is a function of x\
Cost function: function of the parameter\
\
\
**2.5 Gradient Descent**\
\
Outline: Start with some Θ<sub>0</sub>, Θ<sub>1</sub> and keep change them to reduce J(Θ<sub>0</sub>,Θ<sub>1</sub>) until we end up at a minimum\
\
Gradient descent algorithm:\
&nbsp; repeat until convergence {\
&nbsp; Θ<sub>j</sub> := Θ<sub>j</sub> - α((∂/∂Θ<sub>j</sub>)J(Θ<sub>0</sub>,Θ<sub>1</sub>) (for j=0 and j=1)\
&nbsp; }\
note that:\
&nbsp; := is assignment\
&nbsp; α is learning rate\
&nbsp; (∂/∂Θ<sub>j</sub>)J(Θ<sub>0</sub>,Θ<sub>1</sub>) is derivative term\
\
Simultaneous Update (o)\
&nbsp; temp0 assignment\
&nbsp; temp1 assignment\
&nbsp; => Θ<sub>0</sub> := temp0\
&nbsp; => Θ<sub>1</sub> := temp1\
\
Consecutive Update (x)\
&nbsp; temp0 assignment\
&nbsp; => Θ<sub>0</sub> := temp0\
&nbsp; temp1 assignment\
&nbsp; => Θ<sub>1</sub> := temp1\
&nbsp; in this case, Θ<sub>0</sub> changes so second assignment is not done according to the original purpose\
\
\
**2.6 Gradient Descent Intuition**\
\
α: if learning rate is too mall, gradient descent can be slow.\
&nbsp; &nbsp; if learning rate is too large, gradient descent can overshoot the minimum, thereby failing to converge or even diverge.\
\
\
**2.7 Gradient Descent for Linear Regression**\
\
(∂/∂Θ<sub>j</sub>)J(Θ<sub>0</sub>,Θ<sub>1</sub>)\
&nbsp; = (∂/∂Θ<sub>j</sub>)(1/2m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)<sup>2</sup>\
&nbsp; = (∂/∂Θ<sub>j</sub>)(1/2m)∑<sup>m</sup><sub>i=1</sub>(Θ<sub>0</sub>+Θ<sub>1</sub>x<sup>(i)</sup>-y<sup>(i)</sup>)<sup>2</sup>\
\
j=0: (1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)\
j=1: (1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sup>(i)</sup>\
\
Gradient descent is susceptible to local minimum.\
However, cost function for linear regression is always convex function.\
\
"Batch" Gradient Descent\
Batch: Each step of gradient descent uses all the training examples\
(∑<sup>m</sup><sub>i=1</sub>)\
\
\
**2.8 What's Next**\
\
Two extensions:
1. solve for parameters without needing iteratvie alogrithm (gradient descent)
2. learn with larger number of features




