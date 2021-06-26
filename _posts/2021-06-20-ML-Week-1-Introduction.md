---
title: "ML Week 1 Introduction"
date: 2021-06-20
categories: Machine_Learning
---
**1.1 What is Machine learning**<br />
: field of study that gives computers the ability to learn without being explicitly programmed<br />
: a computer program is said to learn from experience E with respect to some task T and some\
&nbsp; performance measure P, if its performance on T, as measured by P improves with experience E.\
\
Using the second definition,\
Suppose your email program watches your checking spams, and learns based on that to better filter spam.\
What is the task T in this setting?\
\
My answer: Watching you label emails as spam or not spam (correct)\
\
2 Machine learning algorithms: supervised learning, unsupervised learning\
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; (reinforcement learning, recommender systems...)\
\
\
**1.2 Supervised Learning**\
\
Housing price prediction example\
=> supervised learning: "right answers" are given\
=> Regression: predict real-valued output (here, price)\
\
Breast cancer example\
=> Classification: discrete valued output (0 or 1, or even more classes) (here, malignant or not)\
=> There might be infinitely many features -> we'll use support vector machine\
\
You want to develop learning algorithms for two problems below.\
P1: having a large inventory of identical items, predict how many will sell over next 3 months\
P2: want software to examine customer accounts and decide if hacked\
Classification or Regression?\
\
My answer: P1 is regression and P2 is classification (correct)\
\
\
**1.3 Unsupervised Learning**\
\
No labels for the dataset and find the structure from it\
\
Clustering algorithm: break dataset into separate clusters\
ex: Google News, Gene Sequencing, organizaing computing clusters, social network analysis, market segmentation, astronomical data analysis\
\
Cocktail party problem\
: in noisy party, two speakers use microphones\
=> using unsupervised learning, separate two different voices\
[W,s,v] = svd((repmat(sum(x.*x,1),size(x,1),1).*x)*x');\
\
Which of the examples would you use an unsupervised learning algorithm?\
&nbsp; 1 given email labeled spam/not, learn a spam filter\
&nbsp; 2 given a set of news articles on the web, group them according to the same story\
&nbsp; 3 given customer data, discover market segments and group customers into different market segments\
&nbsp; 4 given patients data as either diabetes or not, learn to classify new patients as diabetes or not\
\
My answer: 2, 3 (correct)
