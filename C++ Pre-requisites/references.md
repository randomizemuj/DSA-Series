# References in C++

A reference variable is an alias, that is, another name for an already existing variable. Once a reference is initialized with a variable, either the variable name or the reference name may be used to refer to the variable.

## References vs Pointers

References are often confused with pointers but three major differences between references and pointers are −

-   You cannot have NULL references. You must always be able to assume that a reference is connected to a legitimate piece of storage.
    
-   Once a reference is initialized to an object, it cannot be changed to refer to another object. Pointers can be pointed to another object at any time.
    
-   A reference must be initialized when it is created. Pointers can be initialized at any time.
    

## Creating References in C++

Think of a variable name as a label attached to the variable's location in memory. You can then think of a reference as a second label attached to that memory location. Therefore, you can access the contents of the variable through either the original variable name or the reference. For example, suppose we have the following example −

```int i = 17;```

We can declare reference variables for i as follows.

```int& r = i;```

Read the & in these declarations as  **reference**. Thus, read the first declaration as "r is an integer reference initialized to i" and read the second declaration as "s is a double reference initialized to d.". Following example makes use of references on int and double −

```
#include  <iostream>

using  namespace  std;

int  main  ()  {

// declare simple variables

int i;

double d;

// declare reference variables

int& r = i;

double& s = d;

i =  5;

cout <<  "Value of i : "  << i << endl;

cout <<  "Value of i reference : "  << r << endl;

d =  11.7;

cout <<  "Value of d : "  << d << endl;

cout <<  "Value of d reference : "  << s << endl;

return  0;

}
```

When the above code is compiled together and executed, it produces the following result −
```
Value of i : 5
Value of i reference : 5
Value of d : 11.7
Value of d reference : 11.7
```
References are usually used for function argument lists and function return values. So following are two important subjects related to C++ references which should be clear to a C++ programmer −

|Sr.No |Concept & Description|
|--|--|
|1|[References as Parameters](https://www.tutorialspoint.com/cplusplus/passing_parameters_by_references.htm "Passing parameters by references in C++") C++ supports passing references as function parameter more safely than parameters.|
|2|[Reference as Return Value](https://www.tutorialspoint.com/cplusplus/returning_values_by_reference.htm "Returning values by reference in C++") You can return reference from a C++ function like any other data type.|

> For more information, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/references-in-c/)