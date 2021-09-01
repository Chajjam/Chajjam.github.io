---
title: "DL Lecture 13 Object Detection"
date: 2021-08-31
categories: Object_Detection
---
**13.1 Object Localization**\
Need to output b<sub>x</sub>, b<sub>y</sub>, b<sub>h</sub>, b<sub>w</sub>, class label\
If class label is background, don't need to care the rest\
\
**13.2 Landmark Detection**\
Set key points (landmarks) along some object (like eye or mouth)\
\
**13.3 Object Detection**\
Sliding windows detection:\
&nbsp; take a small window and input that to ConvNet\
&nbsp; => if not the object, shift the window a little bit\
&nbsp; => Repeat with larger window sizes\
&nbsp; Disadvantage: computational cost\

**13.4 Convolutional Implementation of Sliding Windows**
