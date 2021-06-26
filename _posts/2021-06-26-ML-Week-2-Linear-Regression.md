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




