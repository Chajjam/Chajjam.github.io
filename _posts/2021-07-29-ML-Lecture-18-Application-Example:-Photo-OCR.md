---
title: "ML Lecture 18 Application Example: Photo OCR"
date: 2021-07-29
categories: Machine_Learning_Application\
---
**18.1 Problem Description and Pipeline**\
Photo OCR: Photo Optical Character Recognition\
Photo OCR pipeline:\
&nbsp;1. Text detection\
&nbsp;2. Character segmentation\
&nbsp;3. Character classification\
\
\
**18.2 Sliding Windows**\
Text detections step:\
Push a rectangle little bit over and over (for side parameter or step size) until it catches the objective\
=> then, try a larger rectangle\
\
Character segmentation step:\
Perform 1D sliding window\
\
\
**18.3 Getting Lots of Data and Artificial Data**\
Artificial data synthesis for photo OCR:\
&nbsp;- Use different fonts in computer and apply blurring/rotation...\
&nbsp;- Use current data to add more data by applying distortions\
&nbsp; Distortions introduced should be representation of the type of noise/distortions in the test set\
&nbsp; Usually does not help to add purely random/meaningless noise to your data\
\
Discussions on getting mor data:\
&nbsp;1. Make sure that you have a low bias classifier before expending the effort\
&nbsp;2. How much work would it be to get 10x as much data as we currently have?\
\
\
**18.4 Ceiling Analysis: What Part of the Pipeline to Work on Next**\
Estimating the errors due to each component (ceiling analysis)\
Image -> Text detection -> Character segmentation -> Character recognition\
\
Overall system: 72% accuracy\
After manually giving each component 100% accuracy,\
Text detection: 89% accuracy (inc 17%)\
Character segmentation: 90% accuracy (inc 1%)\
Character recognition: 100% accuracy (inc 10%)\
=> it would be worthwhile to work more on text detection
