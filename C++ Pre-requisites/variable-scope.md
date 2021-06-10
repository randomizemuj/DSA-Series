# Variable Scope in C++
A scope is a region of the program and broadly speaking there are three places, where variables can be declared −

 * Inside a function or a block which is called local variables,
 * In the definition of function parameters which is called formal parameters.
 * Outside of all functions which is called global variables.

## Local Variables
Variables that are declared inside a function or block are local variables. They can be used only by statements that are inside that function or block of code. Local variables are not known to functions outside their own.  

## Global variables
They are defined outside of all the functions, usually on top of the program. The global variables will hold their value throughout the life-time of your program.
A global variable can be accessed by any function. That is, a global variable is available for use throughout your entire program after its declaration.  

## What if there exists a local variable with the same name as that of global variable inside a function?

If there is a variable inside a function with the same name as that of a global variable and if the function tries to access the variable with that name, then which variable will be given precedence? Local variable or Global variable? Look at the following program to understand the question:  

**Input:**
```cpp
#include <iostream>
using namespace std;
 
// Global variable declaration:
int g = 20;
 
int main () {
   // Local variable declaration:
   int g = 10;
 
   cout << g;
 
   return 0;
}

```
**Output:**
`10`  

So whenever there is a local variable defined with same name as that of a global variable, _the compiler will give precedence to the local variable_.  

## How to access a global variable when there is a local variable with same name?
To solve this problem we will need to use the scope resolution operator.  
**Input:**

```cpp
#include<iostream> 
using namespace std;
   
// Global x  
int x = 0;  
    
int main()
{
  // Local x    
  int x = 10; 
  cout << "Value of global x is " << ::x;
  cout<< "\nValue of local x is " << x;  
  return 0;
}
```

**Output:**  
`Value of global x is 0
Value of local x is 10`

---

> To learn more about the scope of variables, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/scope-of-variables-in-c/), [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_variable_scope.htm)
