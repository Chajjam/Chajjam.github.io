---
title: "DL Lecture 7 Hyperparameter Tuning, Batch Normalization and Progmramming Frameworks"
date: 2021-08-07
categories: Hyperparameter
---
**7.1 Tuning Process**\
Importance 1: α\
Importance 2: β, n of hidden units, mini-batch size\
Importance 3: number of layers, learning rate decay\
Rest: β<sub>1</sub>, β<sub>2</sub>, ε\
\
Other ways:\
&nbsp;- Try random values\
&nbsp;- Coarse to fine: zoom pointing better values\
\
\
**7.2 Using an Appropriaate Scale to Pick Hyperparameters**\
Setting appropriate scale for α:\
it is not appropriate to set between 0.0001 - 1 randomly.\
=> use logarithm scale instead of linear scale\
\
Hyperparameters for exponentially weighted averages:\
Use logarithm scale for 1-β\
\
\
**7.3 Hyperparameters Tuning in Practice: Pandas vs. Caviar**\
Enough resources: training many models in parallel and pick the best one (Caviar)\
Not enough: babysitting one model (panda)\
\
\
**7.4 Normalizing Activations in a Network**\
Normalization: X = X/σ\
Normalize before activation or after activation? => normally normalize z\
z<sup>(i)</sup><sub>norm</sub> = (z<sup>(i)</sup>-μ)/√(σ<sup>2</sup>+ε)\
~z<sup>(i)</sup> = γz<sub>norm</sub><sup>(i)</sup> + β\
\
\
**7.5 Fitting Batch Norm into a Neural Network**\
X -> z<sup>[1]</sup> --- Batch Norm ---> ~z<sup>[1]</sup> -> a<sup>[1]</sup> = g<sup>[1]</sup>(~z<sup>[1]</sup>) -> z[2]...\
Update γ and β\
\
Note: b can be eliminated due to mean subtraction\
\
\
**7.6 Why does Batch Norm Work?**\
Covariate shift: if distribution changes, we might need to retrain learning algorithm\
=> batch norm reduces the effect
\
Batch Norm as regularization:\
&nbsp;- Each mini-batch is scaled by the mean/variance computed on just that mini-batch\
&nbsp;- this adds some noise to z<sup>[l]</sup> within that mini-batch.\
&nbsp;- this has a slight regularization effect\
\
\
**7.7 Batch Norm at Test Time**\
\
\
**7.8 Softmax Regression**\
C: n of classes\
\
Softmax layer:\
apply softmax activation function\
&nbsp; t = e<sup>(z<sup>[l]</sup>)</sup>\
&nbsp; a<sup>[l]</sup> = e<sup>z<sup>[l]</sup></sup> / ∑t<sub>i</sub>\
\
\
**7.9 Training a Softmax Classifier**\
Hard max: [1 0 0 0]\
Soft max: [e<sup>5</sup> e<sup>2</sup> e<sup>-1</sup> e<sup>3</sup>]\
\
Loss function: L(y^,y) = -∑y<sub>j</sub>log y^<sub>j</sub>\
Cost function: J = 1/m * ∑L(y^,y)\
\
\
**7.10 Deep Learning Frameworks**\
\
\
**7.11 Tensorflow**\
```Python
import numpy as np
import tensorflow as tf
```
```Python
w = tf.Variable(0, dtype=tf.float32)  # initialize to 0 and define type to floating number
optimizer = tf.keras.optimizers.Adam(0.1)   # set learning rate 0.1

def train_step():
  with tf.GrdientTape() as tape:    # record the sequence of operations during computing cost function in the forward prop
    cost = w ** 2 - 10 * w + 25
  trainable_variables = [w]
  grads = tape.gradient(cost, trainable_variables)
  optimizaer.apply_gradients(zip(grads, trainable_variables))   # zip takes two lists and pair corresponding elements
```
```Python
def training(x, w, optimizer):
  def cost_fn():
    return x[0] * w ** 2 + x[1] * w + x[2]
  for i in range[1000]:
    optimizer.minimize(cost_fn, [w])
  return w

w = training(x, w, optimizer)
```





