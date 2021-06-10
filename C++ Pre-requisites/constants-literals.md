# C++ Constants/Literals

The values assigned to each constant variables are referred to as the literals. Generally, both terms, constants and literals are used interchangeably. Constants are treated just like regular variables except that their values cannot be modified after their definition.  
Constants can be of any of the basic data types and can be divided into

## 1. Integer Numerals:
These are used to represent and store the integer values. Integer literals are expressed in two types i.e.,
   * An integer literal with a **prefix** which specifies the base or radix: 0x or 0X for hexadecimal, 0 for octal, and nothing for decimal.
   * An integer literal can also have a **suffix** that is a combination of U and L, for unsigned and long, respectively. The suffix can be uppercase or lowercase and can be in any order.
Examples of various types of Integer literals −
```
85         // decimal
0213       // octal
0x4b       // hexadecimal
30         // int
30u        // unsigned int
30l        // long
30ul       // unsigned long
```
---

## 2. Floating-Point Numerals: 
These are used to represent and store real numbers. The real number has an integer part, real part, fractional part and an exponential part. The floating-point literals can be stored either in decimal form or exponential form. While representing the floating-point decimals one must keep two things in mind to produce valid literals:

  * In the decimal form, one must include the decimal point, exponent part or both, otherwise, it will lead to an error.
  * In the exponential form, one must include the integer part, fractional part or both, otherwise, it will lead to an error.
Valid Floating Literals:

```
10.125
1.215-10L
10.5E-3
```
---

## 3. Characters:
Character literals are enclosed in single quotes. If the literal begins with L (uppercase only), it is a wide character literal (e.g., L'x') and should be stored in wchar_t type of variable . Otherwise, it is a narrow character literal (e.g., 'x') and can be stored in a simple variable of char type.

A character literal can be a plain character (e.g., 'x'), an escape sequence (e.g., '\t'), or a universal character (e.g., '\u02C0').

There are certain characters in C++ when they are preceded by a backslash they will have special meaning and they are used to represent like newline (\n) or tab (\t).  
Here, you have a list of some of such escape sequence codes −

![](https://cdn.educba.com/academy/wp-content/uploads/2020/01/Escape-Sequence-is-C.png)

---

## 4. Strings: String literals are similar to that of the character literals, except that it can store multiple characters and uses a double quote to store the same. It can also accommodate the special characters and escape sequences mentioned in the table above.  
**Input**
```cpp
#include <iostream>
using namespace std;
  
int main()
{
    const string str
        = "Randomize();";
    cout << str;
    return 0;
}
```
**Output**
`Randomize();`

---

## 5. Boolean Values:
This literal is provided only in C++ and not in C. They are used to represent the boolean datatypes. These can carry two values:

  * true: To represent True value. This must not be considered equal to int 1.
  * false: To represent False value. This must not be considered equal to int 0.
For example:  
**Input:**
```cpp
#include <iostream>
using namespace std;
  
int main()
{
    const bool isTrue = true;
    const bool isFalse = false;
  
    cout << "isTrue? "
         << isTrue << "\n";
    cout << "isFalse? "
         << isFalse << "\n";
  
    return 0;
}
```
**Output**
```
isTrue? 1
isFalse? 0
```
---

# Defining Constants

There are two simple ways in C++ to define constants −

  * Using #define preprocessor
    * syntax : `#define identifier value`

  * Using const keyword
    * syntax : `const type variable = value;`

---

> For more information on constants in C++, visit: [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_constants_literals.htm), [GeeksForGeeks](https://www.geeksforgeeks.org/types-of-literals-in-c-c-with-examples/).
