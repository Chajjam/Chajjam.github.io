---
title: "DL Lecture 8 ML Strategy (1)"
date: 2021-08-07
categories: Machine_Learning
---
**8.1 Why ML Strategy**\
Ideas:\
&nbsp;- Collect more data\
&nbsp;- Collect more diverse training set\
&nbsp;- Train algorithm longer with gradient descent\
&nbsp;- Try Adam instead of gradient descent\
&nbsp;- Try bigger network\
&nbsp;- Try smaller network\
&nbsp;- Try dropout\
&nbsp;- Add L<sub>2</sub> regularization\
&nbsp;- Network architecture\
\
\
**8.2 Orthogonalization**\
Orthogonalization: each "knob" does one thing\
\
\
**8.3 Single Number Evaluation Metric**
Using single number evaluation metric helps us to make decision faster\
\
\
**8.4 Satisficing and Optimizing Metric**\
Satisficing metric: we want at least bigger/smaller than some value, but don't need more\
ex: N metric => 1 optimizing and N-1 satisficing\
ex: wakewords / trigger words\
\
\
**8.5 Train/dev/test Distributions**\
Choose a dev set and test set to reflect data you expect to get in the future and consider important to do well on.\
Also, get from same distributions.\
\
\
**8.6 Size of the Dev and Test Sets**\
Size of test set: Set your test set to be big enough to give high confidence in the overall performance of your system\
\
\
**8.7 When to Change Dev/Test Sets and Metrics?**\









