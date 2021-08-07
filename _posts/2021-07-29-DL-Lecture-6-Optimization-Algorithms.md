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
\
\
**6.7 RMSprop**\
\
\
**6.8 Adam Optimization Algorithm**\
Intialize V<sub>dW</sub>=0, S<sub>dW</sub>=0, V<sub>db</sub>=0, S<sub>db</sub>=0\
On iteration t:\
&nbsp; Compute dW, db using current mini-batch\
&nbsp; V<sub>dW</sub> = β<sub>1</sub>V<sub>dW</sub>\
&nbsp; V<sub>db</sub> = β<sub>1</sub>V<sub>db</sub> + (1-β<sub>1</sub>)db  (momentum)\
&nbsp; S<sub>dW</sub> = β<sub>2</sub>s<sub>dW</sub>\
&nbsp; S<sub>db</sub> = β<sub>2</sub>S<sub>db</sub> + (1-β<sub>2</sub>)db<sup>2</sup> (RMS prop)\
&nbsp; V<sub>dW</sub><sup>corrected</sup> = V<sub>dW</sub>/(1-β<sub>1</sub><sup>t</sup>)\
&nbsp; V<sub>db</sub><sup>corrected</sup> = V<sub>db</sub>/(1-β<sub>1</sub><sup>t</sup>)\
&nbsp; S<sub>dW</sub><sup>corrected</sup> = S<sub>dW</sub>/(1-β<sub>2</sub><sup>t</sup>)\
&nbsp; S<sub>db</sub><sup>corrected</sup> = V<sub>db</sub>/(1-β<sub>2</sub><sup>t</sup>)\
&nbsp; W := W - α(V<sub>dW</sub><sup>corrected</sup> / (√S<sub>dW</sub><sup>corrected</sup>+ε))\
&nbsp; b := b - α(V<sub>db</sub><sup>corrected</sup> / (√S<sub>db</sub><sup>corrected</sup>+ε))\
\
Hyperparameters:\
α: need to be tuned\
β<sub>1</sub>: 0.9 recommended (dW)\
β<sub>2</sub>: 0.999 recommended (dW<sup>2</sup>)\
ε: 10<sup>-8</sup>\
\
Adam: Adaptive moment estimation\
\
\
**6.9 Learning Rate Decay**\
α = 1 / (1 + DecayRate * epoch) * α<sub>0</sub>\
\
Other method:\
&nbsp;- α = 0.95<sup>epoch_num</sup>α<sub>0</sub>\
&nbsp;- α = k/√epoch_num * α<sub>0</sub> or k/√t * α<sub>0</sub>\
&nbsp;- discrete staircase\
&nbsp;- manual decay\
\
\
**6.10 The Problem of Local Optima**
