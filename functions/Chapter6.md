#Functions 

## Function basics

A function is a block of code that is given a name and can be executed repeatedly, the 
function can take arguments and return a result. They can be overloaded and overridden.
In C++ the steps of a function are specified within the body, we execute a function using 
a call operator. The arguments are passed as comma separated list.

## Local objects

In C++ names have scopes and lifetimes, scope is the part of the programs text where the 
name is visible, the lifetime is the time during the programs execution that the object exists.

Objects defined in functions have a lifetime as long as the function is executing.

### Local static objects

You can define local variables whose lifetime continues across calls and it's value persists.

## Argument passing

Each time we call a function its parameters are created and initialized by the arguments 
passed in the call. When the parameter is a reference the argument is __passed by reference__
,i.e the parameter is bound to argument that is passed and becomes an alias for the passed
argument. When the arguments value is copied the parameter and argument are different and the
parameter is a copy of the argument. This is called __passed by value__.

As long as you're sure what you're going to do with a variable references make more sense
since they save you from the time and space overhead incurred from copying the arguments 
passed.

## Const parameters and arguments

We can use const on the parameters in different ways to control whether they can be changed
or assigned to. Adding a const to variable does not differentiate a function and does not
cause overloading.

It is recommended to use const references to parameters that you don't plan to change since
using normal references may confuse people who are going to use your function and they can't
pass const objects references to the function even though semantically you planned to allow
this.

## How values are returned

* The return value is used to initialize a temporary at the call site, and that temp is the result of the function call. 
* Because of this make sure you never return references or pointers to a object local to a function. 
* All functions with a return type must return a value before they terminate except the main which is an exception.
* Whether a function is an l-value or not depends on the return type.
* If the return type is a reference it is an l-value by default

### Returning a pointer to an array

Before looking at how to return arrays we'll have a look into different ways defining an array
```cpp 
int arr[10];			// arr is an array of ten ints
int *p1[10];			// p1 is an array of 10 pointers to ints
int (*p1)[10];			// p1 is a pointer that points to an array of ten ints
``` 
So a function that returns an array will have the following type `type (*func(par))[dim]`

### Using a trailing return type

Under C++ 11 we can use a new trailing return type where we can define the complicated 
return types after the parameter list
```cpp
auto func(int i,int j) -> int (*)[10];
```
This defines a function func that takes two int's and returns a pointer to an array of 10  ints, we can also use decltype to specify the return type.

## Overloaded functions

Functions that have the same name but different parameter lists and appear in the same scope
are said to be overloaded. Overloading is only done when the parameter lists are different 
else a compiler error is raised.
* top level consts on a type are not considered different
* const and nonconst references are considered different
