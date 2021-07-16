---
title: ML Lecture 9 Neural Networks: Learning
date: 2021-07-15
categories: Neural_Networks
---
**9.1 Cost Function**\
L = total number of layers in network\
s<sub>1</sub> = number of units(excluding bias unit) in layer l\
\
Binary classification\
&nbsp;- y=0 or y=1\
&nbsp;- 1 output unit (i.e. K=1)\
\
Multi-class classification(K classes)\
&nbsp;- y∈R<sup>K</sup>\
&nbsp;- K output units\
\
Cost function for Neural Network\
h<sub>Θ</sub>(x)∈R<sup>K</sup>   (h<sub>Θ</sub>(x))<sub>i</sub> = ith output\
J(Θ) = -(1/m)[∑<sup>m</sup><sub>i=1</sub>∑<sup>K</sup><sub>k=1</sub>y<sub>k</sub><sup>(i)</sup>log(h<sub>Θ</sub>(x<sup>(i)</sup>))<sub>k</sub> + (1-y<sub>k</sub><sup>(i)</sup>)log(1-(h<sub>Θ</sub>(x<sup>(i)</sup>))<sub>k</sub>)] + (λ/2m)∑<sup>L-1</sup><sub>i=1</sub>∑<sup>s<sub>l</sub></sup><sub>i=1</sub>∑<sup>s<sub>l+1</sub></sup><sub>j=1</sub>(Θ<sub>ji</sub><sup>(l)</sup>)<sup>2</sup>\
\
\
**9.2 Backpropagation Algorithm**\
To use gradient descent or etc, we need to compute\
J(Θ) and (∂/∂Θ<sub>ij</sub><sup>(l)</sup>)J(Θ)\
\
Backpropagation algorithm\
Intiution: δ<sub>j</sub><sup>(l)</sup> = "error" of node j in layer l\
δ<sub>j</sub><sup>(4)</sup> = α<sub>j</sub><sup>(4)</sup> - y<sub>j</sub>\
\
δ<sup>(3)</sup> = (Θ<sup>(3)</sup>)<sup>T</sup>δ<sup>(4)</sup> .* g'(z<sup>(3)</sup>)\
δ<sup>(2)</sup> = (Θ<sup>(2)</sup>)<sup>T</sup>δ<sup>(3)</sup> .* g'(z<sup>(2)</sup>)\
g'(z<sup>(l)</sup>) = a<sup>(l)</sup> .* (1-a<sup>(l)</sup>)\
\
Ignoring regularization,\
(∂/∂Θ<sub>ij</sub><sup>(l)</sup>)J(Θ) = a<sub>j</sub><sup>(l)</sup>δ<sub>j</sub><sup>(l+1)</sup>\
\
Training set {(x<sup>(1)</sup>, y<sup>(1)</sup>), ... , (x<sup>m</sup>,y<sup>m</sup>)}\
Set Δ<sub>ij</sub><sup>(l)</sup> = 0 (for all l, i, j)\
For i = 1 to m\
&nbsp; Set a<sup>(1)</sup> = x<sup>(i)</sup>\
&nbsp; Perform forward propagation to compute a<sup>(l)</sup> for l = 2,3,...,L\
&nbsp; Using y<sup>(i)</sup>, compute δ<sup>(L)</sup> = α<sup>(L)</sup>-y<sup>(i)</sup>\
&nbsp; Compute δ<sup>(L-1)</sup>, δ<sup>(L-2)</sup>, ..., δ<sup>(2)</sup>\
&nbsp; Δ<sub>ij</sub><sup>(l)</sup> := Δ<sub>ij</sub><sup>(l)</sup> + α<sub>j</sub><sup>(l)</sup>δ<sub>i</sub><sup>(l+1)</sup>\
D<sub>ij</sub><sup>(l)</sup> := (1/m)Δ<sub>ij</sub><sup>(l)</sup> + λΘ<sub>ij</sub><sup>(l)</sup> if j ≠ 0\
D<sub>ij</sub><sup>(l)</sup> := (1/m)Δ<sub>ij</sub><sup>(l)</sup> if j = 0\
\
\
**9.3 Backpropagation Intuition**\
Formally, δ<sub>j</sub><sup>(l)</sup> = (∂/∂z<sub>j</sub><sup>(l)</sub>cost(i)\
\
\
**9.4 Implementation Note: Unrolling Parameters**\
```Octave
% make matrices to a vector
thetaVec = [ Theta1(:); Theta2(:); Theta3(:) ];
DVec = [D1(:); D2(:); D3(:)];

% return to matrices
Theta1 = reshape(thetaVec(1:110) ,10,11);
Theta2 = reshape(thetaVec(111:220) ,10,11);
Theta3 = reshape(thetaVec(221:231) ,1,11);
```
\
\
**9.5 Gradient Checking**\
Implement: gradApprox = (J(theta + EPSILON) - J(theta - EPSILON)) / (2 * EPSILON)
```Octave
for i = 1:n,
    thetaPlus = theta;
    thetaPlus(i) = thetaPlus(i) + EPSILON;
    thetaMinus = theta;
    thetaMinus(i) = thetaMinus(i) - EPSILON;
    gradApprox(i) = (J(thetaPlus) - J(thetaMinus)) / (2*EPSILON);
end;
% Check that gradApprox ≒ DVec
```
Implementation Note:\
&nbsp;- Implemenet backprop to compute DVec\
&nbsp;- Implement numerical gradient check to compute gradApprox\
&nbsp;- Make sure they give similar values\
&nbsp;- Turn off gradient checking. Using backprop code for learning\
\
Important:\
&nbsp;- Be sure to disable gradient checking code before training classifier. If you run numerical gradient computation on every itertion, your code will be very slow.\
\
\
**9.6 Random Initialization**\
For gradient descent and advanced optimization method, we need initial value for Θ.
```Octave
optTheta = fminunc(@costFunction, initialTheta, options)
```
Consider gradient descent\
Zero initialization
```Octave
% if we set initial Θ = 0
initialTheta = zeros(n,1)
```
After each update, parameters corresponding to inputs going into each of two hidden units are identical.\
=> a<sub>1</sub><sup>(2)</sup> = a<sub>2</sub><sup>(2)</sup>\
\
Random initialization: Symmetry breaking\
=> initialize each Θ<sub>ij</sub><sup>(l)</sup> to a random value in [-ε,ε]
```Octave
Theta1 = rand(10,11)*(2*INIT_EPSILON) - INIT_EPSILON;
Theta2 = rand(1,11)*(2*INIT_EPSILON) - INIT_EPSILON;
```
\
\
**9.7 Putting it Together**\
\
Pick a network architecture\
&nbsp;- No. of input units: dimension of features x<sup>(i)</sup>\
&nbsp;- No. of output units: Number of classes\
&nbsp;- Resonable default: 1 hidden layer, or if>1 hidden layer, have same no. of hidden units in every layer (usually the more the better)\
\
Train a neural network\
&nbsp;1. Randomly initialize weights\
&nbsp;2. Implement forward propagation to get h<sub>Θ</sub>(x<sup>(i)</sup>) for any x<sup>(i)</sup>\
&nbsp;3. Implement code to compute cost function J(Θ)\
&nbsp;4. Implement backprop to compute partial derivatives (∂/∂Θ<sub>jk</sub><sup>(l)</sup>)J(Θ)\
&nbsp; => for i = 1:m (for/back prop using examples and get activations)\
&nbsp;5. Gradient checking, then disable gradient checking code\
&nbsp;6. Gradient descent or advanced optimization method with backpropagation to try to minimize J(Θ) as a function of parameters Θ







