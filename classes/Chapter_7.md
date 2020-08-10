# Chapter 7 Classes

In C++ we use classes to define our own data types. This lets us define types that resemble
the actual real world problems that we are trying to solve. Classes are a fundamental concept
in Object oriented programming and help introduce data abstraction and encapsulation.

## this keyword

The this keyword is implicitly include for all data members and is of the type __const pointer 
to the non-static version of the class object__. For const member functions i.e functions 
which shouldn't be able to change the members of the objects, we can use a __const after the
parameter list__ to explicitly change the type of this pointer that is passed with the function
making it a const pointer to a const object thereby preventing any change in to the data members.

```cpp
	// Valid declaration of a const member function
	// Passes a const pointer to a const version of the class
	string id_read() const 
	{
		return this->id;
	}

	// Invalid declaration since we are redefinig this
	
	string id_read(const Data_entry *const this)
	{
		return this->id;
	}  


```

## Class scope and member functions

The definitions of data members and most member functions are done within the definition of 
the class and hence nested inside the class scope itself. While for within functions and other
blocks the scope of a variable begins from the point where it is declared to the end of the 
surrounding scope. __Within class definitions the compiler first processes all member declarations
and only then are the member function bodies processed.__Thus member functions can use members
of their class regardless of where in the class the members are defined.

```cpp
	// The following implementation is valid due to the order in which class definitions are processed
	class Data_entry
	{
		string name_read() const
		{
			return this->name;
		}
		string id_read() const
		{
			return this->id;
		}
		string name,id;
	}
```

### Defining member function outside the class

After declaring the member functions inside the class definition we can define the function
body. The definition must include it's class name using the scope operator and match its 
declaration signature exactly.

### Defining non-member class related functions

We can define auxiliary functions that help us to access the class interface but not exactly 
a part of it. This can be done like defining any other function. Keeping them in the same 
header file helps to sort it. The this keyword won't be available. The read and print functions
are good examples

```cpp

	istream &read(istream &is,Data_entry &item)
	{
		is >> item.name >> item.id;
		return is;		
		// We need to return to get the >> type of functionality which we can reuse
	}

	ostream &print(ostream &os,Data_entry &item)
	{
		os << item.name_read() << " " << item.id_read();
		return os;
	}

```






