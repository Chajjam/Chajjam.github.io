---
title: "DL Lecture 9 ML Strategy (2)"
date: 2021-08-10
categories: Machine_Learning
---
**9.1 Carrying Out Error Analysis**\
Error analysis:\
&nbsp;- get ~100 mislabeled dev set examples\
&nbsp;- count up how many are dogs (problems)\
\
\
**9.2 Cleaning Up Incorrectly Labeled Data**\
Random errors are not a big deal, but systematic errors are\
Count the fraction among 100 samples\
\
\
**9.3 Build your First System Quickly, then iterate**\
Set up dev/test set and metric\
=> build initial system quickly\
=> use bias/variance analysis & Error analysis to prioritize next steps\
\
\
**9.4 Training and Testing on Different Distributions**\
Solution 1: set up same distribution => not recommended due to change in objective\
Solution 2: dev/test set is all original objective\
\
\
**9.5 Bias and Variance with Mismatched Data Distributions**\
When there is a gap between training error and dev error, we cannot immediately say there is a variance problem because data distribution might be different\
\
Training-dev set: same distribution as training set, but not used for training\
\
\
**9.6 Addressing Data Mismatch**\
Addressing data mismatch:\
&nbsp;- carry out manual error analysis to try to understand the difference between training set and dev/test sets\
&nbsp;- make training data more similar; or collect more data similar to dev/test sets\
\
\
**9.7 Transfer Learning**\
Transfer Learning: apply one structure to another objective\
=> remove the last layer and replace it with a layer that we want, keeping the other parameters fixed if small data / train all again if enough data\
\
Pre-training (using extant structure) -> fine-tuning (literally fine-tune)\
\
When transfer learning makes sense?\
&nbsp;- task A and B have the same input x\
&nbsp;- you have a lot more data for task A than Task B\
&nbsp;- low level features from A could be helpful for learning B\
\
\
**9.8 Multi-task Learning**\
When does multi-task learning makes sense\
&nbsp;- training on a set of tasks that could benefit from having shared lower-level features\
&nbsp;- usually: amount of data you have for each task is quite similar\
\
\
**9.9 What is End-to-end Deep Learning?**\
Multi-step task performs better because there are enough data for each process, but not for combined process\
\
\
**9.10 Whether to use End-to-end Deep Learning**\
Pros and cons of end-to-end deep learning:\
Pros:\
&nbsp;- Let the data speak\
&nbsp;- Less hand-designing of components neeeded\
Cons:\
&nbsp;- May need large amount of data\
&nbsp;- Excludes potentially useful hand-designed components\
\
Key question: do you have sufficient data to learn a function of the complexity needed to map x to y?
