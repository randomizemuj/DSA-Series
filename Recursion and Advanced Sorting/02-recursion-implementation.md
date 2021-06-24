# Cases in Recursion
Before you start working recursive functions, you must know that every recursive function must have at least two cases :  
1. The Recursive Case (a.k.a. Inductive Case): It is a general case of the problem we’re trying to solve using recursive call to same function.

2. The Base Case (a.k.a. Stopping Case): It is a small problem that we know how to solve and is the case that *_causes the recursion to end._* In other words, it is the case whose solution is pre-known (either as a value or formula) and used directly.

Note :

  *  The Base case in a recursive program **MUST BE REACHABLE**. Otherwise, an infinite recursion eventually causes a runtime error of *_maximum recursion depth exceeded._*

  *  Any condition where a recursive function does not invoke itself is a base case. A case whose result is known or computed without any recursive calling is called the **base case**.

  *  Every recursive function consists of *_one or more_* base cases and a general, recursive case.

  * **Progressive approach** − The recursive calls should progress in such a way that each time a recursive call is made it comes closer to the base criteria.

---

**Input**
```cpp
// A C++ program to demonstrate working of
// recursion
#include <bits/stdc++.h>
using namespace std;

void printFun(int test)
{
    if (test < 1)
        return;
    else {
        cout << test << " ";
        printFun(test - 1); // statement 2
        cout << test << " ";
        return;
    }
}

// Driver Code
int main()
{
    int test = 3;
    printFun(test);
}
```

**Output**

```
3 2 1 1 2 3
```
---
# Implementation of Recursion
Many programming languages implement recursion by means of stacks. In executing a program, the computer creates what is called the **function stack**. It is a stack of frames, each frame corresponding to a function invocation. At all times, the computer works on executing whichever function is at the top of the stack. But when there is a function invocation, the computer creates a new frame and places it atop the stack. When the function at the stack's top returns, the computer removes the function's frame from the stack's top and resumes its work on the function _*now*_ on the frame's top.

![](https://www.tutorialspoint.com/data_structures_algorithms/images/activation_records.jpg)

---

## Time Complexity

In case of iterations, we take number of iterations to count the time complexity. Likewise, in case of recursion, *_assuming everything is constant_*, we try to figure out the number of times a recursive call is being made. A call made to a function is Ο(1), hence the (n) number of times a recursive call is made makes the recursive function Ο(n).

## Space Complexity

Space complexity is counted as what amount of extra space is required for a module to execute. In case of iterations, the compiler hardly requires any extra space. The compiler keeps updating the values of variables used in the iterations. But in case of recursion, the system needs to store activation record each time a recursive call is made. Hence, it is considered that space complexity of recursive function may go higher than that of a function with iteration.

---
> [Practice problems](https://www.codechef.com/tags/problems/recursion) on recursive functions.

> You can practice problems on recursion [here](https://www.geeksforgeeks.org/recursion-practice-problems-solutions/).
