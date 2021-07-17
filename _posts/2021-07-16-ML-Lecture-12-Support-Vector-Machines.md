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
