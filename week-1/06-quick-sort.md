
# Quick Sort
Like  [Merge Sort](http://quiz.geeksforgeeks.org/merge-sort/), QuickSort is a Divide and Conquer algorithm. It picks an element as pivot and partitions the given array around the picked pivot. There are many different versions of quickSort that pick pivot in different ways.

1.  Always pick first element as pivot.
2.  Always pick last element as pivot (implemented below)
3.  Pick a random element as pivot.
4.  Pick median as pivot.

The key process in quickSort is partition(). Target of partitions is, given an array and an element x of array as pivot, put x at its correct position in sorted array and put all smaller elements (smaller than x) before x, and put all greater elements (greater than x) after x. All this should be done in linear time.

**Pseudo Code for recursive QuickSort function :**

/* low  --> Starting index,  high  --> Ending index */
quickSort(arr[], low, high)
{
    if (low < high)
    {
        /* pi is partitioning index, arr[pi] is now
           at right place */
        pi = partition(arr, low, high);

        quickSort(arr, low, pi - 1);  // Before pi
        quickSort(arr, pi + 1, high); // After pi
    }
}

![quicksort](https://www.geeksforgeeks.org/wp-content/uploads/gq/2014/01/QuickSort2.png)

**Partition Algorithm**  
There can be many ways to do partition, following pseudo code adopts the method given in CLRS book. The logic is simple, we start from the leftmost element and keep track of index of smaller (or equal to) elements as i. While traversing, if we find a smaller element, we swap current element with arr[i]. Otherwise we ignore current element.

  

  
```
/* low  --> Starting index,  high  --> Ending index */
quickSort(arr[], low, high)
{
    if (low < high)
    {
        /* pi is partitioning index, arr[pi] is now
           at right place */
        pi = partition(arr, low, high);

        quickSort(arr, low, pi - 1);  // Before pi
        quickSort(arr, pi + 1, high); // After pi
    }
}
```
**Pseudo code for partition()**
```
/* This function takes last element as pivot, places
   the pivot element at its correct position in sorted
    array, and places all smaller (smaller than pivot)
   to left of pivot and all greater elements to right
   of pivot */
partition (arr[], low, high)
{
    // pivot (Element to be placed at right position)
    pivot = arr[high];  
 
    i = (low - 1)  // Index of smaller element and indicates the 
                   // right position of pivot found so far

    for (j = low; j <= high- 1; j++)
    {
        // If current element is smaller than the pivot
        if (arr[j] < pivot)
        {
            i++;    // increment index of smaller element
            swap arr[i] and arr[j]
        }
    }
    swap arr[i + 1] and arr[high])
    return (i + 1)
}
```
**Illustration of partition() :**
```
arr[] = {10, 80, 30, 90, 40, 50, 70}
Indexes:  0   1   2   3   4   5   6 

low = 0, high =  6, pivot = arr[h] = 70
Initialize index of smaller element, **i = -1**

Traverse elements from j = low to high-1
**j = 0** : Since arr[j] <= pivot, do i++ and swap(arr[i], arr[j])
**i = 0** 
arr[] = {10, 80, 30, 90, 40, 50, 70} // No change as i and j 
                                     // are same

**j = 1** : Since arr[j] > pivot, do nothing
// No change in i and arr[]

**j = 2** : Since arr[j] <= pivot, do i++ and swap(arr[i], arr[j])
**i = 1**
arr[] = {10, 30, 80, 90, 40, 50, 70} // We swap 80 and 30 

**j = 3** : Since arr[j] > pivot, do nothing
// No change in i and arr[]

**j = 4** : Since arr[j] <= pivot, do i++ and swap(arr[i], arr[j])
**i = 2**
arr[] = {10, 30, 40, 90, 80, 50, 70} // 80 and 40 Swapped
**j = 5** : Since arr[j] <= pivot, do i++ and swap arr[i] with arr[j] 
**i = 3** 
arr[] = {10, 30, 40, 50, 80, 90, 70} // 90 and 50 Swapped 

We come out of loop because j is now equal to high-1.
**Finally we place pivot at correct position by swapping**
**arr[i+1] and arr[high] (or pivot)** 
arr[] = {10, 30, 40, 50, 70, 90, 80} // 80 and 70 Swapped 
```
Now 70 is at its correct place. All elements smaller than
70 are before it and all elements greater than 70 are after
it.
**Analysis of QuickSort**  
Time taken by QuickSort, in general, can be written as following.

 T(n) = T(k) + T(n-k-1) + ![\theta](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a372b7ef1ffaec3b4ad80e0141550990_l3.svg "Rendered by QuickLaTeX.com")(n)

The first two terms are for two recursive calls, the last term is for the partition process. k is the number of elements which are smaller than pivot.  
The time taken by QuickSort depends upon the input array and partition strategy. Following are three cases.

_**Worst Case:**_  The worst case occurs when the partition process always picks greatest or smallest element as pivot. If we consider above partition strategy where last element is always picked as pivot, the worst case would occur when the array is already sorted in increasing or decreasing order. Following is recurrence for worst case.

 T(n) = T(0) + T(n-1) + ![\theta](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a372b7ef1ffaec3b4ad80e0141550990_l3.svg "Rendered by QuickLaTeX.com")(n)
which is equivalent to  
T(n) = T(n-1) + ![\theta](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a372b7ef1ffaec3b4ad80e0141550990_l3.svg "Rendered by QuickLaTeX.com")(n)

The solution of above recurrence is ![\theta        ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-ad96603b6b3b79032cac5cb68d6aa9ff_l3.svg "Rendered by QuickLaTeX.com")(n2).

  
  

_**Best Case:**_  The best case occurs when the partition process always picks the middle element as pivot. Following is recurrence for best case.

 T(n) = 2T(n/2) + ![\theta](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a372b7ef1ffaec3b4ad80e0141550990_l3.svg "Rendered by QuickLaTeX.com")(n)

The solution of above recurrence is ![\theta        ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-ad96603b6b3b79032cac5cb68d6aa9ff_l3.svg "Rendered by QuickLaTeX.com")(nLogn). It can be solved using case 2 of  [Master Theorem](http://en.wikipedia.org/wiki/Master_theorem).

_**Average Case:**_  
To do average case analysis, we need to  [consider all possible permutation of array and calculate time taken by every permutation which doesn’t look easy](https://www.geeksforgeeks.org/analysis-of-algorithms-set-2-asymptotic-analysis/).  
We can get an idea of average case by considering the case when partition puts O(n/9) elements in one set and O(9n/10) elements in other set. Following is recurrence for this case.

 T(n) = T(n/9) + T(9n/10) + ![\theta](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a372b7ef1ffaec3b4ad80e0141550990_l3.svg "Rendered by QuickLaTeX.com")(n)

Solution of above recurrence is also O(nLogn)  
Although the worst case time complexity of QuickSort is O(n2) which is more than many other sorting algorithms like  [Merge Sort](http://quiz.geeksforgeeks.org/merge-sort/)  and  [Heap Sort](http://quiz.geeksforgeeks.org/heap-sort/), QuickSort is faster in practice, because its inner loop can be efficiently implemented on most architectures, and in most real-world data. QuickSort can be implemented in different ways by changing the choice of pivot, so that the worst case rarely occurs for a given type of data. However, merge sort is generally considered better when data is huge and stored in external storage.

**Is QuickSort** [**stable**](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/)**?**  
The default implementation is not stable. However any sorting algorithm can be made stable by considering indexes as comparison parameter.

**Is QuickSort** [**In-place**](https://www.geeksforgeeks.org/in-place-algorithm/)**?**  
As per the broad definition of in-place algorithm it qualifies as an in-place sorting algorithm as it uses extra space only for storing recursive function calls but not for manipulating the input.

**What is 3-Way QuickSort?**  
In simple QuickSort algorithm, we select an element as pivot, partition the array around pivot and recur for subarrays on left and right of pivot.  
Consider an array which has many redundant elements. For example, {1, 4, 2, 4, 2, 4, 1, 2, 4, 1, 2, 2, 2, 2, 4, 1, 4, 4, 4}. If 4 is picked as pivot in Simple QuickSort, we fix only one 4 and recursively process remaining occurrences. In 3 Way QuickSort, an array arr[l..r] is divided in 3 parts:  
a) arr[l..i] elements less than pivot.  
b) arr[i+1..j-1] elements equal to pivot.  
c) arr[j..r] elements greater than pivot.  
See  [this](https://www.geeksforgeeks.org/3-way-quicksort/)  for implementation.

**How to implement QuickSort for Linked Lists?**  
[QuickSort on Singly Linked List](https://www.geeksforgeeks.org/quicksort-on-singly-linked-list/)  
[QuickSort on Doubly Linked List](https://www.geeksforgeeks.org/quicksort-for-linked-list/)

**Can we implement QuickSort Iteratively?**  
Yes, please refer  [Iterative Quick Sort](https://www.geeksforgeeks.org/iterative-quick-sort/).

**Why Quick Sort is preferred over MergeSort for sorting Arrays**  
Quick Sort in its general form is an in-place sort (i.e. it doesn’t require any extra storage) whereas merge sort requires O(N) extra storage, N denoting the array size which may be quite expensive. Allocating and de-allocating the extra space used for merge sort increases the running time of the algorithm. Comparing average complexity we find that both type of sorts have O(NlogN) average complexity but the constants differ. For arrays, merge sort loses due to the use of extra O(N) storage space.  
Most practical implementations of Quick Sort use randomized version. The randomized version has expected time complexity of O(nLogn). The worst case is possible in randomized version also, but worst case doesn’t occur for a particular pattern (like sorted array) and randomized Quick Sort works well in practice.  
Quick Sort is also a cache friendly sorting algorithm as it has good locality of reference when used for arrays.  
Quick Sort is also tail recursive, therefore tail call optimizations is done.

[Quick Sort implementation here](https://www.geeksforgeeks.org/quick-sort/)