# Loops in C++

There may be a situation, when you need to execute a block of code several number of times. In general, statements are executed sequentially: The first statement in a function is executed first, followed by the second, and so on.

Programming languages provide various control structures that allow for more complicated execution paths.

A loop statement allows us to execute a statement or group of statements multiple times and following is the general from of a loop statement in most of the programming languages −

In Loop, the statement needs to be written only once and the loop will be executed 10 times as shown below.  
In computer programming, a loop is a sequence of instructions that is repeated until a certain condition is reached.

-   An operation is done, such as getting an item of data and changing it, and then some condition is checked such as whether a counter has reached a prescribed number.
-   **Counter not Reached:** If the counter has not reached the desired number, the next instruction in the sequence returns to the first instruction in the sequence and repeat it.
-   **Counter reached:**  If the condition has been reached, the next instruction “falls through” to the next sequential instruction or branches outside the loop.

---
**For Loop**
A for loop is a repetition control structure which allows us to write a loop that is executed a specific number of times. The loop enables us to perform n number of steps together in one line.  
**Syntax:**
```
for (initialization expr; test expr; update expr)
{    
     // body of the loop
     // statements we want to execute
}
```
Flow Diagram for 'for' loop

![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/loops.png)

**While Loop**

While studying  **for loop**  we have seen that the number of iterations is known beforehand, i.e. the number of times the loop body is needed to be executed is known to us. while loops are used in situations where we do not know the exact number of iterations of loop beforehand. The loop execution is terminated on the basis of test condition.

**Syntax**:  
We have already stated that a loop is mainly consisted of three statements – initialization expression, test expression, update expression. The syntax of the three loops – For, while and do while mainly differs on the placement of these three statements.

**initialization expression;**
```
while (**test_expression**)
{
   // statements
 
  **update_expression;**
}
```
**Flow Diagram**:

![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/php-while-loop.jpg)

**do while loop**

In do while loops also the loop execution is terminated on the basis of test condition. The main difference between do while loop and while loop is in do while loop the condition is tested at the end of loop body, i.e do while loop is exit controlled whereas the other two loops are entry controlled loops.  
**Note**: In do while loop the loop body will execute at least once irrespective of test condition.

  

  

**Syntax**:

**initialization expression;**
```
do
{
   // statements

   **update_expression;**
} while (**test_expression**);
```
**Note**: Notice the semi – colon(“;”) in the end of loop.

**Flow Diagram**:

![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/php-do-while.jpg)

**Important Points:**

-   Use for loop when number of iterations is known beforehand, i.e. the number of times the loop body is needed to be executed is known.
-   Use while loops where exact number of iterations is not known but the loop termination condition is known.
-   Use do while loop if the code needs to be executed at least once like in Menu driven programs

> For more information on loops visit: [GeeksForGeeks](https://www.geeksforgeeks.org/loops-in-c-and-cpp/), [TutorialsPoint](https://www.tutorialspoint.com/cplusplus/cpp_loop_types.htm).
