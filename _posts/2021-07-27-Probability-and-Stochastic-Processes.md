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
&nbsp; &nbsp;- The complement of A (A<sup>-</sup>) defines a second set that contains all teh elements in S that are not in A\
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
**Lecture 2: The Axioms of Probability & Conditional Probability**



