---
title: "ML Lecture 17 Large Scale Machine Learning"
date: 2021-07-29
categories: Machine_Learning
---
**17.1 Learning with Large Datasets**\
Before using big datasets, it is reasonable to check if smaller dataset works\
\
\
**17.2 Stochastic Gradient Descent**\
Problem of Batch (use all training examples) gradient descent: parameter update can be very expensive\
Stochastic gradient descent:\
cost(Θ,(x<sup>(i)</sup>,y<sup>(i)</sup>)) = (1/2)(h<sub>Θ</sub>(x<sup>(i)</sup>)-y<sup>(i)</sup>)<sup>2</sup>\
J<sub>train</sub>(Θ) = (1/m)∑<sup>m</sup><sub>i=1</sub>cost(Θ,(x<sup>(i)</sup>,y<sup>(i)</sup>))\
&nbsp;1. Randomly shuffle (reorder) the dataset\
&nbsp;2. Repeat: for i=1 to m, Θ<sub>j</sub> = Θ<sub>j</sub> - α(h<sub>Θ</sub>(x<sup>(i)</sup)-y<sup>(i)</sup>)x<sub>j</sub><sup>(i)</sup>\
&nbsp; &nbsp; &nbsp; &nbsp; Repeat this for all j\
Difference is that Θ is updated for every i rather than waiting for the summation\
\
\
**17.3 Mini-Batch Gradient Descent**\
Use b examples in each iteration (where b = mini-batch size (typically 2-100))\
=> mini-batch gradient descent is likely to outperform stochastic gradient descent only if with a good vectorized implementation\
\
\
**17.4 Stochastic Gradient Descent Convergence**\
Checking for convergence:\
Every 1000 iterations (say), plot(cost(Θ,(x<sup>(i)</sup>,y<sup>(i)</sup>)) averaged over the last 1000 examples processed by algorithm\
Slowly decreasing the learning rate α is helpful for Θ to converge (E.g. α = const1 / (iterationNumber + const2)) (but may be more costly)\
\
\
**17.5 Online Learning**\
Repeat forever:\
Get (x,y) corresponding to user\
update Θ using (x,y)\
\
\
**17.6 Map Reduce and Data Parallelism**\
For example, when m=400 for updating parameter,\
Machine 1: Use i=1 to 100\
Machine 2: Use i=101 to 200\
...\
=> Combine all to update parameter\
\
Many learning algorithms can be expressed as computing sums of functions over the training set\
\
If there are multiple CPUs, each core can work as a computing machine.


