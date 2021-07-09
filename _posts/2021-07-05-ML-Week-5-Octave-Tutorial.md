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
>> hist(w)
>> hist(w,50) % histogram with 50 bars

% eye: identity matrix
>> I = eye(3)
I =
    1   0   0
    0   1   0
    0   0   1

% help: documentation for functions
>> help rand
```
\
\
**5.2 Moving Data Around**
```Octave
% size
>> A = [1 2; 3 4; 5 6];
>> size(A)
ans =
  3   2

>> sz = size(A);
>> size(sz)
ans =
  1   2

>> size(A,1)  % the size of 1st dimension
ans = 3
>> size(A,2)  % the size of 2nd dimension
ans = 2

% length
>> v = [1 2 3 4];
>> length(v)
ans = 4
>> length(A)  % length of the longest dimension
ans = 3
>> length([1;2;3;4;5])
ans = 5

% pwd
>> pwd  % directory
ans = C:\...

% ls
>> ls % files in current directory

% load
>> load featuresX.dat
>> load('featuresX.dat')  % equivalent

% who
>> who  % shows variables in current scope
>> whos % shows variables in current scope with more details

% save
>> save hello.mat v;
>> save hello.txt v;
>> save hello.txt v -ascii  % save as ASCII text

% clear
>> clear  % remove variables

% get with index 
>> A = [1 2; 3 4; 5 6]
ans =
  1   2
  3   4
  5   6
>> A(3,2)
ans = 6
>> A(2,:)   % ":" means every element along that row/column
ans =
  3   4
>> A(:,2)
ans =
  2
  4
  6
>>A([1 3], :)
ans =
  1   2
  5   6
>> A(:,2) = [10; 11; 12]
A =
  1   10
  3   11
  5   12
>> A = [A, [100; 101; 102]]   % append another column vector
  1   10    100
  3   11    101
  5   12    102
>> A(:) % put all elements of A into a single vector

% matrix of matrices
>> C = [A B]
>> C = [A, B]   % equivalent
>> C = [A; B]
```
\
\
**5.3 Computing on Data**
```Octave
>> A = [1 2; 3 4; 5 6];
>> B = [11 12; 13 14; 15 16];
>> C = [1 1; 2 2];

>> A * C    % matrix multiplication
>> A .* B   % elements multiplcation
>> A .^ B
>> 1 ./ A
>> log(A)   % logarithm
>> exp(A)   % e
>> abs(v)   % absolute value
>> A'       % transpose
>> max(A)   % get max value for each column/vector
>> [val, ind] = max(A)    % get value and index of max value
>> A < 3    % prints boolean values of each element
>> (A < 3)  % prints indices of elements that satisfy the condition
>> magic(3) % sets magic matrix: sum of elements of every row and column is same
>> [r, c] = find(A >= 7)  % gets row index and column index of elements satisfying the condition
r =
  1
  3
  2
c =
  1
  2
  3
>> sum(A)         % sum of all elements in A
>> prod(A)        % product of all elements in A
>> floor(A)       % round down all elements in A
>> ceil(A)        % round up all elements in A
>> max(A,[],1)    % get max value columnwise
>> max(A,[],2)    % get max value rowwise
>> max(max(A))    % get max value in the matrix
>> max(A(:))      % equivalent
>> sum(A,1)       % sum of column elements
>> sum(A,2)       % sum of row elements
>> A .* eye(3)    % wipes out every matrix and only leaves diagonal elements
>> sum(sum(A.*eye(3)))  % sum of diagonal elements
>> flipud(eye(3)) % reverse diagonal identity matrix
>> pinv(A)        % inverse matrix
>> pinv(A) * A    % identity matrix
```
\
\
**5.4 Plotting Data**
```Octave
>> plot(a,b);       % shows the graph using a as x axis and b as y axis
>> hold on;
>> plot(c,d,'r');   % shows both graph and shows c,d with red color
>> xlabel('time')   % mark x axis with time
>> ylabel('value')  % mark y axis with value
>> legend('sin', 'cos')  % display names of the lines
>> title('my plot') % set title of the plot
>> print -dpng 'myplot.png' % save as png file
>> cd 'C:\Users....'; print -dpng 'myplot.png'  % another directory
>> close  % closes the plot
>> figure(1); plot(t,y1);
>> figure(2); plot(t,y2); % plot another figure
>> subplot(1,2,1);  % divides plot into a 1x2 grid and ready to set first plot
>> axis([0.5 1 -1 1]) % set x axis range 0.5-1.0 / y axis range -1.0-1.0
>> clf;         % erases the contents in current screen
>> imagesc(A)   % shows A as colored grid
>> imagesc(A), colorbar, colormap gray;
    % colorbar: shows a bar that matches number and color
    % colormap gray: display as black and white
>> a=1, b=2, c=3    % 3 commands in one line
>> a=1; b=2; c=3;   % equivalent but no output
```
\
\
**5.5 While If Statements and Functions**
```Octave
% For loop
>> for i=1:10,  % indentation doesn't matter
>    v(i) = 2^i;
>  end;

>> indices=1:10;
>> for i=indices,   % also possible
>    disp(i);
>  end;

% While
>> i = 1;
>> while i <= 5;
>     v(i) = 100;
>     i = i+1;
>  end;
>> v

>> i=1;
>> while true,
>     v(i) = 999;
>     i = i+1;
>     if i == 6,
>       break;
>     end;
>  end;

% if else
>> if v(1) == 1,
>     disp('The value is one');
>  elseif v(1) == 2,
>     disp('The value is two');
>  else
>     disp('The value is not one or two.');
>  end;

% defining functions

% File "squareThisNumber.m"
function y = squareThisNumber(x)
y = x^2;

>> squareThisNumber(5)
ans = 25

% search path
>> addpath('C:\Users...') % where sqaureThisNumber.m is located
>> cd 'C:\'               % another directory
>> squareThisNumber(5)    % still works!

% two return values

% squareAndCubeThisNumber.m
function [y1,y2] = squareAndCubeThisNumber(x)
y1 = x^2;
y2 = x^3;

>> [a,b] = squareAndCubeThisNumber(5)
a = 25
b = 125

% Goal: Define a function to compute the cost function J(Θ)
>> X = [1 1; 1 2; 1 3]
X =
  1   1
  1   2
  1   3

>> y = [1; 2; 3]
y =
  1
  2
  3

% costFunctionJ.m
function J = costFunctionJ(X, y, theta)
m = size(X,1);          % number of training examples
predictions = X*theta;  % predictions of hypothesis on all m examples
sqrErrors = (predictions-y).^2;   % squared errors
J = 1/(2*m) * sum(sqrErrors);

>> j = costFunctionJ(X, y theta)
```
\
\
**5.6 Vectorization**
```Ocatve
% Unvectorized implementation
prediction = 0.0
for j = 1:n+1,
  prediction = prediction + theta(j) * x(j)
end;

% Vectorized implementation
prediction = theta` * x;  % much more efficient, simpler
```
