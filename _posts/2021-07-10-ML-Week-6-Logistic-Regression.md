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
Decision boundary: a line that divides where hypothesis is 1 and where hypothesis is 0\
There can also be non-linear decision boundaries.\
\
\
**6.4 Cost Function**\
Q: How to choose parameters Θ?\
Linear regression: J(Θ) = (1/m)∑<sup>m</sup><sub>i=1</sub>Cost(h<sub>Θ</sub>(x<sup>(i)</sup>),y<sup>(i)</sup>)\
Cost(h<sub>Θ</sub>(x<sup>(i)</sup>),y<sup>(i)</sup>) = (1/2)(h<sub>Θ</sub>(x<sup>(i)</sup>-y<sup>(i)</sup>)<sup>2</sup>\
=> this works fine in linear regression, but it is non-convex for logistic regression\
\
Logistic regression cost function\
Cost(h<sub>Θ</sub>(x),y) =\
&nbsp; -log(h<sub>Θ</sub>(x))   if y=1\
&nbsp; -log(1-h<sub>Θ</sub>(x)) if y=0\
\
\
**6.5 Simplified Cost Function and Gradient Descent**\
Combining two cost functions:\
&nbsp; Cost(h<sub>Θ</sub>(x),y) = -ylog(h<sub>Θ</sub>(x)) - (1-y)log(1-h<sub>Θ</sub>(x))\
&nbsp; (derives from maximum likelihood estimation, and is convex)\
\
To minimize the cost function, use gradient descent\
Repeat {
&nbsp; Θ<sub>j</sub> := Θ<sub>j</sub> - α∑<sup>m</sup><sub>i=1</sub>(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)x<sub>j</sub><sup>(i)</sup>\
}\
\
When updating parameters, it is better to use *vectorized implementation* rather than for loop.\
Vectorized implementation updates parameters at the same time.


