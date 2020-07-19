# Chapter 4 - Expressions

An expression is a combination one or operands and operators that yield a result when 
evaluated.

## Basic concepts

Operators can be classified based on the number of operators they take
* unary like & and *
* binary like arithmetic and relational operator
* ternary that takes three
* the functional call that takes three operators

### L-values and R-values

Every expression in C++ is either an r-value or an l-value, this concept in c meant values 
that could be on the left-side of an assignment operator. In C++ in addition there are much 
more subtleties.

* In C++ an l-value expression yields an object or function, however l-values like const objects cannot be on the left side of an assignment operator.
* some expression that yield objects return them as r-values and not r-values. 
* when we use an object as an r-value we use it's contents, when we use an object as an l-value. 
* operators differ based on whether they require l-value or r-value operands and what they return. We can use lvalue where an rvalue is required almost everywhere but not the other way.
* assignment requires a non-const l-value as it its left hand operator
* the address operator requires an l-value
* the builtin and dereference operators all yield lvalue
* iterator increment and decrement operators require and yield l-value 
* decltype results on the type of the operand

### Precedence and associativity

An expression with two or more operators in called a compound expression. Evaluating a 
compound expression needs grouping the operands to operators. Precedence and associativity
rules determine how operands are grouped. These rules can be overridden using parentheses.
* multiplication and division have higher precedence over addition and subtraction 
* arithmetic operator are left associative, i.e group from left to right
* parentheses can be used to override the above precedence and associativity
* the assignment operator is one of the only right associative operators and requires a modifiable l-value.

### Order of evaluation 

Precedence and associativity decide which operands and operators are to be grouped together
they do not specify which parts of the expression are to be evaluated first.

In C++ and C presumably only 4 operators are guaranteed to have and order
* && the logical and operator also support short circuit evaluation the second operator is only evaluated if the first operand is truthy
* || same as above short circuit only if first value is falsey
* ternary conditional operator
* , separated operators are evaluated sequentially from left to right

For all other operators and functions referring to and changing the same object in the same
expression may result in an error and leads to an undefined state.

### Bitwise operators

* if operand is a small integer its value is first promoted
* the lh can be signed or unsigned, the rh cannot be negative.
* for left shift the left most bits are discarded and rightmost are 0
* for right shift the left most depend on the sign of the value and is implementation specific
* they are left associative

### Sizeof operator

* it takes two forms `sizeof(<type_name>)` or `sizeof <expression>`
* it is right associative
* it can be used of references
* on dereferenced pointers

## Type conversions

Some types in c++ are related to each other we can use objects of objects in place of objects
of their related type. In some cases conversions are specified by the compiler to use these
replacement objects this is called implicit conversion.
* in most expressions values of integral types smaller than int are converted to larger integral types
* conversion from nonbool to bool
* value of initializers  are converted to that of the lh

## Explicit conversions

* `static_chast` is used for well defined type conversion other than low-level const
* `const_cast` is used for changing low-level const
* old style casts type (expr) (type) expr
* 
