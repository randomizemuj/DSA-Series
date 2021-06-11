# Introduction to C++ programming

It can be simplified into:
* Writing your program in a text-editor and saving it with correct extension (.CPP)
* Compiling your program using a compiler or online IDE
* Understanding the basic terminologies.

---

# C++ program structure

**Input:**

```cpp
#include <iostream>
using namespace std;

/* main() is where 
the program execution begins.*/

int main() {
   cout << "Hello World"; // prints Hello World
   return 0;
}
```

**Output:**
`Hello World`

---

1. **#include:** In C++,  all lines that start with pound (#) sign are called _**directives**_ and are processed by preprocessor which is a program invoked by the compiler.

2. **using namespace std:** This is used to import the entirety of the std namespace into the current namespace of the program. The statement using namespace std is _**generally considered a bad practice.**_ When we import a namespace we are essentially pulling all type definitions into the current scope. The std namespace is huge. The alternative to this statement is to specify the namespace to which the identifier belongs using the scope operator(::) each time we declare a type.

3. **Comments:** Program comments are explanatory statements that you can include in the C++ code. These comments help anyone reading the source code. Any line beginning with ‘//’ without quotes OR multiple lines in between /*…*/ in C++ comprise a comment.

4. **int main():** This line is used to declare a function named “main” _**which returns data of integer type**_.

5. **'{' and '}':** A block is a set of logically connected statements that are surrounded by opening and closing braces.In this example, everything between these two comprises the body of the **main** function.

6. **Statements:** Every statement is meant to perform some task. A semi-colon ‘;’ is used to end a statement. Semi-colon character at the end of statement is used to indicate that the statement is ending there. For example, the statement `cout << "Hello World";` causes the message "Hello World" to be displayed on the screen. 

7. **return 0; :** This is also a statement. This statement is used to return a value from a function and indicates the finishing of a function. Here, it terminates main( )function and causes it to return the value 0 to the calling process.

---

# C++ Identifiers

A C++ identifier is a name used to identify a variable, function, class, module, or any other user-defined item. An identifier starts with a letter A to Z or a to z or an underscore (\_) followed by zero or more letters, underscores, and digits (0 to 9).

C++ does not allow punctuation characters such as @, $, and % within identifiers. C++ is a case-sensitive programming language. Thus, Manpower and manpower are two different identifiers in C++.

Here are some examples of acceptable identifiers −

```
mohd       zara    abc   move_name  a_123
myname50   _temp   j     a23b9      retVal
```

---

# C++ Keywords
These are reserved words, which must not be used as constant or variable or any other identifier names.  
[Here](https://www.learncpp.com/cpp-tutorial/keywords-and-naming-identifiers/comment-page-2/) is a list of all the C++ keywords.

Some of them are:

![C++ Keywords](https://2.bp.blogspot.com/-AJgOlezZIMw/W_j30-pZXxI/AAAAAAAAAZ4/DDZO0Kkrx-wnmpghHUciWLdfCDPUebCXQCLcBGAs/s1600/keywords1.jpg)

---
# Whitespace in C++

Whitespace is the term used in C++ to describe blanks, tabs, newline characters and comments. Whitespace separates one part of a statement from another and enables the compiler to identify where one element in a statement, such as int, ends and the next element begins.
A line containing only whitespace, possibly with a comment, is known as a blank line, and C++ compiler totally ignores it.

---

> For more information on basic C++ syntax, visit: [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_basic_syntax.htm), [GeeksForGeeks](https://www.geeksforgeeks.org/c-programming-basics/)
