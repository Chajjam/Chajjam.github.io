---
title: "ML Week 11 Machine Learning System Design"\
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
y = 1 in presence of rare class we want to detect
