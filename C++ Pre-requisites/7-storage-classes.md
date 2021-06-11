# Storage Classes in C++

A storage class defines the scope (visibility) and life-time of variables and/or functions within a C++ Program. These specifiers precede the type that they modify. There are following storage classes, which can be used in a C++ Program

 1. auto
 2. register
 3. static
 4. extern
 5. mutable

---

## The auto Storage Class

The auto storage class is the default storage class for all local variables.

```cpp
{
   int mount;
   auto int month;
}
```
The example above defines two variables with the same storage class, auto can only be used within functions, i.e., local variables.

---

## The register Storage Class

The register storage class is used to define local variables that should be stored in a register instead of RAM. This means that the variable has a maximum size equal to the register size (usually one word) and can't have the unary '&' operator applied to it (as it does not have a memory location).

```cpp
{
   register int  miles;
}
```

The register should only be used for variables that require quick access such as counters. It should also be noted that defining 'register' does not mean that the variable will be stored in a register. It means that it MIGHT be stored in a register depending on hardware and implementation restrictions.

---

## The static Storage Class

This storage class is used to declare static variables which are popularly used while writing programs in C++ language. Static variables have a property of preserving their value even after they are out of their scope! Hence, static variables preserve the value of their last use in their scope. So we can say that they are initialized only once and exist until the termination of the program. Thus, no new memory is allocated because they are not re-declared. Their scope is local to the function to which they were defined. Global static variables can be accessed anywhere in the program. By default, they are assigned the value 0 by the compiler.  
**Input:**

```cpp
#include <iostream>
using namespace std;
 
// Function containing static variables
// memory is retained during execution
int staticFun()
{
    cout << "For static variables: ";
    static int count = 0;
    count++;
    return count;
}
 
// Function containing non-static variables
// memory is destroyed
int nonStaticFun()
{
    cout << "For Non-Static variables: ";
 
    int count = 0;
    count++;
    return count;
}
 
int main()
{
 
    // Calling the static parts
    cout << staticFun() << "\n";
    cout << staticFun() << "\n";
    ;
 
    // Calling the non-static parts
 
    cout << nonStaticFun() << "\n";
    ;
    cout << nonStaticFun() << "\n";
    ;
    return 0;
}
```

**Output:**  
```
For static variables: 1
For static variables: 2
For Non-Static variables: 1
For Non-Static variables: 1
```
---
## The extern Storage Class

The extern storage class is used to give a reference of a global variable that is visible to ALL the program files. When you use 'extern' the variable cannot be initialized as all it does is point the variable name at a storage location that has been previously defined.

When you have multiple files and you define a global variable or function, which will be used in other files also, then extern will be used in another file to give reference of defined variable or function.   

First File: main.cpp
```cpp
#include <iostream>
int count ;
extern void write_extern();
 
main() {
   count = 5;
   write_extern();
}
```
Second File: support.cpp

```cpp
#include <iostream>

extern int count;

void write_extern(void) {
   std::cout << "Count is " << count << std::endl;
}
```
Here, extern keyword is being used to declare count in another file. Now compile these two files as follows −

`$g++ main.cpp support.cpp -o write`

---
## The mutable Storage Class

Sometimes there is a requirement to modify one or more data members of class/struct through const function even though you don’t want the function to update other members of class/struct. This task can be easily performed by using the mutable keyword. The keyword mutable is mainly used to allow a particular data member of const object to be modified. When we declare a function as const, this pointer passed to function becomes const. Adding mutable to a variable allows a const pointer to change members.

---

> For more information on storage classes, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/storage-classes-in-c-with-examples/), [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_storage_classes.htm)
