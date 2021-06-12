# Heap Sort

Heap sort is a comparison-based sorting technique based on Binary Heap data structure. It is similar to selection sort where we first find the minimum element and place the minimum element at the beginning. We repeat the same process for the remaining elements.

**What is** [**Binary Heap**](https://www.geeksforgeeks.org/binary-heap/)**?**  
Let us first define a Complete Binary Tree. A complete binary tree is a binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible (Source  [Wikipedia](http://en.wikipedia.org/wiki/Binary_tree#Types_of_binary_trees))  
A  [Binary Heap](https://www.geeksforgeeks.org/binary-heap/)  is a Complete Binary Tree where items are stored in a special order such that the value in a parent node is greater(or smaller) than the values in its two children nodes. The former is called max heap and the latter is called min-heap. The heap can be represented by a binary tree or array.

**Why array based representation for Binary Heap?**  
Since a Binary Heap is a Complete Binary Tree, it can be easily represented as an array and the array-based representation is space-efficient. If the parent node is stored at index I, the left child can be calculated by 2 * I + 1 and the right child by 2 * I + 2 (assuming the indexing starts at 0).

**Heap Sort Algorithm for sorting in increasing order:**  
**1.**  Build a max heap from the input data.  
**2.**  At this point, the largest item is stored at the root of the heap. Replace it with the last item of the heap followed by reducing the size of heap by 1. Finally, heapify the root of the tree.  
**3.**  Repeat step 2 while the size of the heap is greater than 1.

**How to build the heap?**  
Heapify procedure can be applied to a node only if its children nodes are heapified. So the heapification must be performed in the bottom-up order.  
Lets understand with the help of an example:

  

  
```
Input data: 4, 10, 3, 5, 1
         4(0)
        /   \
     10(1)   3(2)
    /   \
 5(3)    1(4)

The numbers in bracket represent the indices in the array 
representation of data.

Applying heapify procedure to index 1:
         4(0)
        /   \
    10(1)    3(2)
    /   \
5(3)    1(4)

Applying heapify procedure to index 0:
        10(0)
        /  \
     5(1)  3(2)
    /   \
 4(3)    1(4)
The heapify procedure calls itself recursively to build heap
 in top down manner.
 ```
> **Notes:**  
Heap sort is an in-place algorithm.  
Its typical implementation is not stable, but can be made stable (See  [this](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/))

**Time Complexity:** Time complexity of heapify is O(Logn). Time complexity of createAndBuildHeap() is O(n) and the overall time complexity of Heap Sort is O(nLogn).

**Applications of HeapSort**  
**1.**  [Sort a nearly sorted (or K sorted) array](https://www.geeksforgeeks.org/nearly-sorted-algorithm/)  
**2.** [k largest(or smallest) elements in an array](https://www.geeksforgeeks.org/k-largestor-smallest-elements-in-an-array/)  
Heap sort algorithm has limited uses because Quicksort and Mergesort are better in practice. Nevertheless, the Heap data structure itself is enormously used. See  [Applications of Heap Data Structure](https://www.geeksforgeeks.org/applications-of-heap-data-structure/)  
https://youtu.be/MtQL_ll5KhQ

[Heap Sort implementation here](https://www.geeksforgeeks.org/heap-sort/)