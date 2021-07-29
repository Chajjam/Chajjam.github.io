---
title: "ML Lecture 14 Dimensionality Reduction"
date: 2021-07-21
categories: Dimensionality_Reduction
---
**14.1 Motivation I: Data Compression**\
Ex) centimeter / inch as one label\
\
**14.2 Motivation II: Visualization**\
Often reduce to 2 or 3 dimension because we cannot visualize higher dimension\
\
**14.3 Principal Component Analysis Problem Formulation**\
Principal Component Analysis (PCA): tries to find a surface that reduces projection error\
Before performing PCA, it is common to perform mean normalization at feature scaling so that different features have zero mean\
\
Note: PCA is a totally different algorithm from linear regression (LR: between points, have y value / PCA: orthogonal projection, no y)\
\
\
**14.4 Principal Component Analysis Algorithm**\
PCA algorithm:\
Reduce data from n-dimensions to k-dimensions\
Compute "covariance matrix"\
&nbsp; &nbsp; ∑ = (1/m) * ∑<sup>n</sup><sub>i=1</sub>(x<sup>(i)</sup>)(x<sup>(i)</sup>)<sup>T</sup>\
Compute "eigenvectors" of matrix ∑:
[U, S, V] = svd(Sigma); (or eig(Sigma))\
Ureduce = U(:,1:k);\
z = Ureduce' * x;\
\
\
**14.5 Reconstruction from Compressed Representation**\
x<sub>approx</sub> = U<sub>reduce</sub> * z\
\
\
**14.6 Choosing the Number of Principal Components**\
Typically, choose k to be smallest value so that:\ 
(Average squared projection error) / (Total variation in the data) ≤ 0.01\
=> 99% of variance is retained\
\
Algorithm:\
Try PCA with k=1 (next 2, 3...)\
=> Compute U<sub>reduce</sub>, z<sup>(1)</sup>, z<sup>(2)</sup>, ... , z<sup>(m)</sup>, x<sub>approx</sub><sup>(1)</sup>, ..., x<sub>approx</sub><sup>(m)</sup>\
=> Check if (Error/Variation) ≤ 0.01\
\
[U, S, V] = svd(Sigma)\
s = [[s11, 0, 0, 0,...], [0, s22, 0, 0, ...]. ..., [0, ..., Snn]]\
For given k,\
1 - (∑<sup>k</sup><sub>i=1</sub>S<sub>ii</sub>) / (∑<sup>n</sup><sub>i=1</sub>S<sub>ii</sub>) ≤ 0.01\
\
\
**14.7 Advice for Applying PCA**\
Supervised learning speedup:\
(x<sup>(i)</sup>, y<sup>(i)</sup>) ... where x is very high dimension\
Extract inputs: Apply PCA to unlabeled dataset x<sup>(i)</sup>... and make it to z<sup>(i)</sup>, which is lower dimension\
As a result: new training set (z<sup>(i)</sup>, y<sup>(i)</sup>)...\
\
Note: mapping x->z should be defined by running PCA only on TRAINING SET. This mapping can be applied as well to the exampels 
 




