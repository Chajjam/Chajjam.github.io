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
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;= Θ<sup>T</sup>x
