---
title: DL Lecture 3 Shallow Neural Network
date: 2021-07-21
categories: Shallow_Neural_Network
---
**3.1 Neural Networks Overview**
represent ith layer with superscript [i] (don't confuse with ith training example (i))\
z<sup>[1]</sup> = W<sup>[1]</sup>x + b<sup>[1]</sup>\
=> a<sup>[1]</sup> = σ(z<sup>[1]</sup>)\
=> z<sup>[2]</sup> = W<sup>[2]</sup>x + b<sup>[1]</sup>\
=> a<sup>[2]</sup> = σ(z<sup>[2]</sup>)\
=> L(a<sup>[2]</sup>,y)\
\
\
**3.2 Neural Network Representation**\
Input layer: x1, x2, x3, ... (X / a<sup>[0]</sup>)\
Hidden layer: values are not observed (a<sup>[1]</sup>)\
&nbsp; w: (nodes, inputs), b: (nodes, 1)\
Output layer: generates predicted value y^ (y^ / a)\
=> two layer NN (don't count input layer conventionally)\
\
\
**3.3 Computing a Neural Network's Output**\
What happens in the first node in hidden layer in two layer NN:\
z<sup>[i]</sup> = w<sup>T</sup>x + b\
=> a<sub>1</sub><sup>1</sup> = σ(z<sub>1</sub><sup>[1]</sup>)\
... to last node\
[-w-](4,3)[x](3,1) + [b](4,1) = [wx+b] = [z]\
\
\
**3.4 Vectorizing Across Multiple Examples**\
for i=1 to m:
&nbsp; z<sup>[1](i)</sup> = W<sup>[1]</sup>x<sup>(i)</sup> + b<sup>[1]</sup>\
&nbsp; a<sup>[1](i)</sup> = σ(z<sup>[1](i)</sup>)\
&nbsp; z<sup>[2](i)</sup> = W<sup>[2]</sup>a<sup>[1](i)</sup> + b<sup>[2]</sup>\
&nbsp; a<sup>[2](i)</sup> = σ(z<sup>[2](i)</sup>)\
\
Z<sup>[1]</sup> = W<sup>[1]</sup>X + b<sup>[1]</sup>\
A<sup>[1]</sup> = σ(Z<sup>[1]</sup>)\
Z<sup>[2]</sup> = W<sup>[2]</sup>A<sup>[1]</sup> + b<sup>[2]</sup>\
A<sup>[2]</sup> = σ(Z<sup>[2]</sup>)\
\
\
**3.5 Explanation for Vectorized Implementation**\
\
\
**3.6 Activation Functions**\
tangent function g(hyperbolic tangent function) a = tanh(z) = (e<sup>z</sup>-e<sup>-z</sup>)/(e<sup>z</sup>+e<sup>-z</sup>)\
=> works better than sigmoid because sometimes we want data to be 0 (center)\
downside: if z is very large/very small, slope is very small, slowing down gradient descent
\
rectified linear unit (ReLu): a = max(0,z)
Leaky ReLU: usually works better; a = max(0.01 * z, z)
\
Rule:\
Output is 0/1 value (binary classification): sigmoid\
Other: ReLU default\
\
\
**3.7 Why Do You Need Non-Linear Activation Functions?**\
linear (identity) activation function does not really affect at all\
\
\
**3.8 Derivatives of Activation Functions**
g(z) = 1/(1+e<sup>-z</sup>)\
d/dz g(z) = 1/(e<sup>-z</sup>) * (1-1/(1+e<sup>-z</sup>))\
= g(z)(1-g(z))\
\
g(z) = tanh(z) = (e<sup>-z</sup> - e<sup>-z</sup>) / (e<sup>z</sup> + e<sup>-z</sup>)\
g'(z) = 1 - (tanh(z))<sup>2</sup>\
\
g(z) = max(0,z)\
g'(z) = 0 if z<0, 1 if z>0\
\
g(z) = max(0.01 * z,z)\
g'(z) = 0.01 if z<0, 1 if z>0\
\
\
**3.9 Gradient Descent for Neural Networks**\
n<sub>x</sub> = n<sup>[0]</sup> (input), n<sup>[1]</sup> (hidden unit), n<sup>[2]</sup> = 1 (output)\
\
Parameters:\
w<sup>[1]</sup>: (n<sup>[1]</sup>, <sup>[1]</sup>)\
b<sup>[1]</sup>: (n<sup>[0]</sup>, 1)\
w<sup>[2]</sup>: (n<sup>[2]</sup>, n<sup>[1]</sup>)\
b<sup>[2]</sup>: (n<sup>[1]</sup>, 1)\
\
Cost function: (1/m) ∑ L(y^,y)\
\
Randomly initialize parameters and perform gradient descent\
Repeat:\
Compute predicts (y^<sup>(i)</sup>)\
dw<sup>[1]</sup> = dJ/dw<sup>[1]</sup>, db<sup>[1]</sup> = dJ/db<sup>[1]</sup>\
w<sup>[1]</sup> = <sup>[1]</sup> - αdw<sup>[1]</sup>\
b<sup>[1]</sup> = <sup>[1]</sup> - αdb<sup>[1]</sup>\
\
Forward propagation:\
Z<sup>[1]</sup> = w<sup>[1]</sup>x + b<sup>[1]</sup>\
A<sup>[1]</sup> = g<sup>[1]</sup>(z<sup>[1]</sup>)\
z<sup>[2]</sup> = w<sup>[2]</sup>A<sup>[1]</sup> + b<sup>[2]</sup>\
A<sup>[2]</sup> = g<sup>[2]</sup>(z<sup>[2]</sup>)\
\
Backpropagation:\
dz<sup>[2]</sup> = A<sup>[2]</sup> - Y\
dw<sup>[2]</sup> = (1/m)dz<sup>[1]</sup>A<sup>[1]T</sup>\
db<sup>[2]</sup> = (1/m) * np.sum(dz<sup>[2]</sup>, axis=1, keepdims=True)\
dz<sup>[1]</sup> = w<sup>[2]T</sup>dz<sup>[2]</sup> * g<sup>[1]</sup>'(z<sup>[1]</sup>)\
dw<sup>[1]</sup> = (1/m)dz<sup>[1]</sup>X<sup>T</sup>\
db<sup>[1]</sup> = (1/m)np.sum(dz<sup>[1]</sup>, axis=1, keepdims=True)\
\
\
**3.10 Backpropagation Intuition**\
\
\
**3.11 Random Initialization**\
zero initialization is not a good choice because hidden units become identical (symmetric)\
W<sup>[1]</sup> = np.random.randn((2,2)) * 0.01 (we usually prefer small values because large weights will mess up sigmoid/tanh)\
b<sup>[1]</sup> = np.zeros((2,1)) (b doesn't matter)




