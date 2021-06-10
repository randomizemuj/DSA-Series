# Data types in C++

While writing program in any language, you need to use various variables to store various information. Variables are nothing but reserved memory locations to store values. This means that when you create a variable you reserve some space in memory.  
Based on the data type of a variable, the operating system allocates memory and decides what can be stored in the reserved memory.

# Primitive Built-in Types

C++ offers the programmer a rich assortment of built-in as well as user defined data types. Following table lists down seven basic C++ data types −
| Type 	                | Keyword |
|-----------------------|---------|
| Boolean               | bool    |
| Character 	          | char    |
| Integer 	            | int     |
| Floating point      	| float   |
| Double floating point |	double  |
| Valueless 	          | void    |
| Wide character 	      | wchar_t |

---

Several of the basic types can be modified using one or more of these **type modifiers** −

   * signed
   * unsigned
   * short
   * long  

The following table shows some variable types, how much memory they take to store the value in memory, and what is the maximum and minimum value which can be stored in such type of variables.  
  
![](https://xcbiology.files.wordpress.com/2015/07/table-e1438380260928.png)

---
# sizeof() operator

When sizeof() is used _with the data types_ such as int, float, char… etc it simply returns the amount of memory is allocated to that data types.

**Input:**
```cpp
#include <iostream>
using namespace std;
 
int main()
{
    cout << sizeof(char)<<"\n";
    cout << sizeof(int)<<"\n";
    cout << sizeof(float)<<"\n";
    cout << sizeof(double)<<"\n";
    return 0;
}
```

**Output:**
```
1
4
4
8
```

---

# typedef Declarations

You can create a new name for an existing type using typedef. Following is the simple syntax to define a new type using typedef −

```cpp
typedef type newname;
```

For example, the following tells the compiler that feet is another name for int −

```cpp
typedef int feet;
```
Now, the following declaration is perfectly legal and creates an integer variable called distance −

```cpp
feet distance;
```
---
> For more information on data types, visit [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_data_types.htm), [GeeksForGeeks](https://www.geeksforgeeks.org/c-data-types/)
