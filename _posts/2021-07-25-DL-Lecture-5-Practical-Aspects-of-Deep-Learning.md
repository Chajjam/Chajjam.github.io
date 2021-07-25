---
title: "DL Lecture 5 Practical Aspects of Deep Learning"
date: 2021-07-25
categories: Deep_Learning
---
**5.1 Train/Dev/Test Sets**\
It is impossible to choose appropriate hyperparameters at first.\
Data sets => training set / cross validation set (development set) / test set\
\
Mismatched train/test distribution:\
&nbsp;- Training set: cat pictures from webpages (high resolution, professional)\
&nbsp;- Dev/test sets: cat pictures from users using your app (low resolution, blurry)\
&nbsp;=> make sure dev and test sets come from same distribution\
\
+) not having a test set might be okay\
\
\
**5.2 Bias/Variance**\
high bias: underfitting the data\
high variance: overfitting the data\
\
low train set error + high dev set error => high variance\
high train set error + high dev set error => high bias\
high train set error + very high dev set error => high bias && high variance\
low train set error + low dev set error => low bias && low variance\
\
Optimal (Bayes) error: human error\
\
\
**5.3 Basic Recipe for Machine Learning**\
High Bias?\
=> Y => Bigger network/train longer/(NN architecture change)...\
=> N\
=> High Variance?\
=> Y => More data/regularization/(NN architecture change)...\
=> N\
=> Done\
\
\
**5.4 Regularization**\
L2 regularization for logistic regression: add (λ/2m)||w||<sub>2</sub><sup>2</sup> (just omit b because it is just a single number)\
L1 regularization for logistic regression: add (λ/2m)||w||<sub>2</sub> (w will be sparse: w vector will have a lot of zeros in it)\
λ: regularization parameter\
\
regularization for neural network: add (λ/2m)∑<sub>l=1</sub><sup>L</sup>||w<sup>[l]</sup>||<sup>2</sup>\
Frobenius norm formula: ||w<sup>[l]</sup>||<sup>2</sup> = ∑<sup>n<sup>l</sup></sup><sub>i=1</sub>∑<sup>n<sup>[l-1]</sup></sup><sub>j=1</sub>(w<sub>i,j</sub><sup>[l]</sup>)<sup>2</sup> (w: (n<sup>[l]</sup>, n<sup>[l-1]</sup>)\
when updating the parameter, dW<sup>[l]</sup> = (backprop term) + (λ/m)W<sup>[l]</sup>\
L2 regularization is also called as "Weight Decay"\
\
\
**5.5 Why Regularization Reduces Overfitting?**\
\
\
**5.6 Dropout Regularization**\
Dropout regularization: randomly removed nodes for each training example\
Inverted dropout:
```Python
keep_prob = 0.8
d3 = np.random.rand(a3.shape[0], a3.shape[1]) < keep_prob
a3 = np.multiply(a3, d3)
a3 /= keep.prob   # inverted dropout technique
```
No dropout at test time\
\
\
**5.7 Understanding Dropout**\
Intuition: cannot rely on any one feature, so have to spread our weights\
Downside: cost function J is not well defined for every iteration\
=> turn off droup out when plotting cost-iteration graph\
\
\
**5.8 Other Regularization Methods**\
Data augmentation: randomly distorted images\
Early stopping: compare training and dev set error, then stop iteration earlier and update the parameters where overfitting is not too much\
=> downside: couples two unrelated tasks: optimizing J and avoid overfitting\
\
\
**5.9 Normalizing Inputs**\
Subtract mean:\
μ = (1/m)∑x<sup>(i)</sup>\
x := x - μ\
Then Normalize variance:\
σ<sup>2</sup> = (1/m)∑x<sup>(i)</sup> ** 2 (element-wise squaring)\
Note: use same μ,σ values for training and test sets\
\
Why normalize inputs?: because inputs may range very differently\
\
\
**5.10 Vanishing/Exploding Gradients**\
For very deep neural network, the value of y^ might vanish/explode\
=> partial solution: careful initialization of weights\
\
\
**5.11 Weight Initialization for Deep Networks**\
```Python
WL = np.random.randn(X.shape) * np.sqrt(2/n[L-1])   # good for relu
WL = np.random.randn(X.shape) * np.sqrt(1/n[L-1])   # good for tanh: Xavier initialization
sqrt(2/(n[l-1] + n[l]))   # another choice
```
\
\
**5.12 Numerical Approximation of Gradients**\
(f(Θ+ε) - f(Θ+ε))/2ε ≒ derivative\
\
\
**5.13 Gradient Checking**
Take parameters and reshape them into a big vector Θ.\
Take derivative parameters and reshape them into a big vector dΘ.\
```Python
for each i:
  dΘ_approx[i] = (J(Θ_1, ..., Θ_i+ε, ...) - J(Θ_1, ..., Θ_i-ε, ...)) / 2ε
# Check
||dΘ_approx - dΘ|| / (||d_approx|| + ||dΘ||)
# if this is similar to 10^-7 or whatever, it is less iikely there is bug
```
\
\
**5.14 Gradient Checking Implementation Notes**\
&nbsp;- Don't use gradient checking in training - only to debug\
&nbsp;- If algorithm fails grad check, look at components to try to identify bug\
&nbsp;- Remember regularization\
&nbsp;- Does not work with dropout\
&nbsp;- Run at random initialization; perhaps again after some training
