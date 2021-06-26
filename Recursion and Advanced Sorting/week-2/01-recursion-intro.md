# Recursion

* The process in which a function **calls itself** directly or indirectly is called recursion and the corresponding function is called as recursive function.

* If a function calls itself, it’s known as **direct recursion**. This results in a one-step recursive call: the function makes a recursive call inside its own function body.

* If the function f1 calls another function f2 and f2 calls f1 then it is **indirect recursion (or mutual recursion)**. This is a two-step recursive call: the function calls another function to make a recursive call.
---
* An example of direct recursion
```
void directRecFun()
{
    // Some code....

    directRecFun();

    // Some code...
}
```
* An example of indirect recursion
```
void indirectRecFun1()
{
    // Some code...

    indirectRecFun2();

    // Some code...
}
void indirectRecFun2()
{
    // Some code...

    indirectRecFun1();

    // Some code...
}
```
---
# Recursion versus Iteration

* Recursion and Iteration both repeatedly execute the set of instructions.  
* Recursion is when a *_statement in a function_* calls itself repeatedly. Iteration is when a *_loop_* repeatedly executes until the controlling condition becomes false.  
* The primary difference between recursion and iteration is that recursion is a process, always applied to a function and iteration is applied to the set of instructions which we want to get repeatedly executed.
* In iteration, the code is executed repeatedly function using the same memory space. That is, the memory space allocated once, is used for each pass of the loop. On the other hand in recursion, since it involves function calls overhead, the recursive function runs slower than its iterative counterpart.


---
## Recursion Advantages

*  Recursive functions make the code look clean and elegant.
*  A complex task can be broken down into simpler sub-problems using recursion.
*  Sequence generation is easier with recursion than using some nested iteration.

## Recursion Disadvantages

*  Sometimes the logic behind recursion is hard to follow through.
*  Recursive calls are expensive (inefficient) as they take up a lot of memory and time.
*  Recursive functions are hard to debug.

---

> Learn more about recursion [here](https://www.tutorialspoint.com/data_structures_algorithms/recursion_basics.htm).

> Read about the difference between recursion and iteration [here](https://www.geeksforgeeks.org/difference-between-recursion-and-iteration/).
