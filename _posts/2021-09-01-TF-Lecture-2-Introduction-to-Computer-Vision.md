---
title: "TF Lecture 2 Introduction to Computer Vision"
date: 2021-09-01
categories: Computer_Vision
---
**2.1 A Conversation with Andrew NG**\
\
**2.2 An Introduction to Computer Vision**\
\
**2.3 Writing Code to Load Training Data**
```Python
fasion_mnist = keras.datasets.fashion_mnist
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
```
\
**2.4 Coding a Computer Vision Neural Network**
```Python
model = keras.Sequential([
  keras.layers.Flatten(input_shape=(28,28)),  # input shape is 28 * 28
  keras.layers.Dense(128, activation=tf.nn.relu), # hidden layer
  keras.layers.Dense(10, activation=tf.nn.softmax)  # 10 classes of clothings
])
```
Flatten: turns the input shape into a simple linear array\
\
\
**2.5 Walk Through a Notebook for Computer Vision**\


