# Getting started 

## Compiling a CPP program 

Compiling involves taking source code we have written in `.cpp, .c,.h,.hpp` files and converting them to an executable that can run on a specific platform. The steps gone through to get a working executable are as follows

### 1. Pre-processing
--- * the preprocessor directives in cpp are identified with a `#` in front, they tell the compiler various instructions such as macros includes and conditional macros and pragmas to make it each to change and easy to compile in different environments

---  the pre-processing stage does all the actions defined by the preprocessor including macro substitution 
### 2. Compilation 

---  compiling converts the source code into assembly language,this assembly code is converted to machine code resulting in an intermediate file format called the object file.

---  many errors regarding syntax are found in this stage 

### 3. Linking 

---  this is the final stage which links up all the included libraries and files

