# Bubble Sort
Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.  
**Example:**  
**First Pass:**  
(  **5**  **1**  4 2 8 ) –> (  **1**  **5**  4 2 8 ), Here, algorithm compares the first two elements, and swaps since 5 > 1.  
( 1  **5**  **4**  2 8 ) –> ( 1  **4**  **5**  2 8 ), Swap since 5 > 4  
( 1 4  **5**  **2**  8 ) –> ( 1 4  **2**  **5**  8 ), Swap since 5 > 2  
( 1 4 2  **5**  **8**  ) –> ( 1 4 2  **5**  **8**  ), Now, since these elements are already in order (8 > 5), algorithm does not swap them.  
**Second Pass:**  
(  **1**  **4**  2 5 8 ) –> (  **1**  **4**  2 5 8 )  
( 1  **4**  **2**  5 8 ) –> ( 1  **2**  **4**  5 8 ), Swap since 4 > 2  
( 1 2  **4**  **5**  8 ) –> ( 1 2  **4**  **5**  8 )  
( 1 2 4  **5**  **8**  ) –> ( 1 2 4  **5**  **8**  )  
Now, the array is already sorted, but our algorithm does not know if it is completed. The algorithm needs one  **whole**  pass without  **any**  swap to know it is sorted.  
**Third Pass:**  
(  **1**  **2**  4 5 8 ) –> (  **1**  **2**  4 5 8 )  
( 1  **2**  **4**  5 8 ) –> ( 1  **2**  **4**  5 8 )  
( 1 2  **4**  **5**  8 ) –> ( 1 2  **4**  **5**  8 )  
( 1 2 4  **5**  **8**  ) –> ( 1 2 4  **5**  **8**  )



![bubble-sort](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/02/bubble-sort1.png)

**Worst and Average Case Time Complexity:** O(n*n). Worst case occurs when array is reverse sorted.  
**Best Case Time Complexity:** O(n). Best case occurs when array is already sorted.  
**Auxiliary Space:** O(1)  
**Boundary Cases:** Bubble sort takes minimum time (Order of n) when elements are already sorted.  
**Sorting In Place:** Yes  
**Stable:** Yes  
Due to its simplicity, bubble sort is often used to introduce the concept of a sorting algorithm.  
In computer graphics it is popular for its capability to detect a very small error (like swap of just two elements) in almost-sorted arrays and fix it with just linear complexity (2n). For example, it is used in a polygon filling algorithm, where bounding lines are sorted by their x coordinate at a specific scan line (a line parallel to x axis) and with incrementing y their order changes (two elements are swapped) only at intersections of two lines (Source: [Wikipedia](http://en.wikipedia.org/wiki/Bubble_sort#In_practice))

[Bubble Sort implementation here](https://www.geeksforgeeks.org/bubble-sort/)