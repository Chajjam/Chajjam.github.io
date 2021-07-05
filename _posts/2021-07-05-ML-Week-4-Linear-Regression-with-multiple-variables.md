---
title: "ML Week 4 Linear Regression with multiple variables"
date: 2021-07-05
categories: Linear_Regression
---
**4.1 Multiple Features**\
\
Notation:\
&nbsp; n: number of features\
&nbsp; x<sup>(i)</sup>: input(features) of ith training example\
&nbsp; x<sub>j</sub><sup>(i)</sup>: value of feature j in ith training example\
\
Hypothesis:\
&nbsp; x=[x<sub>0</sub> x<sub>1</sub> x<sub>2</sub> ... x<sub>n</sub>]<sup>T</sup>\
&nbsp; Θ=[Θ<sub>0</sub> Θ<sub>1</sub> Θ<sub>2</sub> ... Θ<sub>n</sub>]<sup>T</sup>\
\
&nbsp; h<sub>Θ</sub>(x) = Θ<sub>0</sub>x<sub>0</sub> + Θ<sub>1</sub>x<sub>1</sub> + Θ<sub>2</sub>x<sub>2</sub> + ... + Θ<sub>n</sub>x<sub>n</sub>\
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= Θ<sup>T</sup>x\
\
\
**4.2 Gradient Descent for Multiple Variables**\
\
Hypothesis: h<sub>Θ</sub>(x) = Θ<sup>T</sup>x\
Parameters: Θ\
Cost function: J(Θ)\
Gradient Descent:\
&nbsp; Repeat {\
&nbsp; &nbsp; &nbsp; Θ<sub>j</sub> := Θ<sub>j</sub> - α(∂/∂Θ<sub>j</sub>)J(Θ)\
&nbsp; } (simultaneously update for every j = 0, ..., n)\
\
New algorithm (n ≥ 1):\
&nbsp; Repeat {\
&nbsp; &nbsp; &nbsp; Θ<sub>j</sub> := Θ<sub>j</sub> - α(1/m)∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sub>j</sub><sup>(i)</sup> (simultaneously update Θ<sub>j</sub> for j = 0, ..., n)\
\
\
**4.3 Gradient in Practical Feature Scaling**\
\
Feature Scaling\
Idea: Make sure features are on a similar scale\
E.g. x<sub>1</sub> = size (0 - 2000 feet<sup>2</sup>)\
&nbsp; &nbsp; x<sub>2</sub> = number of bedrooms (1-5)\
&nbsp; &nbsp; x<sub>1</sub> = (size(feet<sup>2</sup>))/2000\
&nbsp; &nbsp; x<sub>2</sub> = (number of bedrooms)/5\
&nbsp; &nbsp; both between 0 and 1\
\
Feature scaling\
&nbsp; : Get every feature into approximately -1 ≤ x<sub>i</sub> ≤ 1 range\
&nbsp; 0 ≤ x<sub>1</sub> ≤ 3 (o)\
&nbsp; -2 ≤ x<sub>2</sub> ≤ 0.5 (o)\
&nbsp; -100 ≤ x<sub>3</sub> ≤ 100 (x)\
&nbsp; -0.0001 ≤ x<sub>4</sub> ≤ 0.0001 (x)\
&nbsp; doesn't need to be exactly same scale\
\
Mean normalization\
&nbsp; : Replace x<sub>i</sub> with x<sub>i</sub>-μ<sub>i</sub> to make features have approximately zero mean (Do not apply to x<sub>0</sub>=1)\
&nbsp; E.g. x1 = (size-1000)/2000 (when avg size is 1000)\
&nbsp; &nbsp; &nbsp; &nbsp; x2 = (#bedrooms-2)/5 (when avg size is 2)\
&nbsp; &nbsp; &nbsp; &nbsp; -0.5≤x<sub>1</sub>≤0.5, -0.5≤x<sub>2</sub>≤0.5\
&nbsp; &nbsp; &nbsp; &nbsp; more generally, (x<sub>1</sub>-μ<sub>1</sub>)/s<sub>1</sub>\
&nbsp; &nbsp; &nbsp; &nbsp; μ: avg value of x in training set\
&nbsp; &nbsp; &nbsp; &nbsp; s: range(max-min) (or standard deviation if *standardization*)\
\
\
**4.4 Learning Rate**\
\
Debugging: How to make sure gradient descent is working correctly\
\
How to choose learning rate α?\
=> Plot as (No. of iterations - x axis) and (J(Θ) - y axis)\
