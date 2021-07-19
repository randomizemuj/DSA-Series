# Operations on stacks
![LIFO](https://www.tutorialspoint.com/data_structures_algorithms/images/stack_representation.jpg)
- push()

Algorithm of push() function −
```
    Step 1 − Checks if the stack is full.

    Step 2 − If the stack is full, produces an error and exit.

    Step 3 − If the stack is not full, increments top to point next empty space.

    Step 4 − Adds data element to the stack location, where top is pointing.

    Step 5 − Returns success.
```
Implementation of push() in C++
```cpp
bool Stack::push(int x)
{
    if (top >= (MAX - 1)) {
        cout << "Stack Overflow";
        return false;
    }
    else {
        a[++top] = x;
        cout << x << " pushed into stack\n";
        return true;
    }
}
 
```
- pop()

Algorithm of pop() function −
```
    Step 1 − Checks if the stack is empty.

    Step 2 − If the stack is empty, produces an error and exit.

    Step 3 − If the stack is not empty, accesses the data element at which top is pointing.

    Step 4 − Decreases the value of top by 1.

    Step 5 − Returns success.
```
Implementation of pop() in C++
```cpp
int Stack::pop()
{
    if (top < 0) {
        cout << "Stack Underflow";
        return 0;
    }
    else {
        int x = a[top--];
        return x;
    }
}
```

- peek()

Algorithm of peek() function −
```
begin procedure peek
   return stack[top]
end procedure
```
Implementation of peek() in C++
```cpp
int Stack::peek()
{
    if (top < 0) {
        cout << "Stack is Empty";
        return 0;
    }
    else {
        int x = a[top];
        return x;
    }
}
 
```

- isEmpty()

Algorithm of isEmpty() function −
```
begin procedure isEmpty

   if top less than 1
      return true
   else
      return false
   endif
   
end procedure
```
Implementation of isEmpty() in C++
```cpp
bool Stack::isEmpty()
{
    return (top < 0);
}
```
---
## Time Complexities of operations on stack:

push(), pop(), isEmpty() and peek() all take O(1) time. We do not run any loop in any of these operations.
 
---
> Solve problems on Stacks [here](https://www.geeksforgeeks.org/stack-data-structure/).
> Read more about implementing stacks [here](https://www.geeksforgeeks.org/stack-data-structure-introduction-program/) and [here](https://www.tutorialspoint.com/data_structures_algorithms/stack_algorithm.htm).
