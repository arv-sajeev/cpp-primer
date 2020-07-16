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

## Library vector type

A vector unlike a string is not just a class but is a class template, which are basically
instructions for creating functions and classes for different types. These are then instantiated by the compiler for each given type.

In vector the info we provide to the template is the type of the objects that the vector 
will hold.

### Defining and Initializing vectors

* default initialize a vector - `vector <"type"> name` will be empty
* copy initialize a vector 1  - `vector <"type"> name(other_vec) copy element from other_vec
* copy initialize a vecotr 2  - `vector <"type"> name = other-vec same as above

While copy initializing vectors the type need to match or error will be thrown.

* List initializing `vector <type> name = { <e1>,<e2> .... <e3> }`
* you can specify the number of elements using `vector <type> name(<num>,<el>)`
* Some classes that cannot be default initialized need have an explicit initial value provided
* {} is used to pass initial values, () is used to pass number followed by one initial value
* in cases where the value in {} can only be used as number of objects it is done so for e.g vector of strings

### Adding elements to a vector 

* using the `push_back` method to add the new element to the back of the vector
* the vector is usually allocated extra space so it can grow efficiently
* when this space is overflowed as well 
* we can use the for range operator on vectors for (auto &i : v)
* subscripting cannot add elements it can only modify or access


## Introducing Iterators

Is a mechanism to access sequential containers, the containers have methods called 
begin() and end() which are used to return their iterator 
* begin() returns the iterator to the first element if there is one
* end() returns an iterator just off the end of the container which can be used to check of overflow
* iterators have to be dereferenced using * to obtain the element they point to
* it also has the -> operator to dereference the members of the element pointed to by the iterator
* `const_iterator` is used to provide read only access to the elements it points to 
* each iterator also has a type that it points to vector <int> iterators only point to vector <int> objects

### Iterator arithemetic

* adding or subtracting an integral value to an iterator yield an iterator that is that many elements forward or backward within the container from the present iterator
* all relational operators work based on the position the iterators have within the container

## Arrays

Arrays are sort of the static version of vectors, they have fixed size and hence have less 
flexibility but they have much higher performance and space saving.
* they can be initialized with a size described by a constexpr
* or they can be explicitly initialised with their values
* when initializing char arrays from string literals remember to leave space for the null in the end
* we cannot initialize an array as a copy of another like in vectors

### Pointer arithmetic

* when we add or subtract an integer the address moved depends on the size of the object pointed to
* we can only use relational operators on pointers that are related to each other. 

