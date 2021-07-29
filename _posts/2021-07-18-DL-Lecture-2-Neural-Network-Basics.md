---
title: "DL Lecture 2 Neural Network Basics"
date: 2021-07-18
categories: Neural_Network
---
**2.1 Binary Classification**\
(x,y): single training sample\
m: number of training examples\
X: [-x<sup>(1)</sup>-;...;x<sup>(m)</sup>] => n<sub>x</sub> * m matrix\
Y: [y<sup>(1)</sup>  ...   y<sup>(m)</sup>] => 1 * m matrix\
\
\
**2.2 Logistic Regression**\
y^ (y hat): P(y=1|x)\
w∈R<sup>n<sub>x</sub></sup> (parameters), b∈R (bias)\
\
y^ = σ(w<sup>T</sup>x) + b\
\
Another notation: (not used in the course)\
x<sub>0</sub> = 1, x∈R<sup>n<sub>x</sub>+1</sup>\
y^ = σ(Θ<sup>T</sup>x)\
Θ = [b ; w]\
\
\
**2.3 Logistic Regression Cost Function**\
Loss (error) function: L(y^,y) =  -(ylog y^ + (1-y)log(1-y^))\
Cost function: J(w,b) = (1/2)∑<sup>m</sup><sub>i=1</sub>L(y^<sup>(i)</sup>,y<sup>(i)</sup>) = -(1/m)∑<sup>m</sup><sub>i=1</sub>[y<sup>(i)</sup>log y^<sup>(i)</sup> + (1-y<sup>(i)</sup>)log(1-y^<sup>(i)</sup>]\
\
Difference between cost function and loss function:\
loss function computes the error for a single training example, while the cost function is the average of the loss functions of the entire training set\
\
\
**2.4 Gradient Descent**\
want to find w,b that minimize J(w,b)\
Generally initialize w,b by 0\
Repeat w := w - α(dJ(w)/dw) => w :- w - αdw\
\
\
**2.5 Derivatives**\
**2.6 More Derivative Examples**\
\
\
**2.7 Computation Graph**\
J(a,b,c) = 3(a+bc)\
&nbsp; 1) u = bc\
&nbsp; 2) v = a+u\
&nbsp; 3) J = 3v\
\
\
**2.8 Derivatives with a Computation Graph\
**2.9 Logistic Regression Gradient Descent**\
\
\
**2.10 Gradient Descent on m Examples**\
J=0; dw<sub>1</sub>=0; dw<sub>2</sub>=0; db=0\
For i=1 to m:\
z<sup>(i)</sup> = w<sup>T</sup>x<sup>(i)</sup>+b\
a<sup>(i)</sup> = σ(z<sup>(i)</sup>)\
J += -[y<sup>(i)</sup>log a<sup>(i)</sup> + (1-y<sup>(i)</sup>)log(1-a<sup>(i)</sup>)]\
dz<sup>(i)</sup> = a<sup>(i)</sup> - y<sup>(i)</sup>\
dw<sub>1</sub> += x<sub>1</sub><sup>(i)</sup>dz<sup>(i)</sup>\
dw<sub>1</sub> += x<sub>1</sub><sup>(i)</sup>dz<sup>(i)</sup>\
db += dz<sup>(i)</sup>\
\
J /= m\
dw<sub>1</sub>/=m; dw<sub>2</sub>/=m; db/=m\
\
result:\
dw<sub>1</sub> = ∂J/∂w<sub>1</sub>\
w<sub>1</sub> := w<sub>1</sub> - αdw<sub>1</sub>\
w<sub>2</sub> := w<sub>2</sub> - αdw<sub>2</sub>\
b := b - αdb\
\
\
**2.11 Vectorization**\
Vectorization: get rid of explicit for loops\
\
z = w<sup>T</sup>x + b\
```Python
# Non-vectorized
z = 0
for i in range(n,x):
  z += w[i] * x[i]
z += b

# Vectorized
z = np.dot(w,x) + b
```
```Python
import numpy as np
a = np.array([1,2,3,4])

# Output: [1 2 3 4]
```
```Python
import time
a = np.random.rand(1000000)
b = np.random.rand(1000000)

tic = time.time()
c = np.dot(a,b)
toc = time.time()   # measures current time

print("Vectorized version: " + str(1000*(toc-tic) + "ms")

# Output: Vectorized version: 1.59876567890ms
```
```Python
tic = time.time()
for i in range(1000000):
  c += a[i]*b[i]
toc = time.time()

print("For loop:" + str(1000*(toc-tic)) + "ms")

# Output: For loop: 474.298767898ms
```
\
\
**2.12 More Vectorization Examples**\
```Python
u = np.zeros((n,1))
for i in range(n):
  u[i] = math.exp(v[i])
```
```Python
import numpy as np
u = np.exp(v)   # elementwise operation
# np.log(v), np.abs(v), np.maximum(v,0)
```
\
\
**2.13 Vectorizing Logistic Regression**\
**2.14 Vectorizing Logistic Regression's Gradient Output**\
**2.15 Broadcasting in Python**\
```Python
import numpy as np

A = np.array([[56.0, 0.0, 4.4, 68.0],
              [1.2, 104.0, 52.0, 8.0],
              [1.8, 135.0, 99.0, 0.9]])

cal = A.sum(axis=0)   # sum vertically
print(cal)
# Output: [  59.  239.  155.4  76.9]

percentage = 100*A/cal.reshape(1,4)   # reshape is very cheap
print(percentage)
# Output: [[95  0.  2.8  88]
           [2.0  45  33  10]
           [3.0  56  63  1.1]]
```
Broadcasting example:\
[1, 2, 3, 4] + 100 = [1, 2, 3, 4] + [100, 100, 100, 100] = [101, 102, 103, 104]\
[[1, 2, 3],[4, 5, 6]] + [100, 200, 300] = [[101, 202, 303], [104, 205, 306]]\
\
\
**2.16 A Note on Python / Numpy Vectors**\
It is better to use (5,1) shape than (5,) shape\
\
\
**2.17 Quick Tour of Jupyter / ipython notebooks**\
**2.18 Explanation of Logistic Regression Cost Function**







