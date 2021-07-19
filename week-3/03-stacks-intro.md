# Stacks

Stack is a linear data structure which has two main operations — push (insert) and pop (remove). Imagine a stack of plates or a deck of cards placed on a table. A new plate or card is always added (pushed) to the top of that stack, not the bottom. And if you were to remove (pop) an element, that too would be from the top of the stack.  
Thus the last element to enter the stack would be the first to leave, and vice-versa. The order in which elements come off a stack gives rise to its alternative name **LIFO(Last In First Out)** a.k.a. FILO(First In Last Out).  
![LIFO](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2013/03/stack.png)  

## Basic Operations

Stack operations may involve initializing the stack, using it and then de-initializing it. Apart from these basic stuff, a stack is used for the following two primary operations −

 *   push() − Pushing (storing) an element on the stack.

 *  pop() − Removing (accessing) an element from the stack.


To use a stack efficiently, we need to check the status of stack as well. For the same purpose, the following functionality is added to stacks −

 *  peek() − get the top data element of the stack, without removing it.

 *  isFull() − check if stack is full.

 *  isEmpty() − check if stack is empty.

At all times, we maintain a pointer to the last PUSHed data on the stack. As this pointer always represents the top of the stack, hence named top. The top pointer provides top value of the stack without actually removing it.


## Implementation: 
There are two ways to implement a stack: 

* Using array

  * Pros: Easy to implement. Memory is saved as pointers are not involved. 
  * Cons: It is not dynamic. It doesn’t grow and shrink depending on needs at runtime.
 
* Using linked list

  * Pros: The linked list implementation of stack can grow and shrink according to the needs at runtime. 
  * Cons: Requires extra memory due to involvement of pointers.

---

> Read more about Stacks [here](https://en.wikipedia.org/wiki/Stack_(abstract_data_type))
