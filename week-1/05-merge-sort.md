
# Merge Sort
Like  [QuickSort](https://www.geeksforgeeks.org/quick-sort/), Merge Sort is a  [Divide and Conquer](https://www.geeksforgeeks.org/divide-and-conquer-introduction/)  algorithm. It divides the input array into two halves, calls itself for the two halves, and then merges the two sorted halves.  **The merge() function**  is used for merging two halves. The merge(arr, l, m, r) is a key process that assumes that arr[l..m] and arr[m+1..r] are sorted and merges the two sorted sub-arrays into one. See the following C implementation for details.
```
MergeSort(arr[], l,  r)
If r > l
     1 Find the middle point to divide the array into two halves:  
             middle m = l+ (r-l)/2
    2. Call mergeSort for first half:   
             Call mergeSort(arr, l, m)
     3. Call mergeSort for second half:
             Call mergeSort(arr, m+1, r)
     4. Merge the two halves sorted in step 2 and 3:
             Call merge(arr, l, m, r)
```
The following diagram from  [wikipedia](http://en.wikipedia.org/wiki/File:Merge_sort_algorithm_diagram.svg)  shows the complete merge sort process for an example array {38, 27, 43, 3, 9, 82, 10}. If we take a closer look at the diagram, we can see that the array is recursively divided into two halves till the size becomes 1. Once the size becomes 1, the merge processes come into action and start merging arrays back till the complete array is merged.  

![Merge-Sort-Tutorial](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Merge-Sort-Tutorial.png)
**Time Complexity:**  Sorting arrays on different machines. Merge Sort is a recursive algorithm and time complexity can be expressed as following recurrence relation.  
T(n) = 2T(n/2) + θ(n)

The above recurrence can be solved either using the Recurrence Tree method or the Master method. It falls in case II of Master Method and the solution of the recurrence is θ(nLogn). Time complexity of Merge Sort is θ(nLogn) in all 3 cases (worst, average and best) as merge sort always divides the array into two halves and takes linear time to merge two halves.  
**Auxiliary Space:**  O(n)  
**Algorithmic Paradigm:** Divide and Conquer  
**Sorting In Place:**  No in a typical implementation  
**Stable:**  Yes

[Merge Sort implementation here](https://www.geeksforgeeks.org/merge-sort/)