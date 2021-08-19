## Priority Queue is an extension of queue with following properties.

1. Every item has a priority associated with it.
2. An element with high priority is dequeued before an element with low priority.
3. If two elements have the same priority, they are served according to their order in the queue.

**In the below priority queue, element with maximum ASCII value will have the highest priority.**

![Image of Priority Queue](https://www.geeksforgeeks.org/wp-content/uploads/Priority-Queue-min-768x384.png)

### A typical priority queue supports following operations.

1. insert(item, priority): Inserts an item with given priority.
2. getHighestPriority(): Returns the highest priority item.
3. deleteHighestPriority(): Removes the highest priority item.

Ideally, we should implement a priority queue using heaps.(Because the above operation will have a better time complexity in heaps.)

Depending on the type heap we use (*max heap,min heap*) we can implement a job scheduler or a event driven simulator.

---
> To learn how to implement a priority queue go [here](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) and go [here](https://www.geeksforgeeks.org/heap-data-structure/) to understand heaps better.

> Solve this [question](https://leetcode.com/problems/relative-ranks/) to gain better understanding of the concept.

> To learn more go [here](https://www.javatpoint.com/ds-priority-queue).



