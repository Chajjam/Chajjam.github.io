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
