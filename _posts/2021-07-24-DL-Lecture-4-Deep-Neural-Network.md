---
title: DL Lecture 4 Deep Neural Network
date: 2021-07-24
categories: Neural_Network
---
**4.1 Deep L-layer Neural Network**\
L: number of layers\
n<sup>[l]</sup>: number of units in layer l
a<sup>[l]</sup> = g<sup>[l]</sup>(z<sup>[l]</sup>)\
W<sup>[l]</sup>, b<sup>[l]</sup> = weights for z<sup>[l]</sup>\
\
\
**4.2 Forward Propagation in a Deep Network**\
x: z<sup>[1]</sup> = W<sup>[1]</sup>x + b<sup>[1]</sup>\
a<sup>[1]</sup> = g<sup>[1]</sup>(z<sup>[1]</sup>)\
z<sup>[2]</sup> = W<sup>[2]</sup>a<sup>[1]</sup> + b<sup>[2]</sup>\
a<sup>[2]</sup> = g<sup>[2]</sup>(z<sup>[2]</sup>)\
...\
z<sup>[4]</sup> = W<sup>[4]</sup>a<sup>[3]</sup> + b<sup>[4]</sup>\
a<sup>[4]</sup> = g<sup>[4]</sup>(z<sup>[4]</sup>) = y^\
*Question: can't we eliminate for loop with l?*\
\
\
**4.3 Getting Your Matrix Dimensions Right**\
z<sup>[l]</sup>, a<sup>[l]</sup>: (n<sup>[l]</sup>, 1)\
Z<sup>[l]</sup>, A<sup>[l]</sup>: (n<sup>[l]</sup>, m)\
dZ<sup>[l]</sup>, dA<sup>[l]</sup>: (n<sup>[l]</sup>, m)\
\
\
**4.4 Why Deep Representations**\
Circuit theory:\
Informally: there are functions you can compute with a small L-layer deep neural network that shallower networks require exponentially more hidden units to compute.\
\
\
**4.5 Building Blocks of Deep Neural Networks**\
\
\
**4.6 Forward and Backward Propagation**\
\
\
**4.7 Parameters vs Hyperparameters**\
Parameters: W, b\
Hyperparameters: learning rate, iterations, hidden layers, hidden units, activation function, (later: momentum, mini batch, regularizations) ...\
\
\
**4.8 What Does This Have to Do with the Brain?**
