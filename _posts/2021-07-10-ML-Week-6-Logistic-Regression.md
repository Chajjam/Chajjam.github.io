---
title: "ML Week 6 Logistic Regression"
date: 2021-07-10
categories: Logistic_Regression
---
**6.1 Classification**\
Classification problems:\
&nbsp; email: spam or not spam?\
&nbsp; online transactions: fraudulent or not?\
&nbsp; tumor: malignant or benign?\
&nbsp; => y ∈ {0,1}\
&nbsp; &nbsp; 0: negative class\
&nbsp; &nbsp; 1: positive class\

&nbsp;- set hypothesis h<sub>Θ</sub>(x) = Θ<sup>T</sup>x\
&nbsp;- threshold classifier ouput h<sub>Θ</sub>(x) at 0.5:\
&nbsp; &nbsp; if hypothesis ≥ 0.5 => predict "y=1"\
&nbsp; &nbsp; if hypothesis ≤ 0.5 => predict "y=0"\
\
Consider a case there is an extreme example\
=> linear regression will display bad result\
\
Classification: y=0 or y=1
When using linear regression, h<sub>Θ</sub>(x) can be >1 or <0 (strangely)\
Logistic Regression: always 0≤h<sub>Θ</sub>(x)≤1\
\
\
**6.2 Hypothesis Representation**\
h<sub>Θ</sub>(x) = g(<sup>T</sup>x)\
where g(z) = 1/(1+e<sup>-z</sup>): sigmoid(or logistic) function\
\
Interpretation of Hypothesis Output\
h<sub>Θ</sub>(x): estimated probability that y=1 on input x\
&nbsp; h<sub>Θ</sub>(x) = P(y=1|x:Θ)\
&nbsp; "Probability that y=1, given x, parameterized by Θ"\
&nbsp; P(y=0|x;Θ) + P(y=1|x;Θ) = 1\
\
\
**6.3 Decision Boundary**\

