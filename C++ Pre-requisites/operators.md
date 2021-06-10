# Operators in C++
An operator is a symbol that tells the compiler to perform specific mathematical or logical manipulations. C++ is rich in built-in operators and provide the following types of operators −

## Arithmetic Operators
These are the operators used to perform arithmetic/mathematical operations on operands. Examples: (+, -, *, /, %,++,–). Arithmetic operator are of two types:

 *  Unary Operators: Operators that operates or works with a single operand are unary operators. For example: (++ , –)
 *  Binary Operators: Operators that operates or works with two operands are binary operators. For example: (+ , – , * , /)
---

## Relational Operators
These are used for comparison of the values of two operands. For example, checking if one operand is equal to the other operand or not, an operand is greater than the other operand or not etc. Some of the relational operators are (==, >= , <= ).

---

## Logical Operators
Logical Operators are used to combine two or more conditions/constraints or to complement the evaluation of the original condition in consideration. The result of the operation of a logical operator is a boolean value either true or false. For example, the logical AND represented as ‘&&’ operator in C or C++ returns true when both the conditions under consideration are satisfied. Otherwise it returns false. Therfore, a && b returns true when both a and b are true (i.e. non-zero).

---
## Bitwise Operators
The Bitwise operators is used to perform bit-level operations on the operands. The operators are first converted to bit-level and then the calculation is performed on the operands. The mathematical operations such as addition, subtraction, multiplication etc. can be performed at bit-level for faster processing. For example, the bitwise AND represented as & operator in C or C++ takes two numbers as operands and does AND on every bit of two numbers. The result of AND is 1 only if both bits are 1.

---
## Assignment Operators
Assignment operators are used to assign values to variables.

---
## Misc Operators
Apart from the above operators there are some other operators available in C or C++ used to perform some specific task. Some of them are discussed here:

  1. sizeof operator: a much used in the C/C++ programming language. It is a compile time unary operator which can be used to compute the size of its operand. The result of sizeof is of unsigned integral type which is usually denoted by size_t. Basically, sizeof operator is used to compute the size of the variable.
  2. The comma operator: (represented by the token **,**) a binary operator that evaluates its first operand and discards the result, it then evaluates the second operand and returns this value (and type). The comma operator has the lowest precedence of any C operator.  
  3. Conditional operator is of the form `Expression1 ? Expression2 : Expression3` . Here, Expression1 is the condition to be evaluated. If the condition(Expression1) is True then we will execute and return the result of Expression2 otherwise if the condition(Expression1) is false then we will execute and return the result of Expression3. We may replace the use of if..else statements by conditional operators.

---
> For more information on operators, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/operators-c-c/), [W3Schools](https://www.w3schools.com/cpp/cpp_operators_assignment.asp), [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_operators.htm)
