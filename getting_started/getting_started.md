# Getting started 

## Compiling a CPP program 

Compiling involves taking source code we have written in `.cpp, .c,.h,.hpp` files and converting them to an executable that can run on a specific platform. The steps gone through to get a working executable are as follows

### 1. Pre-processing
* the preprocessor directives in cpp are identified with a `#` in front, they tell the compiler various instructions such as macros includes and conditional macros and pragmas to make it each to change and easy to compile in different environments

* the pre-processing stage does all the actions defined by the preprocessor including macro substitution 
### 2. Compilation 

* compiling converts the source code into assembly language,this assembly code is converted to machine code resulting in an intermediate file format called the object file.

* many errors regarding syntax are found in this stage 

### 3. Linking 

*  this is the final stage which links up all the included libraries and files


## I/O

* the cpp standard library provides I/O using the iostream library using the istream and ostream, the stream is intended to suggest that the characters are generated or consumed sequentially over time.

* the 4 standard stream objects are cin, cout, clog and cerr

### Writing to a stream

* the `<<` operator takes two operands the left-hand operand must be an ostream
* the operator writes the given value to the left hand operand and then returns the left hand operand 
* the `endl` which is a special value called a manipulator, it ends the current line and flushes the buffer associated with the device making sure the output is actually written to the stream, rather than sitting to be written

### Reading from a stream

* the `<<` output operator it takes two operands the left-hand operand must be an istream
* writes the value on the stream to the variable on the right, and return the stream.
* an istream becomes invalid when we hit end-of-file
