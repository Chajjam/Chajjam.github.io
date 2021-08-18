---
title: "DL Lecture 11 Deep Convolutional Models: Case Studies"
date: 2021-08-14
categories: Case_Study
---
**11.1 Why Look at Case Studies?**\
\
**11.2 Classic Networks**\
LeNet-5\
&nbsp;- n<sub>W</sub>, n<sub>H</sub> decreases, n<sub>c</sub> increases\
&nbsp;- conv pool conv - pool - conv - pool - fc - fc - output\
\
AlexNet\
&nbsp;- similar to LeNet, but much bigger network\
&nbsp;- ReLU\
&nbsp;- multiple GPUs\
&nbsp;- Local Response Optimization\
\
VGG-16\
&nbsp;- simplified architecture\
&nbsp;- downside: large network\
\
\
**11.3 ResNets**\
a<sup>[l]</sup> -> linear -> ReLU -> a<sup>[l+1]</sup> -> linear -> ReLU -> a<sup>[l+2]</sup>\
shortcut / skip connection: adding a<sup>[l]</sup> to z<sup>[l+2]</sup> before applying ReLU activation\
\
Plain network: in theory, deeper network should always work better, but it is not true in reality\
ResNet: trining error constantly decreases as the number of layers increases\
\
\
**11.4 Why ResNets Work?**\
X -> Big NN -> a<sup>[l]</sup> -> layer1 -> layer2 -> a<sup>[l+2]</sup>\
a<sup>[l+2]</sup>\
= g(z<sup>[l+2]</sup> + a<sup>[l]</sup>\
= g(W<sup>[l+2]</sup>a<sup>[l+1]</sup> + b<sup>[l+2]</sup> + a<sup>[l]</sup>)\
If W<sup>[l+2]</sup>=0 and b<sup>[l+2]</sup>=0, g(a<sup>[1]</sup>) = a<sup>[l]</sup>\
=> Identity function is easy for residual block to learn\
\
\
**11.5 Networks in Networks and 1x1 Convolutions**\
What 1x1 convolution does: having a fully connected network\
also called network in network\
can be used to shrink dimension\
\
\
**11.6 Inception Network Motivation**\
Instead of picking one of various filter sizes or pooling, do them all and concatenate all the outputs and let the network learn whatever parameter it wants.\
The computional cost is pretty large, but we can reduce it by using 1x1 convolution as a "bottleneck layer".\
\
\
**11.7 Inception Network**\





