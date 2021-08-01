---
title: "DL Lecture 6 Optimization Algorithms"
date: 2021-07-29
categories: Optimizataion
---
**6.1 Mini-batch Gradient Descent**\
Batch vs. mini-batch gradient descent\
=> Vectorization allows you to efficiently compute on m examples\
\
Split training set into mini-batches\
X<sup>{1}</sup>, X<sup>{2}</sup>... (mini batch notation)
mini-batch t: X<sup>{t}</sup>, Y<sup>{t}</sup>\
\
Perform forward propagation on t examples\
=> Compute cost (with regularization)\
=> Implement backpropagation to get J and update gradient\
=> This process is called doing 1 *epoch* of training\
\
\
**6.2 Understanding Mini-batch Gradient Descent**\
May not decrease on every iteration because training occurs on different training set every time\
\
Choosing size of mini-batch:\
size = m -> batch gradient descent\
size = 1 -> stochastic gradient descent\
(Downside of SGD: lose the advantage of vectorization)\
If small training set: use batch gradient descent (<2000)\
Typical mini-batch size: 64, 128, 256, 512\
Make sure mini-batch fits in GPU/CPU memory\
\
\
**6.3 Exponentially Weighted Averages**\
V<sub>t</sub> = βV<sub>t-1</sub> + (1-β)Θ<sub>t</sub>\
V<sub>t</sub> is averaging the value of approximately 1/(1-β) samples\
\
\
**6.4 Understanding Exponentially Weighted Averages**\
V<sub>100</sub> = 0.1Θ<sub>100</sub> + 0.1 * 0.9Θ<sub>99</sub> + 0.1(0.9)<sup>2</sup>Θ<sub>98</sub> + ...\
\
0.9<sup>10</sup> ≒ 0.35 ≒ 1/e\
(1-ε)<sup>1/ε</sup> = 1/e\
=> Thus, we say approximately 1/(1-β) days\
\
\
**6.5 Bias Correction in Exponentially Weighted Averages**\
To prevent unusually low initial values,\
V<sub>t</sub>/(1-β<sup>t</sup>)\
\
If t becomes large, this term approaches 0, so no effect\
\
\
**6.6 Gradient Descent with Momentum**\
Use exponentially weighted averages of gradients to update weights instead









