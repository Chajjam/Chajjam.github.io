---
title: "ML Lecture 8 Neural Networks: Representation"
date: 2021-07-14
categories: Neural_Networks
---
**8.1 Non-linear Hypotheses**\
Background: if there are too many variables, logistic regression can be very expensive(O(n<sup>2</sup>, O(n<sup>3</sup>)...)\
Solution: include only a subset of features => low accuracy\
=> need another solution\
\
\
**8.2 Neurons and the brain**\
Neural Networks\
Origins: Algorithms that try to mimic the brain\
\
\
**8.3 Model Representation I**\
Neurons in the brain: computational units\
&nbsp;- input wires called dendrites\
&nbsp;- output wire called an axon\
Neuron model: Logistic unit\
input layer: (x0(bias unit), x1,x2,x3,...)\
-> hidden layers\
-> output layer: h<sub>Θ</sub>(x)\
neuron with a sigmoid activation function\
Θ = parameters = weights\
\
x1   a<sub>1</sub><sup>(2)</sup>\
x2   a<sub>2</sub><sup>(2)</sup>   O  ->  h<sub>Θ</sub>(x)\
x3   a<sub>3</sub><sup>(2)</sup>\
\
terminology:\
a<sub>i</sub><sup>(j)</sup>: activation of unit i in layer j\
Θ<sup>(j)</sup>: matrix of weights controlling function mapping from layer j to layer j+1\
\
&nbsp; a<sub>1</sub><sup>(2)</sup> = g(Θ<sub>10</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>11</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>12</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>13</sub><sup>(1)</sup>x<sub>3</sub>)\
&nbsp; a<sub>2</sub><sup>(2)</sup> = g(Θ<sub>20</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>21</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>22</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>23</sub><sup>(1)</sup>x<sub>3</sub>)\
&nbsp; a<sub>3</sub><sup>(2)</sup> = g(Θ<sub>30</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>31</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>32</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>33</sub><sup>(1)</sup>x<sub>3</sub>)\
&nbsp; h<sub>Θ</sub>(x) = a<sub>1</sub><sup>(3)</sup> = g(Θ<sub>10</sub><sup>(2)</sup>a<sub>0</sub><sup>(2)</sup> + Θ<sub>11</sub><sup>(2)</sup>a<sub>1</sub><sup>(2)</sup> + Θ<sub>13</sub><sup>(2)</sup>a<sub>3</sub><sup>(2)</sup>)\
\
Θ<sup>(1)</sup> ∈ R<sup>3x4</sup>\
If network has s<sub>j</sub> units in layer j, s<sub>j+1</sub> units in layer j+1, then Θ<sup>(j)</sup> will be of dimension s<sub>j+1</sub>x(s<sub>j</sub>+1)\
\
\
**8.4 Model Representation II**\
Forward propagation: input -> hidden -> activation\
a<sub>1</sub><sup>(2)</sup> = g(Θ<sub>10</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>11</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>12</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>13</sub><sup>(1)</sup>x<sub>3</sub>)\
a<sub>2</sub><sup>(2)</sup> = g(Θ<sub>20</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>21</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>22</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>23</sub><sup>(1)</sup>x<sub>3</sub>)\
a<sub>3</sub><sup>(2)</sup> = g(Θ<sub>30</sub><sup>(1)</sup>x<sub>0</sub> + Θ<sub>31</sub><sup>(1)</sup>x<sub>1</sub> + Θ<sub>32</sub><sup>(1)</sup>x<sub>2</sub> + Θ<sub>33</sub><sup>(1)</sup>x<sub>3</sub>)\
h<sub>Θ</sub>(x) = a<sub>1</sub><sup>(3)</sup> = g(Θ<sub>10</sub><sup>(2)</sup>a<sub>0</sub><sup>(2)</sup> + Θ<sub>11</sub><sup>(2)</sup>a<sub>1</sub><sup>(2)</sup> + Θ<sub>13</sub><sup>(2)</sup>a<sub>3</sub><sup>(2)</sup>)\
\
z<sup>(2)</sup> = Θ<sup>(1)</sup> = a<sup>(1)</sup>\
a<sup>(2)</sup> = g(z<sup>(2)</sup>)\
z<sup>(3)</sup> = Θ<sup>(2)</sup>a<sup>(2)</sup>\
h<sub>Θ</sub>(x) = a<sup>(3)</sup> = g(z<sup>(3)</sup>)\
\
The model is not constrained with the inputs x1, x2, x3, but it develops its own inputs a<sub>1</sub><sup>(2)</sup>, a<sub>2</sub><sup>(2)</sup>, a<sub>3</sub><sup>(2)</sup>\
\
Architecture: how the neurons are connected each other\
\
\
**8.5 Examples and Intuitions I**\
Simple example: AND\
x1,x2 ∈ {0,1}\
y = x1 AND x2\
\
+1\
x1   O   h<sub>Θ</sub>(x)\
x2\
=> h<sub>Θ</sub>(x) = g(-30 + 20x1 + 20x2)\
note that: g(-4.6) = 0.01, g(4.6) = 0.99\
x1   x2   h<sub>Θ</sub>(x)\
0    0     0\
0    1     0\
1    0     0\
1    1     1\
\
\
**8.6 Examples and Intuitions II**\
x<sub>1</sub> AND x<sub>2</sub>\
+1\
x<sub>1</sub>   ->   O   ->   h<sub>Θ</sub>(x)\
x<sub>2</sub>\
\
(NOT x<sub>1</sub>) AND (NOT x<sub>2</sub>)\
+1\
x<sub>1</sub>   ->   O   -> h<sub>Θ</sub>(x)\
x<sub>2</sub>\
\
x<sub>1</sub> OR x<sub>2</sub>\
+1\
x<sub>1</sub>   ->   O   ->   h<sub>Θ</sub>(x)\
x<sub>2</sub>\
\
Putting it together: x<sub>1</sub> XNOR x<sub>2</sub> = NOT(x<sub>1</sub> OR x<sub>2</sub>)\
+1&nbsp; &nbsp; a<sub>1</sub><sup>(2)</sup>\
x<sub>1</sub>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; a<sub>1</sub><sup>(3)</sup>   ->   h<sub>Θ</sub>(x)\
x<sub>2</sub>&nbsp; &nbsp; a<sub>2</sub><sup>(2)</sup>\
\
\
**8.7 Multiclass Classification**\
One-vs-all\
Pedestrian - Car - Motorcycle - Truck\
h<sub>Θ</sub>(x) ∈ R<sup>4</sup> ( 4 logistic classifiers )\
Training set: (x<sup>(1)</sup>, y<sup>(1)</sup>) ...



