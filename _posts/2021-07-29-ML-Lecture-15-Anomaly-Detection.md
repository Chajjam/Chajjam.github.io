---
title: "ML Lecture 15 Anomaly Detection"
date: 2021-07-29
categories: Anomaly_Detection
---
**15.1 Problem Motivation**\
p(x<sub>test</sub>)<ε => flag anomaly\
\
Fraud detection:\
&nbsp; x<sup>(i)</sup>: features of user i's activities\
&nbsp; Model p(x) from data\
&nbsp; Identify unusual users by checking which have p(x)<ε\
\
Manufacturing:\
Monitoring computers in a data center:\
&nbsp; x<sup>(i)</sup>: features of machine i\
&nbsp; x<sub>1</sub>: memory use, x<sub>2</sub>: number of disk access/sec...\
\
\
**15.2 Gaussian Distribution**\
Gaussian (normal) didstribution:\
Say x∈R. If x is a distributed Gaussian with mean μ, variance σ<sup>2</sup>,\
x ~ N(μ, σ<sup>2</sup>) (~ means "distributed as")\
probability: p(x;μ, σ<sup>2</sup>) = (1/(√(2π)σ))e<sup>(-(x-μ)<sup>2</sup>/(2σ<sup>2</sup>)</sup>\
\
\
**15.3 Algorithm**\
Density Estimation:\
Training set: {x<sup>(1)</sup>, ..., x<sup>(m)</sup>}\
Each sample is x∈R<sup>n</sup>\
p(x) = p(x<sub>1</sub>;μ<sub>1</sub>,σ<sub>1</sub><sup>2</sup>) ... p(x<sub>n</sub>;μ<sub>n</sub>,σ<sub>n</sub><sup>2</sup>)\
p(x) = Π<sup>n</sup><sub>j=1</sub>p(x<sub>j</sub>;μ<sub>j</sub>,σ<sub>j</sub><sup>2</sup>)\
(Π means product)\
\
Anomaly Detection Algorithm:\
&nbsp;1. Choose features x<sub>i</sub> that you think might be indicative of anomalous examples\
&nbsp;2. Fit parameters μ<sub>1</sub>...μ<sub>n</sub>, σ<sub>1</sub><sup>2</sup>...σ<sub>n</sub><sup>2</sup>\
&nbsp;3. Given new example x, compute p(x) => anomaly if p(x)<ε\
\
\
**15.4 Developing and Evaluating an Anomaly Detection System**\
The Importance of real-number evaluation:\
When developing a learning alogorithm (choosing features, etc.), making decisions is much eaiser if we have a way of evaluating our learning algorithm\
Assume we have some labeled data, of anomalous and non-anomalous examples. (y=0 if normal, y=1 if anomalous)\
Training set: x<sup>1</sup>...x<sup>m</sup> (not anomalous examples)\
Cross validation set: (x<sub>cv</sub><sup>(1)</sup>,y<sub>cv</sub><sup>(1)</sup>)...(x<sub>cv</sub><sup>(m<sub>cv</sub>)</sup>,y<sub>cv</sub><sup>(m<sub>cv</sub>)</sup>)\
Cross validation set: (x<sub>test</sub><sup>(1)</sup>,y<sub>test</sub><sup>(1)</sup>)...(x<sub>test</sub><sup>(m<sub>test</sub>)</sup>,y<sub>test</sub><sup>(m<sub>test</sub>)</sup>)\
Possible evalauation metrics:\
&nbsp;- True positive, false positive, false negative, true negative\
&nbsp;- Precision/Recall\
&nbsp;- F<sub>1</sub>-score\
Can also use cross validation set to choose parameter ε\
\
\
**15.5 Anomaly Detection vs. Supervised Learning**\
Anomaly Detection:\
&nbsp;- Very small number of positive examples (often 0-20)\
&nbsp;- Large number of negative examples\
&nbsp;- Many different "types" of anomalies. Hard for any algorithm to learn from positive examples what the anomalies look like; futuer anomalies may look nothing like any of the anomalous examples seen so far\
&nbsl;- Fraud detection, Manufacturing, Monitoring Machines...
Supervised Learning:\
&nbsp;- Large number of positive and negative examples\
&nbsp;- Enough positive examples for algorithm to get a sense of what positive examples are like, future positive examples likely to be similar to ones in training set\
&nbsp;- Email spam classificataion, Weather prediction, Cancer classification...\
\
\
**15.6 Choosing What Features to Use**\
Applying log or root makes the histogram looks more "Gaussian"\
\
Error analysis for anomaly detection:\
Want p(x) large for normal examples x\
Want p(x) small for anomalous examples x\
Most common problem: p(x) is comparable for normal and anomalous example\
=> use another feature together\
\
Choose features that might take on unsusually large or small values in the event of an anomaly\
&nbsp; x<sub>1</sub> = CPU load, x<sub>2</sub> = network traffic\
&nbsp; => x<sub>3</sub> = CPU load / Network traffic, x<sub>4</sub> = (CPU load)<sup>2</sup> / Network traffic\
\
\
**15.7 Multivariate Gaussian Distribution**\
Use covariance matrix ∑ instead of variance\
\
\
**15.8 Anomaly Detection Using the Multivariate Gaussian Distribution**\
Multivariate Gaussian Distribution is computationally more expensive
