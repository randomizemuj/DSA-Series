# Variable Definition in C++
A variable provides us with _named storage_ that our programs can manipulate. Each variable in C++ has a specific type, which determines the size and layout of the variable's memory; the range of values that can be stored within that memory; and the set of operations that can be applied to the variable.  

**Syntax:**  
```type variable_list;```  
Here, **type** must be a valid C++ data type including char, w_char, int, float, double, bool or any user-defined object, etc., and **variable_list** may consist of one or more identifier names separated by commas.  

---
# Variable Declaration in C++

A variable declaration provides assurance to the compiler that there is one variable existing with the given type and name so that compiler proceed for further compilation _without needing complete detail about the variable_. A variable declaration has its meaning at the time of compilation only, compiler needs actual variable definition at the time of linking of the program.
It is useful when you are using multiple files and you define your variable in one of the files which will be available at the time of linking of the program. You will use extern keyword to declare a variable at any place. Though you can declare a variable multiple times in your C++ program, but it can be defined only once in a file, a function or a block of code.

---

# Variable Initialization
Variables can be initialized (assigned an initial value) in their declaration. The initializer consists of an equal sign followed by a constant expression as follows −  
```type variable_name = value;```

**Note:** For definition without an initializer: variables with static storage duration are implicitly initialized with NULL (all bytes have the value 0); the initial value of all other variables is undefined.

For example,
```cpp
int myNum = 5;               // Integer (whole number without decimals)
double myFloatNum = 5.99;    // Floating point number (with decimals)
char myLetter = 'D';         // Character
char[6] x = 'abcde';         // the variable x has the value 'x'.
bool myBoolean = true;       // Boolean (true or false)
```

---
# Lvalues and Rvalues

There are two kinds of expressions in C++ −

  *  lvalue − Expressions that refer to a memory location is called "lvalue" expression. An lvalue may appear as either the left-hand or right-hand side of an assignment. l-value often represents an identifier.  
  
  *  rvalue − The term rvalue refers to a data value that is stored at some address in memory. An rvalue is an expression that cannot have a value assigned to it which means an rvalue may appear on the right- but not left-hand side of an assignment.

Variables are lvalues and so may appear on the left-hand side of an assignment. Numeric literals are rvalues and so may not be assigned and can not appear on the left-hand side.  
Following is a valid statement −  
```cpp
int g = 20;
```

But the following is not a valid statement and would generate compile-time error −
```cpp
10 = 20;
```
---
> For more information on variables in C++, visit: [w3schools](https://www.w3schools.com/cpp/cpp_variables.asp), [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_variable_types.htm).
