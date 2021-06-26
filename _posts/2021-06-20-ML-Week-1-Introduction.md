---
title: "ML Week 1 Introduction"
date: 2021-06-20
categories: Machine_Learning
---
**1.1 What is Machine learning**
: field of study that gives computers the ability to learn without being explicitly programmed\
: a computer program is said to learn from experience E with respect to some task T and some\
  performance measure P, if its performance on T, as measured by P improves with experience E.

Using the second definition,\
Suppose your email program watches your checking spams, and learns based on that to better filter spam.\
What is the task T in this setting?\
\
My answer: Watching you label emails as spam or not spam (correct)\
\
2 Machine learning algorithms: supervised learning, unsupervised learning\
                               (reinforcement learning, recommender systems...)\
\
\
**1.2 Supervised Learning**\
\
Housing price prediction example\
=> supervised learning: "right answers" are given\
=> Regression: predict real-valued output (here, price)\

Breast cancer example
=> Classification: discrete valued output (0 or 1, or even more classes) (here, malignant or not)
=> There might be infinitely many features -> we'll use support vector machine

You want to develop learning algorithms for two problems below.
P1: having a large inventory of identical items, predict how many will sell over next 3 months
P2: want software to examine customer accounts and decide if hacked
Classification or Regression?

My answer: P1 is regression and P2 is classification (correct)


**1.3 Unsupervised Learning**

No labels for the dataset and find the structure from it

Clustering algorithm: break dataset into separate clusters
* ex: Google News, Gene Sequencing, organizaing computing clusters, social network analysis,
      market segmentation, astronomical data analysis
      
Cocktail party problem
: in noisy party, two speakers use microphones
=> using unsupervised learning, separate two different voices
[W,s,v] = svd((repmat(sum(x.*x,1),size(x,1),1).*x)*x');

Which of the examples would you use an unsupervised learning algorithm?
1) given email labeled spam/not, learn a spam filter
2) given a set of news articles on the web, group them according to the same story
3) given customer data, discover market segments and group customers into different market segments
4) given patients data as either diabetes or not, learn to classify new patients as diabetes or not

My answer: 2, 3 (correct)


**2.1 Linear Regression with One Variable: Model Representation**

* Notation:
  m = Number of training examples
  x = input variable/features
  y = output variable/target variable
  (x, y) = one training example
  (x<sup>(i)</sup>, y<sup>(i)</sup>) = ith training example

Housing Prices example
- Training set
  1) Size in feet^2 (x)
  2) Price ($) in 1000's (y)

Training set -(feed)-> Learning algorith -> hypothesis(h)
                                          (size of house(x) -> h -> estimated price(y))
                                            => h maps from x's to y's
                                            How do we represent h?
                                            h<sub>Θ</sub>(x) = h(x) = Θ<sub>0</sub> + Θ<sub>1</sub>x
                                            => predicting a straight line functin
                                            => Linear regression with one variable
                                                = Univariate linear regression





