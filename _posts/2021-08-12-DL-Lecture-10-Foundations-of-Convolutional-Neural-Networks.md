---
title: "DL Lecture 10 Foundations of Convolutional Neural Networks"
date: 2021-08-12
categories: Convolutional_Neural_Networks
---
**10.1 Computer Vision Problems**\
Computer vision problems:\
&nbsp;- image classification\
&nbsp;- object detection\
&nbsp;- neural style transfer\
\
\
**10.2 Edge Detection Example**\
Vertical edge detection:\
&nbsp;- * means convolution operation\
&nbsp;- if 6x6 * 3x3, get every 3x3 matrix and perform element-wise multiplication and add them all => 4x4 matrix\
&nbsp;- tf.nn.conv2d (in tensorflow), Conv2D (in keras)\
\
\
**10.3 More Edge Detection**\
Vertical: [[1 0 -1], [1 0 -1], [1 0 -1]]\
Horizontal: [[1 1 1], [0 0 0], [-1 -1 -1]]\
Sobel filter: [[1 0 -1], [2 0 -2], [1 0 -1]], more focus on central pixel\
Scharr filter: [[3 10 3], [10 0 -10], [3 0 -3]]\
Set 9 numbers as 9 parameters\
\
\
**10.4 Padding**\
nxn * fxf = (n-f+1)x(n-f+1)\
=> donwsides:\
&nbsp; &nbsp; - image shrinks for every convolutional operator\
&nbsp; &nbsp; - info of pixel on the edge is relatively thrown away a lot\
=> solution: padding the image with an additional border\
\
Valid and Same convolutions:\
&nbsp; valid: no padding; nxn * fxf = (n-f+1) * (n-f+1)\
&nbsp; same: pad so that output size is same as the input size\
&nbsp; &nbsp; &nbsp; &nbsp; (n+2p-f+1) x (n+2p-f+1) where p = (f-1)/2 (f is usally odd due to p value and the presence of central pixel)\
\
\
**10.5 Strided Convolutions**\
Stride: take multiple step
for padding p and stride s, nxn * fxf = ((n+2p-f)/s + 1) * ((n+2p-f)/s + 1)\
if the term is a fraction z, apply floor(z) to round down to nearest integer\
\
In math textbook, flipping the filter by both vertical and horizontal must be performed. In deep learaning convention, cross-correlation is actually being performed but by convention we call it convlution.\
\
\
**10.6 Convolutions Over Volume**\
multiple filters: take different outputs and stack them\
nxnxn<sub>c</sub> * fxfxn<sub>c</sub> = (n-f+1) x (n-f+1) x n<sub>c</sub>' (number of filters)\
\
\
**10.7 One Layer of a Convolutional Network**\
If layer l is a convolutional layer:\
f<sup>[l]</sup> = filter size\
p<sup>[l]</sup> = padding\
s<sup>[l]</sup> = stride\
n<sub>c</sub><sup>[l]</sup> = number of filters\
input: n<sub>H</sub><sup>[l-1]</sup>xn<sub>W</sub><sup>[l-1]</sup>xn<sub>c</sub><sup>[l-1]</sup>\
Each filter is: f<sup>[l]</sup>xf<sup>[l]</sup>xn<sub>c</sub><sup>[l-1]</sup>\
Activations: a<sup>[l]</sup> -> n<sub>H</sub><sup>[l]</sup>xn<sub>W</sub><sup>[l]</sup>xn<sub>c</sub><sup>[l]</sup>\
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; A<sup>[l]</sup> -> mxn<sub>H</sub><sup>[l]</sup>xn<sub>W</sub><sup>[l]</sup>xn<sub>c</sub><sup>[l]</sup>\
Weights: f<sup>[l]</sup>xf<sup>[l]</sup>xn<sub>c</sub><sup>[l-1]</sup>xn<sub>c</sub><sup>[l]</sup>\
bias: n<sub>c</sub><sup>[l]</sup> - (1,1,1,n<sub>c</sub><sup>[l]</sup>)\
\
\
**10.8 Simple Convolutional Network Example**\
Types of layer in a convolutional network:\
&nbsp;- convolution\
&nbsp;- pooling\
&nbsp;- fully connected\
\
\
**10.9 Pooling Layers**\
Pooling layer: Max pooling\
=> divide areas and get the max value from each area\
Intuition: if detected, keep it. if not, still small number\
\
Pooling layer: Average pooling: instead of max, take average\
=> sometimes used in very deep neural network\
\
Hyperparameters:\
f: filter size\
s: stride\
f=2, s=2 is often used to quick shrinking\
max or average pooling\
p: padding => very rarely used with pooling
note: no parameters to learn; just fixed\
\
\
**10.10 CNN Example**\
Convention: pool layer is not counted as the number of layer because there is no parameter but only some hyperparameters\
\
\
**10.11 Why Convolutions?**\
Parameter sharing: a feature detector (such as a vertical edge detector) that's useful in one part of the image is probably useful in another part of the image\
Sparsity of connections: in each layer, each output value depends only on a small number of inputs
