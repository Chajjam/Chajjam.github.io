---
title: "Probability and Stochastic Processes"
date: 2021-07-27
categories: Probability
---
**Lecture 1: Probability and Set Notation**\
Classic definition of probability:\
&nbsp; Provided that all events are equally likely, the probability of n event A equals\
&nbsp; &nbsp; P(A) = N<sub>A</sub>/N\
&nbsp; where N is the total number of possible outcomes, N<sub>A</sub> is the number of outcomes favorable to A\
\
&nbsp; Relative Frequency:\
&nbsp; The probability of event A, P(A) is determined experimentally by conducting n random experiments.\
&nbsp; The probability is equal to\
&nbsp; &nbsp; P(A) = lim<sub>n->inf</sub> n<sub>A</sub>/n\
&nbsp; where n<sub>A</sub> is the number of times the event occurs\
\
*Set Notation*\
&nbsp;- Set: a collection of *elements*\
&nbsp;- Cardinality |A|: the number of elements in a set\
&nbsp;- ∈, !∈ symbols indicate whether sometihing is or is not an element of a set\
&nbsp;- empty or null set contains no elements and is denoted {∅}\
&nbsp;- universal set or space S contains all possible elements relevnt in a particular context\
&nbsp;- Subset of A: set whose elements are all elements of A\
&nbsp;- B⊆A means tht B is a subset of A or that B belongs to A\
&nbsp;- For any set, A, {∅}⊆A⊆A⊆S\
&nbsp;- A⊂B is most often used to indicate a proper subset: a subset that cannot be also equal to the superset\
&nbsp;- ⊆ also illustrates transitivity: if C⊆B and B⊆A, then C⊆A  /  and equality: if A=B, then A⊆B and B⊆A\
\
*Set Operations*\
&nbsp;- Sum or Union of Two Sets:\
&nbsp; &nbsp;- The union of two sets consists all elements in both sets and is denoted A∪B or A+B\
&nbsp; &nbsp;- Union operation is commutative and associative\
&nbsp; &nbsp;- If B⊆A then B∪A=A\
&nbsp;- Product or Intersection of Two Sets:\
&nbsp; &nbsp;- The product of two sets consists of only those elements that are common to the two sets and is denoted AB or A∩B\
&nbsp; &nbsp;- Intersection operation is commutative, associative, and distributive\
&nbsp; &nbsp;- If A⊆B then AB=A and AA=A\t
&nbsp;- Mutually Exclusive Sets: Two sets A and B are mutually exclusive if they have no elements in common\
&nbsp;- Complement:\
&nbsp; &nbsp;- The complement of A (A<sup>-</sup>) defines a second set that contains all the elements in S that are not in A\
&nbsp; &nbsp;- A∪A<sup>-</sup> = S, AA<sup>-</sup> = {∅}, {∅<sup>-</sup>} = S\
&nbsp;- Partition of a set S is a series of mutually exclusive subsets that completely define S such that\
&nbsp; &nbsp; S = A<sub>1</sub> + ... + A<sub>N</sub>\
&nbsp;- Difference:\
&nbsp; &nbsp;- The difference between sets A and B is denoted A-B and consists of all the elements in A that are not in B\
&nbsp; &nbsp;- A-B = AB<sup>-</sup>\
\
Apparent Contradiction: {∅}⊆A⊆S, but {∅<sup>-</sup>}=S ({∅} and S are mutually exclusive). How is {∅}⊆S possible?\
=> My answer: {∅}⊆{∅<sup>-</sup>}, so it is possible\
=> Answer:\
&nbsp; &nbsp; If A and B are mutually exclusive, then AB={∅}.\
&nbsp; &nbsp; This means that if {∅} and S are mutually exclusive, then {∅}S={∅}\
&nbsp; &nbsp; However, if AB=A, then A⊆B. This allows {∅} to also be a subset of S\
\
Probability & Set Notation:\
&nbsp;- Sample Space: The universal set S containing all possible outcomes for an experiment\
&nbsp;- Outcomes: The elements in the experimental sample space\
&nbsp;- Event: Subsets formed of elements in the sample space\
&nbsp;- Elementary Event: An event containing a single element or outcome\
&nbsp;- Trial: Performing an experiment that generates a single event\
\
\
**Lecture 2: The Axioms of Probability & Conditional Probability**\
The Axioms of Probability:\
&nbsp; P(A) ≥ 0\
&nbsp; P(S) = 1\
&nbsp; If AB = {∅}, then P(A∪B) = P(A) + P(B)\
\
If AB != {∅},\
A∪B = A∪A<sup>-</sup>B\
B = AB∪A<sup>-</sup>B\
P(A∪B) = P(A) + P(A<sup>-</sup>B), P(B) = P(AB) + P(A<sup>-</sup>B)\
P(A∪B) = P(A) + P(B) - P(AB) ≤ P(A) + P(B)\
\
Conditional Probability:\
&nbsp;- The probability of event A given that event M has occured is:\
&nbsp; &nbsp; P(A|M) = P(AM) / P(M)\
&nbsp;- If A⊂M, then P(AM) = P(A) such that\
&nbsp; &nbsp; P(A|M) = P(A) / P(M) ≥ P(A)\
\
Total Probability Theorem\
&nbsp;- If A<sub>1</sub>,...,A<sub>N</sub> is a partition of universal set S, then\
&nbsp; &nbsp; P(B) = ∑P(B|A<sub>i</sub>)P(A<sub>i</sub>)\
Proof:\
&nbsp;B = SB = AB => apply third axiom\
\
Bayes Theorem:\
P(AB) = P(BA)\
P(A|B)P(B) = P(B|A)P(A)\
Using the total probability theorem,\
P(A|B) = P(B|A)P(A)/P(B) = P(B|A)P(A)/(P(B|A)P(A) + P(B|A<sup>-</sup>)P(A<sup>-</sup>)\
where the partition we used on the denominator was A,A<sup>-</sup>\
\
Independence\
&nbsp;- Two events A and B are independent iff P(AB) = P(A)P(B)\
&nbsp;- Mutually exclusive events cannot be independent\
&nbsp;- The impact on conditional probability\
&nbsp; &nbsp; P(A|B) = P(AB)/P(B) = P(A)P(B)/P(B) = P(A)\
&nbsp;- For N independent events\
&nbsp; &nbsp; P(A<sub>1</sub>A<sub>2</sub>...A<sub>N</sub>) = P(A<sub>1</sub>)P(A<sub>2</sub>)...P(A<sub>N</sub>)\
\
\
**Lecture 3: Random Variable Fundamentals**\
Random variable as a function:\
&nbsp;- function maps from domain to range\
&nbsp;- random varaible is a function that maps the outcome of a random experiment or process to a number\
&nbsp;- random experiment is conducted many times and each time is a trial\
&nbsp;- RV domain is the experimental outcome and RV range is the number the outcome is mapped to\
&nbsp;- experiment result is an outcome or a realization of the RV\
\
Continuous vs Discrete RV\
&nbsp;- discrete random variables: RVs with a countable number of outcomes\
&nbsp;- some experiments have results that can be mapped to any real number in either a closed or open interval => can use histograms by partition\
\
Probability density function (PDF)\
&nbsp;- The PDF of a random varaible X is denoted f<sub>X</sub>(x)\
&nbsp;- Example: a uniform distribution is the PDF of a RV where the numbers between a and b are equally likely\
&nbsp; &nbsp; f<sub>X</sub>(x) = 1/(b-a), a≤x≤b // 0, otherwise\
&nbsp;- Gaussian PDF: 1/(√2π<sup>2</sup>)exp[-(x-μ)<sup>2</sup>/2σ<sup>2</sup>]\
\
PDF properties:\
&nbsp;- A PDF is normalized to have unit area such that ∫<sub>-∞</sub><sup>∞</sup>f<sub>X</sub>(x)dx = 1\
&nbsp;- The probability of a single realization of X falls between x<sub>1</sub> and x<sub>2</sub>\
&nbsp; &nbsp; P(x<sub>1</sub> ＜ x ≤ x<sub>2</sub>) = ∫<sub>x<sub>1</sub></sub><sup>x<sub>2</sub></sup>f<sub>X</sub>(x)dx\
&nbsp;- The integral of a Gaussian PDF has no closed form solution but can be expressed in terms of the Q-function\
&nbsp; &nbsp; Q(x) = 1/√2π ∫<sub>x</sub><sup>∞</sup>e<sup>-y<sup>2</sup>/2</sup>dy\
&nbsp;- The Q-function can still be used for an arbitrary mean and variance\
&nbsp; &nbsp; P(X≥α) = 1/√(2π)σ ∫<sub>α</sub><sup>∞</sup>exp[-(x-μ)<sup>2</sup>/2σ<sup>2</sup>]dx\
&nbsp;- Let y = (x-μ)/σ so that dy = dx/σ\
&nbsp;- Limits: x=α becomes y=(α-μ)/σ and x=∞ is y=(∞-μ)/σ and x=∞ is y=(∞-μ)/σ=∞.\
&nbsp; &nbsp; P(X≥α) = 1/√(2π) ∫<sub>(α-μ)/σ</sub><sup>∞</sup>exp[y<sup>2</sup>/2]dy\
&nbsp; &nbsp; = Q((α-μ)/σ)\
\
PDF's for discrete RV's\
&nbsp;- the probability that a continuous RV takes on any specific value:\
&nbsp; &nbsp; P(X=x<sub>0</sub>) = ∫<sub>x<sub>0</sub></sub><sup>x<sup>0</sup></sup>f<sub>X</sub>(x)dx = 0\
&nbsp;- PDF of a discrete RV is made up of delta functions\
&nbsp; &nbsp; f<sub>X</sub>(x) = ∑P(X=x<sub>i</sub>)δ(x-x<sub>i</sub>)\
&nbsp;- discrete PDF can now be integrated\
&nbsp; &nbsp; P(X=1) = lim<sub>δ->0</sub> ∫<sub>1-δ</sub><sup>1+δ</sup>f<sub>X</sub>(x)dx\
&nbsp;- note that discrete RV's are also represented using probability mass functions (PMF's). These are simply functions that are only defined at discrete values such that p<sub>X</sub>(x<sub>i</sub>) = P(X = x<sub>i</sub>)\
\
Cumulative Distribution Functions\
&nbsp;- Also known as probability distribution functions\
&nbsp;- CDF directly yields a probability value\
&nbsp; &nbsp; F<sub>X</sub>(x) = P(X≤x)\
&nbsp;- Coin toss: F<sub>X</sub>(x) = 0, x＜0 // 0.5, 0≤x＜1 // 1, x≥1\
\
CDF properties:\
&nbsp;- F<sub>X</sub>(∞)=1 and F<sub>X</sub>(-∞)=0\
&nbsp;- The function is non-decreasing\
&nbsp;- For any x<sub>2</sub>＞x<sub>1</sub>, P(x<sub>1</sub>＜x≤x<sub>2</sub>) = F<sub>X</sub>(x<sub>2</sub>)-F<sub>X</sub>(x<sub>1</sub>)\
&nbsp; PDF and CDF related:\
&nbsp; &nbsp; f<sub>x</sub>(x) = dF<sub>X</sub>(x)/dx (PDF is derivative of CDF)\
&nbsp; &nbsp; F<sub>X</sub>(x) = ∫<sub>-∞</sub><sup>X</sup>f<sub>X</sub>(α)dα (CDF is integral of PDF)\
\
\
**Lecture 4: Moments of a Random Variable**\
Expected value:\
&nbsp;- expected value is the average of the numbers represented by a RV\
&nbsp;- it is equal to the first moment of PDF\
&nbsp; &nbsp; E{X} = ∫<sub>-∞</sub><sup>∞</sup>xf(x)dx\
&nbsp;- for discrete RV with a PDF that takes general form f(x)=∑p<sub>i</sub>δ(x-x<sub>i</sub>):\
&nbsp; &nbsp; E{X} = ∫<sub>-∞</sub><sup>∞</sup>x(∑p<sub>i</sub>δ(x-x<sub>i</sub>))dx\
&nbsp; &nbsp; &nbsp; =∑p<sub>i</sub>x<sub>i</sub>\
&nbsp;- expected value operation is linear. If X and Y are independent random variables and c is a constant, we can write\
&nbsp; &nbsp; E{X+Y} = E{X} + E{Y}\
&nbsp; &nbsp; E{cX} = cE{X}\
\
Functions of a random variable\
&nbsp;- if Y is the function of a random variable such that Y=g(X)\
&nbsp; &nbsp; E{Y} = ∫<sub>-∞</sub><sup>∞</sup>g(x)f(x)dx\
\
Variance and higher order moments\
&nbsp;- the nth order moment of an RV is defined as\
&nbsp; &nbsp; m<sub>n</sub> = E{X<sup>n</sup>} = ∫<sub>-∞</sub><sup>∞</sup>x<sup>n</sup>f(x)dx\
&nbsp;- variance is defined as:\
&nbsp; &nbsp; σ<sub>X</sub><sup>2</sup>\
&nbsp; &nbsp; = E{(X-μ)<sup>2</sup>}\
&nbsp; &nbsp; = E{X<sup>2</sup>} + E{-2μX} + E{μ<sup>2</sup>}\
&nbsp; &nbsp; = E{X<sup>2</sup>} - 2μE{X} + μ<sup>2</sup>\
&nbsp; &nbsp; = E{X<sup>2</sup>} - 2E{X}<sup>2</sup> + E{X}<sup>2</sup>\
&nbsp; &nbsp; = E{X<sup>2</sup>} - E{X}<sup>2</sup>\
&nbsp;- variance can be considered a function of RV written as z = g(x) = (x-μ)<sup>2</sup> so that\
&nbsp; &nbsp; σ<sub>X</sub><sup>2</sup> = ∫<sub>-∞</sub><sup>∞</sup>(x-μ)<sup>2</sup>f(x)dx\
\
Moment generating functions\
&nbsp;- moment generating functions are calculated as\
&nbsp; &nbsp; Φ(s) = Φ<sub>X</sub>(s) = ∫<sub>-∞</sub><sup>∞</sup>f<sub>X</sub>(x)e<sup>sx</sup>dx = E{e<sup>sX</sup>}\
&nbsp;- higher order moments are then calculated by\
&nbsp; &nbsp; d/dx Φ(s) = ∫<sub>-∞</sub><sup>∞</sup>f<sub>X</sub>(x)xe<sup>sx</sup>dx = E{Xe<sup>sX</sup>}\
&nbsp;- this can be extended to find the nth order moments\
&nbsp; &nbsp; d<sup>n</sup>/ds<sup>n</sup>Φ(s) = E{X<sup>n</sup>e<sup>sX</sup>}\
&nbsp; &nbsp; d<sup>n</sup>/ds<sup>n</sup>Φ(s)|<sub>s=0</sub> = E{X<sup>n</sup>}\
&nbsp;- Moment generating functions can also take the mean of a function of a random variable
