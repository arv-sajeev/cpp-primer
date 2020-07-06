# Variables and types 

* C++ is a statically typed langauge, i.e type checking is done during compile time.
* addition with of signed with and unsigned leads to an unsigned with the signed being converted to signed
* unsigned will never become < 0 so take care of that when using it is conditional expressions
* try your best never to mix signed and unsigned

## Literals

They have a value which is self evident
* integer and floating point literals, 0 infront for octal 0x for hex
* '' is used for character literal "" for a string literala
* null is appended after every string literal and is stored in the code segment
* adjacent literals separated just by white spaces are implicitly concatenated

## Variables

a variables provides us with a named storage which our programs can manipulate, the type
decides the size and layout of the variables memory.

### Variable definitions 

A simple variable consists of a type specifier followed by a list of one or more var names
separated by commas and ends with a semicolon. The definition may include an initial value.

#### Different forms of initialization 

* `int a = 0;`		larger to lower type is allows but truncation will occur
* `int a = {0};` 	not allowed	also called list initialisation 
* `int a{0};`		not allowed	also called list initialisation 
* `int a(0);`		larger to lower type is allows but truncation will occur

#### Default initialization 

When variables are defined without an initializer the compiler usually gives them default 
values depending on the type and location of the variable defined
* variables defined outside a body are initialized to zero
* inside function are left undefined and error rises on copying or referencing it
* classes can define default initialization for objects

#### Variable declaration vs definitions
Programs in C++ can be written is separate files and compiled separately and then linked
to a single object file __separate compilation__ , To support using objects defined in other
files and separate compilation, we need to split the process of declaring and defining.

* a declaration declares a name 
* a definition created the entity i.e assigns memory
* any declaration that includes an explicit initializer is considered a definition even if an extern is associated with it 
* the names for variables must begin with a letter or underscore and can contain alphanumeric
* you can't use keywords or alternative op names like and or xor

### Scope of a name
A name is visible from the point they are declared to the end of the scope, no hoisting like
javascript.
* names defined outside functions have a global scope
* variables usually have a block scope, with blocks defined by curly brackets or paranthesis
* names reused in nested scopes hide their outer definitions

## Compound types
a compound type is a type that is defined in terms of another type references and pointers
are considered compound types.

### References 

A reference is an alternative name for an object, when a variable is assigned to a reference
instead of being copied it is bound to the reference. Any changes made to the reference will
be reflected in the original object as well.

* a reference can only bind to an object of the same type
* it cannot be bound to a literal or the result of a more general expression 
* you can't make a reference to a reference since references are not objects
* a reference cannot be uninitialized

### Pointers

A pointer is a compound type that points to another type. Unlike a reference it is an object
it can be copied assigned many times and can be left uninitialized.
* we can get the address of an object using the `&` operator
* pointers are defined by using the `*` operator saying that dereferencing this object will give an object of the given type
* pointers can be assigned addresses of objects
* a pointer can point to an object
* location just past an object, 
* to a null pointer
* any other value is invalid and will raise an error
* in cpp instead of `NULL` a `nullptr` is used to use `NULL` we need to include cstdlib

#### void pointers

This is a special pointer that can hold the address of any object. It hold the address of
any object, put the type of the object will be unknown. We can only do limited thing on a 
void pointer -
* pass or return from a function 
* assign to another void pointer
* compare to another pointer
* to do any other operation we should cast to a pointer of a valid type

### Pointers to pointers

There are no limits to how many levels of indirection in pointers.
* we can have a reference to a pointer
* we can't have a pointer to a reference since it is not an object

## The const qualifier

We usually use const to prevent changing the value of a variable once it is assigned. Since 
we can't change the value in C++ we need to initialize a const variable
* const objects are local to a file by default
* they are usually replaced by their value by preprocessors
* we can make it available across multiple files by using extern even in the ***definition*** and declaration 

### References to const

Like any other object we can bind references to a const object 
* the const property still applies to the reference to the const, 
* you can't  assign a non-const reference to a const object
* the reference must have const in it's declaration as well
* we can use a cost reference to bind to a non-const object but this ref can't be used to make changes

### Pointers and const

This stuff is quite confusing use the spiral rule to find what the declaration means.

#### pointer to const

Stuff defined like `const <type> *<var-name>` is a pointer to a constant of the specified type
* Changing the value of the object pointed to is illegal. i.e. you can't dereference then assign to it
* you can still change the reference the object is made to.
* also called low level const

#### const pointer

Things that are defined like `<type> * const <var-name>`
* Changing the object that is referenced by the variable is illegal
* you can change the contents of the object referenced by the variable
* also called top level const

### constexpr and Constant expressions
A constant expression is an expression whose value cannot change and can be calculated at
compile time. 

* A literal is a constant expression 
* a const that is initialized by a constant expression  is a constant expression 

We use it to make sure that the const's that we define are initialized by a constant expression.

* we can only on define constexpr pointers to objects that we know will not change

