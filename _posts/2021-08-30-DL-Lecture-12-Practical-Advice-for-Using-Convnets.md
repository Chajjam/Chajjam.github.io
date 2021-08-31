---
title: "DL Lecture 12 Practical Advice for Using ConvNets"
date: 2021-08-30
categories: ConvNets
---
**12.1 Using Open-Source Implementation**\
\
**12.2 Transfer Learning**\
Change softmax with:\
&nbsp;- freezing the entire network\
&nbsp;- freeze the part of the network\
&nbsp;- train from the initialization (when with a lot of data)\
\
**12.3 Data Augmentation**\
Common augmentation method:\
&nbsp;- Mirroring\
&nbsp;- Random Cropping\
&nbsp;- Rotation, Shearing, Local warping...\
&nbsp;- Color shifting (PCA algorithm)\
\
Implementing distortions during training\
: Use CPU thread to implement the distortions -> CPU/GPU training\

**12.4 State of Computer Vision**\
Data: Object Detection < Image Recognition < Speech Recognition\
Lots of data => Simpler algorithms, Less hand-engineering\
Little data => More hand-engineering\
\
Two sources of knowledge: labeled dat, hand engineered features/network\ architectures / other components\
\
Tips for doing well on benchmarks / winning competitions\
&nbsp;- Ensembling: train several networks independently and average their outputs\
&nbsp;- Multi-crop at test time: Run classifier on multiple versions of test images and average results\
&nbsp;- Use open source code
