---
title: "ML Lecture 11 Machine Learning System Design"\
date: 2021-07-16
categories: Machine_Learning
---
**11.1 Prioritizing What to Work on: Spam Classification Example**\
\
**11.2 Error Analysis**\
Recommended approach:\
&nbsp;- start with a simple algorithm\
&nbsp;- plot learning curves to decide helpful approach\
&nbsp;- error analysis: manually examine the examples in CV set that your algorithm made errors on. See if you spot any systematic trend in what type of examples it is making errors on.\
\
The importance of numerical evaluation: ex) error percentage after implementing "stemming" software (E.g. "Porter stemmer")\
\
\
**11.3 Error Metrics for Skewed Classes**\
```Octave
function y = predict(x)
    y = 0;  % ignore x!
return
```
Skewed Classes: when there is very few positive examples compared to negative examples\
\
Precision/Recall\
y = 1 in presence of rare class we want to detect\
Predicted Class (PC), Actual Class (AC)\
&nbsp;- PC==1 && AC==1 => True Positive (TP)\
&nbsp;- PC==0 && AC==0 => True Negative (TN)\
&nbsp;- PC==1 && AC==0 => False Positive (FP)\
&nbsp;- PC==0 && AC==1 => False Negative (FN)\
&nbsp;=> Precision = True Positives / Predicted Positives = TP/(TP+FP)\
&nbsp;=> Recall = True Positives / Actual Positives = TP/(TP+FN)\
\
\
**11.4 Trading Off Precision and Recall**\
Increase threshold (e.g. 0.5->0.7) => Higher precision, Lower recall\
Decrease threshold (e.g. 0.5->0.3) => Lower precision, Higher recall\
\
F<sub>1</sub> Score (F Score)\
Idea: How to compare precision/recall numbers?\
=> Average: (P + R) / 2 => not a good for extreme values\
=> F<sub>1</sub> Score: 2*(PR)/(P+R)\
\
\
**11.5 Data for Machine Learning**\
Large data rationale\
Assume feature x∈R<sup>n+1</sup> has sufficient info to predict y accurately.\
Example: For breakfast I ate (&nbsp; &nbsp; ) eggs.\
Counterexample: Predict housing price from only size and no other features.\
Useful test: Given the input x, can a human expert confidently predict y?\
\
If we use a learning algorithm with many parameters (e.g. regression with many features, neural network with many hidden units) => *Low Bias*\
use a very large training set (unlikely to overfit) => *Low Variance*
