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
If metric/dev prefers algorithm A but you and users prefer B, you should change the evaluation metric.\
Ex) Error: 1/m * sigma[w * J], where w is 1 if nonporn, 100 if porn\
\
\
**8.8 Why Human-Level Performance?**\
Bayes optimal error: the best possible error that performance cannot do better\
Humans are quite good at a lot of tasks. So long as ML is worse than humans, you can:\
&nbsp;- Get labeled data from humans\
&nbsp;- Gain insight from manual error analysis: Why did a person get this right?\
&nbsp;- Better analysis of bias/variance\
\
\
**8.9 Avoidable Bias**\
If the algorithm is not doing as good as humans on training set, foucs on bias.\
Avoidable bias: difference between human level error and Bayes error\
\
\
**8.10 Understanding Human-level Performance**\
Use human level error as an estimate for Bayes error, and note that Bayes error is less than human level error\
\
\
**8.11 Surpassing Human-level Performance**\
Problems where ML significantly surpasses human-level performance:\
&nbsp;- online advertising\
&nbsp;- product recommendations\
&nbsp;- logistics (predicting transit time)\
&nbsp;- loan approvals\
&nbsp; &nbsp;=> all are learning from structured data\
&nbsp; &nbsp;=> not natural perception (which humans are very good at)\
&nbsp; &nbsp;=> need a lot of data\
\
\
**8.12 Improving your Model Performance**\
Two fundamental assumptions of supervised learning:\
&nbsp;- you can fit the training set pretty well\
&nbsp;- the training set performance generalizes pretty well to the dev/test set
