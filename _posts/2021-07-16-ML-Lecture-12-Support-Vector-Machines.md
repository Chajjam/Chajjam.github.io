---
title: "ML Lecture 12 Support Vector Machines
date: 2021-07-16
categories: Support_Vector_Machine
---
**12.1 Optimization Objective**\
Logistic Regression:\
min (1/m)∑<sup>m</sup><sub>i=1</sub>[<sup>m</sup><sub>i=1</sub>y<sup>(i)</sup>(-log h<sub>Θ</sub>(x<sup>(i)</sup>)) + (1-y<sup>(i)</sup>)(-log(1-h<sub>Θ</sub>(x<sup>(i)</sup>)))] + (λ/2m)∑<sup>n</sup><sub>j=1</sub>Θ<sub>j</sub><sup>2</sup>\
\
Support Vector Machine:\
min C∑<sup>m</sup><sub>i=1</sub>[y<sup>(i)</sup>cost<sub>1</sub>(Θ<sup>T</sup>x<sup>(i)</sup>) + (1-y<sup>(i)</sup>)cost<sub>0</sub>(Θ<sup>T</sup>x<sup>(i)</sup>)] + (1/2)∑<sup>n</sup><sub>j=1</sub>Θ<sub>j</sub><sup>2</sup>\
\
\
**12.2 Large Margin Intuition**\
If y=1, we want Θ<sup>T</sup>x ≥ 1\
If y=0, we want Θ<sup>T</sup>x ≤ -1\
\
SVM Decision Boundary: maximizes margin\
C plays similar role with 1/λ\
=> if C is not too large, it would do better job ignoring the extreme values\
\
\
**12.3 Mathematics Behind Large Margin Classification**\
u=[u1;u2], v=[v1;v2]\
inner product: u<sup>T</sup>v\
||u||: length of vector u\
p: length of projection of v onto u\
u<sup>T</sup>=p·||u||\
Simplification: Θ<sub>0</sub>=0, n=2\
(1/2)∑Θ<sub>j</sub><sup>2</sup> = (1/2)(Θ<sub>1</sub><sup>2</sup>+Θ<sub>2</sub><sup>2</sup>) = (1/2)||Θ||<sup>2</sup>\
\
SVM Decision Boundary\
(1/2)||Θ||<sup>2</sup>\
s.t. p<sup>(i)</sup>·||Θ|| ≥ 1    if y<sup>(i)</sup> = 1\
&nbsp; &nbsp; &nbsp; p<sup>(i)</sup>·||Θ|| ≤ -1    if y<sup>(i)</sup> = 0\
if p is small, ||Θ|| must become large, but we need to find small ||Θ||, so boundary with small margin is not a good choice.\
\
\
**12.4 Kernels I**\
Given x, compute new feature depending on proximity to landmarks l<sup>(1)</sup>, l<sup>(2)</sup>, l<sup>(3)</sup>\
f<sub>1</sub>: similarity(x, l<sup>(1)</sup>) = exp(-||x-l<sup>(1)</sup>||<sup>2</sup>/2σ<sup>2</sup>\
f<sub>2</sub>: similarity(x, l<sup>(2)</sup>) = exp(-||x-l<sup>(2)</sup>||<sup>2</sup>/2σ<sup>2</sup>\
f<sub>3</sub>: similarity(x, l<sup>(3)</sup>) = exp(-||x-l<sup>(3)</sup>||<sup>2</sup>/2σ<sup>2</sup>\
=> kernels (Gaussian kernel): k(x,l<sup>(i)</sup>\
\
if x≒l<sup>(i)</sup>,\
f<sub>i</sub> ≒ exp(-0) ≒ 1\
\
if x is far from l<sup>(i)</sup>,\
f<sub>i</sub> ≒ exp(-(large number)<sup>2</sup>/2σ<sup>2</sup>) ≒ 0\
\
\
**12.5 Kernels II**\
Given m training sets, choose l<sup>(1)</sup>=x<sup>(1)</sup>, ..., l<sup>(m)</sup> = x<sup>(m)</sup>\
Hypothesis: given x, compute features f∈R<sup>m+1</sup>, predict y=1 if Θ<sup>T</sup>f≥0\
\
∑Θ<sub>j</sub><sup>2</sup> = Θ<sup>T</sup>Θ\
\
SVM parameters:\
C(=1/λ)\
=> large C: lower bias, high variance\
=> small C: higher bias, low variance\
σ<sup>2</sup>\
=> large σ<sup>2</sup>: features f<sub>i</sub> vary more smoothly, higher bias, lower variance\
\
\
**12.6 Using an SVM**\
Use libraries like liblinear, libsvm...\
Need to specify:
&nbsp; choice of parameter C
&nbsp; choice of kernel:\
&nbsp; &nbsp; No kernel("linear kernel"): when n is large and m is small\
&nbsp; &nbsp; Gaussian kernel: when n is small, m is large\
```Octave
function f = kernel(x1,x2)
  % f = exp(-||x1-x2||^2/2σ^2
return
```
Note: do perform feature scaling before using the Gaussian kernel\
Note: Not all similarity functions similarity(x,l) make valid kernels. Must satisfy technical condition called "Mercer's Theorem" to make sure SVM packages' optimizations run correctly, and do not diverge\
\
Other off-the-shelf kernels available:
&nbsp;- polynomial kernel: k(x,l) = (x<sup>T</sup>l + 0/1/2/...)<sup>2/3/4/...</sup>,\
&nbsp;- more esoteric: string kernel, chi-square kernel, histogram intersection kernel, ...\
\
Multi-class classification: many SVM packages already have built-in multi-class classification functionality, otherwise, use one-vs.-all method\
\
Logistic regression vs. SVMs\
If n is large relative to m, use logistic regression, or SVM without a kernel\
If n is small, m is intermediate, use SVM with Gaussian kernel\
If n is small, m is large, create/add more features, then use logistic regression or SVM without a kernel\
Neural network likely to work well for most of these settings, but may be slower to train
