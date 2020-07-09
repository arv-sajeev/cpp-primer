# Chapter 3 Strings, Vectors and arrays

In addition to the primitive built-in types defined in C++ the standard library defines a
number of higher level types. String and Vectors are types which are implemented by the
STL.

## Library string type

A string is a variable length sequence of characters. It is in the string library.
It is defined in the std namespace.
strings in c++ are mutable, string literals are not though

### Defining and Initializing strings

Like any other class there are multiple ways to initialize a string object.
* default initialization 	- `string s1;` initialized as an empty string
* copy initialization 		- `string s2 = s1` s2 is a copy of s1 s1 can be a literal
* direct initialization 	- `string s3(s1)` s1 is a copy of s1 
* direct with repeat		- `string s3(10,<character>)` s3 is char repeated 10 times

### Operations of strings

* `<<` and `>>` for input and output regarding streams, reads whitespace separated strings
* `getline(<stream>,<var>)` reads line of input from is to s
* `s.empty()` checks if the given string is empty
* `s.size()` the number of characters in s
* [] to reference characters
* + to concatenate strings
* = to copy strings
* == to check character wise equality that is case sensitive
* !=, <, <=, > >= comparison is case sensitive and based on dictionary ordering

The size returned by s.size() is of the type `string::size_type` which is a implementation 
defined unsigned type. So be careful when you use int instead of unsigned it may lead to 
confusion.

It would be good practise to use decltype(s.size()) to define index while traversing thorugh
a string. 

When adding two string or literals we have to be sure to have at least one operand as a 
literal. This is because literal and strings are treated completely differently to give
compatibility with cstrings.

### C library headers for C++

Headers in C have the form `library.h` to use these it is advised to include the clibrary 
named version for the same libraries which are optimised for C++ and found in std namespace


