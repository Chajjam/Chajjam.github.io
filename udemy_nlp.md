&nbsp;1. Markov Model\
\
Let's assume that:\
&nbsp; &nbsp; Sequence: { x<sub>1</sub>, x<sub>2</sub>, ... x<sub>T</sub> }\
&nbsp; &nbsp; Prob of Sequence: p(x<sub>1</sub>, x<sub>2</sub>, ... x<sub>T</sub>)\
&nbsp; &nbsp; Prediction: p(x<sub>T</sub> | x<sub>1</sub>, x<sub>2</sub>, ... x<sub>T</sub>)\
\
We call our model a Markov Model if the model satisfies Markov Property.\
Then what is Markov Property?\
\
Definition:\
The Markov property is a very restrictive assumption on the dependency structure of the joint distribution.\
\
This is not really intuitive.\
A simpler explanation is:\
&nbsp; &nbsp; the property that the probability of one element is only affected by the previous one.\
&nbsp; &nbsp; In other words, x<sub>t</sub> is independent of x<sub>t-2</sub>, x<sub>t-3</sub>, ...\
\
There are cases that the Markov Property is not true.\
Still, we can express the probability with respect to previous one.\
p(x<sub>1</sub>, x<sub>2</sub>) = p(x<sub>1</sub>)(p(x<sub>2</sub> | x<sub>1</sub>)\
This is 2-varaible Bayes' rule.\
For more than 3 variables, Bayes' rule is applied in the same way.\
p(x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub>) = p(x<sub>1</sub>)p(x<sub>2</sub>, x<sub>3</sub> | x<sub>1</sub>)\
p(x<sub>1</sub>, x<sub>2</sub>, x<sub>3</sub>) = p(x<sub>1</sub>)p(x<sub>2</sub> | x<sub>1</sub>)p(x<sub>3</sub> | x<sub>2</sub>, x<sub>1</sub>)\
\
In this way, we can extend Bayes' rule infinitely.\
Generalization of this is called "Chain Rule of Probability".\
p(x<sub>3</sub>, ..., x<sub>3</sub>) = p(x<sub>1</sub>)p(x<sub>2</sub> | x<sub>1</sub>)p(x<sub>3</sub> | x<sub>1</sub>, x<sub>2</sub>)...p(x<sub>T</sub> | x<sub>T-1</sub>, ..., x<sub>1</sub>)\
In general, each term depends on all preceding terms.\
\
Obviously, Markov Property does not always hold.\
Yet, we assume the markov property while it does not, because it is still useful.\
George Box said:\
&nbsp; &nbsp; "All models are wrong, but some are useful"\
\
\
\
Now, let's see how can we express Markov Model mathematically.\
s(t) = s<sub>t</sub> = state at time t (t = 1, 2, ...)\
\
Then we number the states from 1, 2, ..., M\
where M is total number of possible states.\
for example, p(s<sub>t</sub>=i) means "probability that state at time t is i"\
We define 'State Transitions' as:\
&nbsp; &nbsp; p(s<sub>t</sub>=j|s<sub>t-1</sub>=i)\
More generally, we define 'State Transition Matrix' as:\
&nbsp; &nbsp; A<sub>ij</sub> = p(s<sub>t</sub>=j|s<sub>t-1</sub>=i) (i, j = 1,...,M)\
Conventionally, first index refers to previous state and the second refers to next state.\
In this equation, the model A does not depend on time t, so it is time-homogeneous Markov process.\
Generally, it will be A<sub>ij</sub>(t).\
\
We need another thing in addition to this.\
That is an Initial State.\
Why we need it is that initial state does not have a previous state, which deviates from our model.\
To solve this, we use "initial state distribution".\
π<sub>i</sub> = p(s<sub>1</sub>=i) (for i = 1...M)\
\
\
\
Here, I would like address possible problems of our model.\
p(s<sub>1...T</sub>) = π<sub>s<sub>1</sub></sub>PI(A<sub>s<sub>t</sub>s<sub>t-1</sub></sub>) from t=2 to T\
This only involves multiplication.\
When one transition never appeard in train set, that value is 0.\
Then obviously, the entire formula becomes 0.\
This is not we want.\
To resolve this, there is a method called "Add-One Smoothing".\
The idea is that we give a small probability to every possible transition.\
A<sub>ij</sub> = { count(i->j) + 1 } / { count(i) + M }\
Note that we are also adding M to the denominator to ensure each row of A sums to 1.\
We do this also to initial state distribution, which might have the same problem.\
An extended version of Add-One Smoothing is Add-Epsilon Smoothing.\
Instead of 1, we add ε to the numerator and add εM to the denominator.\
\
Another problem we might encounter is getting infinitely smaller.\
We multiply conditional probabilities over and over, so the probability gets smaller and smaller.\
Since computers do not have inifinite precision, it will eventually round nonzero number to zero.\
When we want to compare two cases, this might be problematic.\
To resolve this, we adopt log probabilities.\
The reason that this works is that:\
&nbsp;1) log is monotonically increasing\
&nbsp;2) if A > B then log(A) > log(B)\
This means that it does not have the problem with comparing.\
Another advantage is that addition is faster than multiplication, and noting that multiplication of logs is addition, log probabilities will be more efficient.\
\
\
\
When we are trying to build a text classifier, which is a classifier that determines a given text is one type or another, it is a supervised learning.\
However, our Markov models are unsupervised in that training data is merely a text without any labels.\
\
The answer is to apply Bayes' rule and build a Bayes classifier.\
k<sup>*</sup> = arg max p(class = k|x)\
with some modification,\
k<sup>*</sup> = arg max log p(poem | author = k) + log p(author = k)\
\
\
\
When we are trying to build a language model, we first need to distinguis two types of modes: Discriminative Model ( p(y|x) ) and Generative Model ( p(x|y) ).\
Recall that in our Markov Model, next word depends only on a single preceding word.\
We can extend this to multi-words dependency.\
if we build 2nd order Markov Model,\
&nbps; &nbsp; π<sub>i</sub> = p(s<sub>i</sub>=i)\
&nbps; &nbsp; A<sup>(1)</sup><sub>ij</sub> = p(s<sub>2</sub>=j|s<sub>1</sub>=j)\
&nbps; &nbsp; A<sup>(2)</sup><sub>ij</sub> = p(s<sub>t</sub>=j|s<sub>t-1</sub>=j, s<sub>t-2</sub>=i)\
Continues in Colab...\
\
\
\
\
\
&nbsp;2. Descrypting Deciphers\
\
Before diving into the topic of Ciphers, let's take a look at some terms.\
Cipher: Encoding and decoding a message\
Language modeling: probability of a given sentence, generate new sentences\
Genetic algorithm / evolutionary algorithm" optimization based on biological evolution.\
\
Let's say that we count an aritcle and want to find the probability of each biagram: AA, AB, AC, etc.
In general, p(x<sub>t</sub>|x<sub>t-1</sub>) = count{x<sub>t-1</sub>->count<sub>t</sub>} / count<sub>t-1</sub>\
Applying this,\
P(A|C) = (# of times "CA" appears in the dataset) / (# of times "C" appear in the dataset)\
Note the Bayes rule: p(AB) = p(B|A)p(A).\
\
Using the chain rule of probability,\
p(ABC) = p(C|AB)p(B|A)p(A)\
due to Markov property,\
p(ABC) = p(C|B)p(B|A)p(A).\
\
Generalizing this gives us words of any length:\
p(x<sub>1</sub>,x<sub>2</sub>, ...,x<sub>T</sub>) = p(x<sub>1</sub>) Π<sup>T</sup><sub>t=2</sub>p(x<sub>t</sub>|x<sub>t-1</sub>)\
\
Now let's extend this to a sentence.\
Sentence is a sequence of multiple words.\
w<sub>n</sub> = nth word in a sentence of length N\
T(n): length of nth word\
x<sub>t</sub><sup>(n)</sup>: letter in word n at position t\
p(w<sub>1</sub>,w<sub>2</sub>,...,w<sub>N</sub>) = Π<sup>N</sup><sub>n=1</sub>p(x<sub>1</sub><sup>(n)</sup>)Π<sup>T(n)</sup><sub>t=2</sub>p(x<sub>t</sub><sup>(n)</sup>|x<sub>t-1</sub><sup>(n)</sup>)\
w<sub>n</sub> = {x<sub>1</sub><sup>(n)</sup>,x<sub>2</sub><sup>(n)</sup>,...,x<sub>T(n)</sub><sup>(n)</sup>)\
\
At this point, you might be wondering how can we apply this model.\
First, find the individual bigram/unigram probabilities using a large text.\
This is availiable anywhere-maybe you can use Wikipedia.\
Then, we calculate the probability of any sentence of word.\
For example, a sequence like "FDSF SDDNH FDSFS" will return a low probability, while a sequence like "THEY DRINK WATER" will return a high probability.\
Among them, we want to find one that yields that maximum likelihood.\
As also discussed in Markov Model section, when we only want comparison but not the exact value of probability, we can use logarithm to prevent rounding to 0.\
Continues in Colab...\
\
\
\
\
\
&nbsp;3. Spam Detector\
In our simple spam detector, we use Naive Bayes and AdaBoost.\
Since we discussed Naive Bayes already, we'll only discuss AdaBoost here.\
The concept is that we combine several weak classifiers to form one strong classifier.\
Generally, this approach is called "ensembling".\
Other than AdaBoost, other ways to ensemble are bagging, random forest, etc.\
What is special about AdaBoost is that its base classifiers need to be weak.\
Weak classifiers are classifiers that can't solve sime geometrical structures, iike XOR and donut.\
Linear classifier and Decisions stumps are good examples.\
Using these weak classifiers, AdaBoost perform ensembiling through:\
&nbsp;- builds up each individual decision stump one at a time\
&nbsp;- at m-1 stage, the classifier consists of m-1 individual decision stump\
&nbsp;- training samples are also weighted and the samples that the model gets the most wrong are given the highest weight.\
&nbsp;- the newest decision stump prioritizes getting those samples right\
Through this steps, AdaBoost model improves mostly on what it is bad at.\
Continues in Colab...\
\
\
\
\
\
&nbsp;4. Sentiment Analyzer\
sentiment: how positive or negative some text is\
\
&nbsp;5. NTLK\
NLTK: Natural language toolkit\
We can install using:
```Python3
sudo pip install nltk
```
Using NLTK, we want to reduce words to a base form.\
This is really necessary because vocabulary gets too large easily once we start to analyze the text.\
For example, dog and dogs are practically same meaning, but they are considered as different words.\
We want to reduce these two vocabs into one vocab, dog.\
We can achieve this using Stemming and Lemmatization.\
\
\
\
\
\
&nbsp;6. Latent Semantic Analysis\
synonymy: multiple words with the same meaning\
polysemy: one word with multiple meanings
The key idea of LSA is to address a new latent variable to resolve such problems.\
This not only solves the problem, but also reduces the dimensionality, thereby speeding up our computation.\
\
Mathematics behind LSA is SVD (Singular-Value Decomposition).\
The basic idea is that if two components' relationship is linear, we can predict one component only with another component.\
In other words, we can just omit on component.\
This kind of dimensionality reduction also appears in recommendation system.\
Assume that our model recommends a movie to the user given users' data.\
People who like Power Rangers are likely to like Transformers because they share similar properties.\
If we are able to realize this in mathematical manner, we can reduce the dimesion.\
```Python3
# Input: X (shape is NxD)
# Output: Z (shape is Nxd, where d << D, default d = 2)
model = TruncatedSVD()
model.fit(X)
Z = model.transform(X)
# equivalent: Z = model.fit_transform(X)
```
Our implementation using Python looks like above.\
\
So, why is dimensionality reduction so important?\
There are several good reasons for it.\
&nbsp;- processing time\
&nbsp;- human can visualize only up to 3 dimensions\
&nbsp;- all data has signals and noises; we normally focus on signals more.\
\
\
\
\
\
&nbsp;7. Article Spinner\
Article spinning: take an article and slightly modify it, and generate a new article with different terms but with same meaning.\
This is not really easy. Look at the examples below.\
&nbsp;- Udemy.com is a PLATFORM or MARKETPLACE for online LEARNING.\
&nbsp;- Udemy.com is a PODIUM or FORUM for online RESEARCH.\
We replaced the capitalized words with their synonyms, but this does not match the context.\
Let's see how can we achieve this.\
\
Assume that we got a full text and labeled its words as w(1),...,w(N).\
Trigram model is similar to markov model.\
While markov model cares previous words, trigram model cares one previous and one next word.\
P[w(i)|w(i-1),w(i+1)]\
Of course, replacing every word makes no sense, so replace ith word with some probability.\
Continues in Colab...
