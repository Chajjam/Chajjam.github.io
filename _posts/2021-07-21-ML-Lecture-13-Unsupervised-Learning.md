---
title: "ML Lecture 13 Unsupervised Learning"
date: 2021-07-21
categories: Unsupervised_Learning
---
**13.1 Unsupervised Learning: Introduction**\
Training set: {x<sup>(1)</sup>, x<sup>(2)</sup>, ..., x<sup>(m)</sup>}\
Clustering is good for: market segmentation, social network analysis, organize computing clusters, astronomical data analysis\
\
\
**13.2 K-means Algorithm**\
Randomly initialize n cluster centroids\
=> data sets will be assigned to each cluster according to distance\
=> move cluster centroids to average of data sets in each cluster\
=> assignement\
=> movement\
=> Repeat\
\
K Means Algorithm:\
Input: K (number of clusters), training set {x<sup>(1)</sup>, x<sup>(2)</sup>, ..., x<sup>(m)</sup>}\
Randomly initialize K cluster centroids μ<sub>1</sub>, μ<sub>2</sub>, ..., μ<sub>K</sub>\
Repeat:\
(Cluster assignment step)\
for i=1 to m: c<sup>(i)</sup> := index (from 1 to K) of cluster centroid closest to x<sup>(i)</sup>\
&nbsp; &nbsp; &nbsp; c<sup>(i)</sup> = min<sub>k</sub>||x<sup>(i)</sup>-μ<sub>k</sub>||\
(Move centroid step)\
for k=1 to K:\
μ<sub>k</sub> := average (mean) of points assigned to cluster k\
\
We can remove clusters or randomize it\
\
K-means for non-separated clusters\
Even the data is not well separated, K-means will separate well if clusters are set appropriately\
\
\
**13.3 Optimization Objective**\
c<sup>(i)</sup>: index (from 1 to K) of cluster centroid closest to x<sup>(i)</sup>\
μ<sub>k</sub>: cluster centroid k\
μ<sub>c<sup>(i)</sup></sub>: cluster centroid of cluster to which example x<sup>(i)</sup> has been assigned\
\
Cost function (distortion) J: find c<sup>(i)</sup> and μ<sub>i</sub> that minimizes J\
\
\
**13.4 Random Initialization**\
Random initialization:\
&nbsp;- Should have K < m\
&nbsp;- Randomly pick K training examples\
&nbsp;- Set μ<sub>1</sub>...μ<sub>k</sub> to these K examples\
&nbsp; &nbsp; μ<sub>1</sub> = x<sup>(i)</sup>, μ<sub>2</sub> = x<sup>(j)</sup>\
&nbsp; Solution for local minimum problem (when K is big enough like 50-1000): Iterates random initialization and pick clustering that gave lowest cost J\
\
\
**13.5 Choosing the Number of Clusters**\
Elbow method: As we increase the number of clusters, J decreases and set "Elbow" as K\
=> not used often due to absence of clear elbow\
\
Sometimes, you're running K-means to get clusters to use for some later/downstream purpose. Evaluate K-means based on a metric for how well it performs for thaat later purpose

