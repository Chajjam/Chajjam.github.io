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
**ResNets**\
a<sup>[l]</sup> -> linear -> ReLU -> a<sup>[l+1]</sup> -> linear -> ReLU -> a<sup>[l+2]</sup>\
shortcut / skip connection: adding a<sup>[l]</sup> before applying ReLU activation


