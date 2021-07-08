---
title: "ML Week 5 Octave Tutorial"
date: 2021-07-07
categories: "Octave"
---
**5.1 Basic Operations**

```octave

% addition
5+6
ans = 11

% subtraction
3-2
ans = 1

% multiplication
5*8
ans = 40

% division
1/2
ans = 0.50000

% power
2^6
ans=64

% equal
1 == 2
ans = 0

% not equal
1 ~= 2
ans = 1

% and
1 && 0
ans = 0

% or
1 || 0
ans = 1

% exclusive or
xor(1,0)
ans = 1

% change prompt
PS1('>> ');
>>

% number assignment
>> a = 3
a = 3
>> a = 3;  % semicolon supresses output
>> a
a = 3

% string assignment
>> b = 'hi';
>> b
b = hi

% boolean assignment
>> c = (3 >= 1);
>> c
c = 1

% pi assignment
>> a = pi;
>> a
a = 3.1416

% display
>> disp(sprintf('2 decimals; %0.2f', a))
2 decimals: 3.14
>> a
a = 3.1416
>> format long
>> a
a = 3.14159265358979
>> format short
>> a
a = 3.1416

% matrix assignment
>> A = [1 2; 3 4; 5 6]
A =
  1   2
  3   4
  5   6

% vector assignment
>> v = [1 2 3]
v =
  1   2   3
>> v [1; 2; 3]
v =
  1
  2
  3

% colon notation
>> v = 1:0.1:2;  % iterates +0.1 from 1 to 2
>> v = 1:6
  1   2   3   4   5   6

% ones
>> ones(2, 3)
ans =
    1   1   1
    1   1   1
>> C = 2 * ones(2, 3)
C =
    2   2   2
    2   2   2

% zeros
>> zeros(1,3)
w =
    0   0   0

% rand
>> rand(3,3)  % 3x3 random values

% randn (random numbers from normal distribution)
>> randn(1,3)

% hist: construct histogram
hist(w)
