---
title: "Data Structures"
date: 2021-06-19 14:09 -0400
categories: Data_Structure
---
**Chpater 1 A C++ Primer**
\
**1.1 Basic C++ Programming Elements**\
\
**1.1.1 A Simple C++ Program**\
\
Steps for running C++ program\
1) create a c++ source file\
2) run a compiler\
3) run a linker (typically invoked by the compiler)\
=> includes any required library code functions needed and produces the final executable file\
```C++
#include <cstdlib>
#include <iostream>

int main() {
  int x, y;
  std::cout << "Please enter two number: ";
  std::cin >> x >> y;
  int sum = x + y;
  std::cout << "There sum is " << sum << std::endl;
  return EXIT_SUCCESS;
}
```
&nbsp;- Comments are indicated with two slashes (//)\
&nbsp;- Longer block comments are enclosed between /* */ \
&nbsp;- Operators >> and << are used for input and output\
\
&nbsp;- Lines 1 and 2 input *header files* cstdlib and iostream\
&nbsp; &nbsp; cstdlib : standard system definitions\
&nbsp; &nbsp; iostream : definitions for input and output\
\
&nbsp;- Initial entry point is the function *main*\
&nbsp; By convention, main function returns 0 to indicate success and returns a nonzero value to indicate failure\
&nbsp; EXIT_SUCCESS\
\
&nbsp;- Function body is given within {}\
&nbsp;- std::cout : standard output stream\
&nbsp;- std::cin : standard input stream\
&nbsp;- std::cerr : standard error\
&nbsp;- std:: : the objects are from the system's *standard library*\
&nbsp;- can omit the prefix by *using*\
```C++
#include <iostream>
using namespace std;

cout << "Please enter two numbers: ";
cin >> x >> y;
```
**1.1.2 Fundamental Types**\
&nbsp;- Integral Types\
&nbsp;&nbsp;- enum:    a set of discrete values\
&nbsp;&nbsp;- bool:    boolean, either true or false\
&nbsp;&nbsp;- char:    character\
&nbsp;&nbsp;- int:     integer\
&nbsp;- short:     short integer\
&nbsp;- long:      long integer\
&nbsp;- float:     single-precision floating-point number\
&nbsp;- double:    double-precision floating-point number\
&nbsp;- void:      absence of type\
\
*Characters*\
&nbsp;- holds a single character\
&nbsp;- typically 8-bits, but can be modified by C++'s flexibility\
&nbsp;- literal : a constant value enclosed in single quotes\
&nbsp; * special character literals (with \) :\
&nbsp; &nbsp; '\n'  newline\
&nbsp; &nbsp; '\t'  tab\
&nbsp; &nbsp; '\b'  backspace\
&nbsp; &nbsp; '\0'  null (also indicate the end of a string of characters)\
&nbsp; &nbsp; '\''  single quote\
&nbsp; &nbsp; '\"'  double quote\
&nbsp; &nbsp; '\\'  backslash\
&nbsp;- every character is associated with an integer code\
&nbsp;=> int(ch) returns it\
\
*Integers*\
&nbsp;- holds an integer\
&nbsp;- three sizes : short int (short), int (int), long int (long)\
&nbsp; * suffixes l or L can be added to make a long integer (ex: 12345L)\
&nbsp;- Octal (base 8) constants : prefixing number with zero digit (256 -> 0400)\
&nbsp;- Hexadecimal (base 16) constants : prefixing the number with 0x (256 -> 0x100)\
&nbsp;* When declaring a variable, we can provide a *definition* or initial value. If not, the initial value is unpredictable.\
&nbsp;* Rules for Variable names: may consist of letters, digits, underscores first character cannot be a digit it is better to avoid underscore as first char because some C++ compilers use this to define\
&nbsp;- short is at least 16 bits, long is at least 32 bits\
&nbsp;- sizeof(T) returns the size of type T, expressed as multiples of size of char\
&nbsp; &nbsp; ex) if char is 8 bits, int is 32 bits => sizeof(int) == 4\
\
*Enumerations*\
&nbsp;- a user-defined type that can hold any of a set of discrete values\
&nbsp;- int-like behavior\
&nbsp;- each element of an enumeration is associated with an integer value\
&nbsp;- conventionally write enumerations with capital letters\
```C++
enum Day { SUN, MON, TUE, WED, THU, FRI, SAT }; // no specification; SUN would be 0, MON, would be 1
enum Mood { HAPPY = 3, SAD = 1, ANXIOUS = 4, SLEEPY = 2 };  

Day today = THU;
Mood myMood = SLEEPY;
```
*Floating Point*\
&nbsp;- float holds a single-precision floating-point number\
&nbsp;- double holds a double-precision floating-point number\
&nbsp;- mostly double by default\
To force a literal to be a float, add suffix f or F (ex: 2.0f)\
\
\
**1.1.3 Pointers, Arrays, and Structures**\
\
*Pointers*\
&nbsp;- each variable is stored at some address\
&nbsp;- pointer is a variable that holds the value of an address\
&nbsp;- Given type T, the type T* denotes a pointer to a variable of type T\
&nbsp;- & (address-of operator) : returns the address of an object\
&nbsp;- * : access an object's value from address (dereferencing)\
&nbsp;- null pointer : points to nothing, assigned the value zero, dereferncing results in a runtime error\
&nbsp;- NULL : activated by #include cstdlib\
&nbsp;- cannot declare void variable, but can declare void* variable. it can point to a variable of any type, but it is discouraged due to absence of compiler check\
\
*Arrays*\
&nbsp;- a collection of elements of the same type\
&nbsp;- T[N] holds an array of N elements with type T\
&nbsp;- elements are referenced by its index (0 - N-1)\
&nbsp;- once declared, cannot increase the number of elements in an array\
&nbsp;- can initialize by indicating values then the compiler figures the size out\
&nbsp;- can declare an array of pointers\
&nbsp; &nbsp; ex: int* r[17] declares an array of r consisting of 17 pointers to int\
&nbsp; &nbsp; * r[16] ix the value of the integer pointed by last element\
\
*Pointers and Arrays*


