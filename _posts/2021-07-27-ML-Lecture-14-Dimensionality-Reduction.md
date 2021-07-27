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
