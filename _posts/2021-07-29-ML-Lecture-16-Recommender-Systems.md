---
title: "ML Lecture 16 Recommender Systems"
date: 2021-07-29
categories: Recommender_Systems
---
**16.1 Problem of Formulation**\
n<sub>u</sub>: number of users\
n<sub>m</sub>: number of movies\
r(i,j): 1 if user j has rated movie i\
y<sup>(i,j)</sup>: rating given by user j to movie i (defined only if r(i,j)=1)\
\
\
**16.2 Content Based Recommendations**\
x<sub>i</sub>: measures the degree of a certain content\
For each user j, learn a parameter Θ<sup>(j)</sup>∈R<sup>3</sup>.\
Predict user j as rating movie i with (Θ<sup>(j)</sup>)<sup>T</sup>x<sup>(i)</sup> stars\
\
Θ<sup>(j)</sup>: parameter vector for user j\
x<sup>(i)</sup>: feature vector for movie i\
For user j, movie i, predicted rating: (Θ<sup>(j)</sup>)<sup>T</sup>(x<sup>(i)</sup>)\
m<sup>(j)</sup>: number of movies rated y user j\
To learn Θ<sup>(j)</sup>:\
&nbsp; min (1/2m<sup>(j)</sup>)∑<sub>i:r(i,j)=1</sub>((Θ<sup>(j)</sup>)<sup>T</sup>(x<sup>(i)</sup>)-y<sup>(i,j)</sup>)<sup>2</sup> + λ/2m<sup>(j)</sup>∑(Θ<sub>k</sub><sup>(j)</sup>)<sup>2</sup>\
&nbsp; add ∑ from j=1 to n<sub>u</sub> for all users\
&nbsp; Then, apply gradient descent update\
\
\
**16.3 Collaborative Filtering**\
Given x<sup>(1)</sup>...x<sup>(n<sub>m</sub>)</sup> and movie ratings, can estimate Θ<sup>(1)</sup>...Θ<sup>(n<sub>u</sub>)</sup>\
Iterate minimizing Θ guessing and minimizing x guessing alternately to improve\
\
\
**16.4 Collaborative Filtering Algorithm**\
Perform minimizing Θ guessing and minimizing x guessing simultaneously\
\
Collaborative filtering algorithm:\
&nbsp;1. Initialize x and Θ variables to small random values\
&nbsp;2. Minimize cost function using gradient descent (or advanced optimization algorithm) for every j and i\
&nbsp;3. For a user with parameters Θ and a movie with (learned) features x, predict a star rating of Θ<sup>T</sup>x\
\
\
**16.5 Vectorization: Low Rank Matrix Factorization**\
Finding relative movies:\
How to find movies j related to movie i?\
Small ||x<sup>(i)</sup>-x<sup>(j)</sup>|| value means more relative\
\
\
**16.6 Implementational Detail: Mean Normalization**\
Perform mean normalization to every data: useful when there is a person with no rating data\
For user j, on movie i, predict (Θ<sup>(j)</sup>)<sup>T</sup>(x<sup>(i)</sup>) + μ<sub>i</sub>(mean vector)
