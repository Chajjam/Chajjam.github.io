---
title: "TF Lecture 1 A New Programming Paradigm"
date: 2021-08-31
categories: Tensorflow
---
**1.1 Introduction: A Conversation with Andrew Ng**\
\
**1.2 A Primer in Machine Learning**\
\
**1.3 The 'Hello World' of Neural Networks"**
```Python
model = keras.Sequential([keras.layers.Dense(units=1, input_shape=[1])])
model.compile(optimizer='sgd', loss='mean_squared_error')

xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype=float)
ys = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 7.0])

model.fit(xs, ys, epochs=500)

print(model.predict([10.0]))
```
Dense: define a layer of connected neurons\
Sequential: successive layers are defined in sequence\
\
\
**1.4 Working through 'Hello World' in Tensorflow and Python**
