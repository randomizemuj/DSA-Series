# Sorting Algorithms
A Sorting Algorithm is used to rearrange a given array or list elements according to a comparison operator on the elements. The comparison operator is used to decide the new order of element in the respective data structure.
## Sorting Terminology?
**What is in-place sorting?**  
An in-place sorting algorithm uses constant extra space for producing the output (modifies the given array only). It sorts the list only by modifying the order of the elements within the list.  
For example, Insertion Sort and Selection Sorts are in-place sorting algorithms as they do not use any additional space for sorting the list and a typical implementation of Merge Sort is not in-place, also the implementation for counting sort is not in-place sorting algorithm.

**What are Internal and External Sortings?**  
When all data that needs to be sorted cannot be placed in-memory at a time, the sorting is called  [external sorting](http://en.wikipedia.org/wiki/External_sorting). External Sorting is used for massive amount of data. Merge Sort and its variations are typically used for external sorting. Some external storage like hard-disk, CD, etc is used for external storage.  
When all data is placed in-memory, then sorting is called internal sorting.
Stability is mainly important when we have key value pairs with duplicate keys possible (like people names as keys and their details as values). And we wish to sort these objects by keys.

**What is it?**  
A sorting algorithm is said to be stable if two objects with equal keys appear in the same order in sorted output as they appear in the input array to be sorted.

Formally stability may be defined as,  
Let  ![A](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-e63249dbcb7bc1df2ae6aa725a10a1ad_l3.svg "Rendered by QuickLaTeX.com")  be an array, and let  ![<](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-695699ab9016bc52f4da5f0fa35b9480_l3.svg "Rendered by QuickLaTeX.com")  be a strict weak ordering on the elements of  ![A](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-e63249dbcb7bc1df2ae6aa725a10a1ad_l3.svg "Rendered by QuickLaTeX.com").  
A sorting algorithm is stable if-  
![i < j\:\:and\:\:A[i]\equiv A[j]\:\:implies\:\:\pi (i) < \pi (j)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-8e99a78816d6dccaf01441f612788157_l3.svg "Rendered by QuickLaTeX.com")  
where  ![\pi](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-8874a17fc40c8e51a122ea351eb44182_l3.svg "Rendered by QuickLaTeX.com")  is the sorting permutation ( sorting moves  ![A[i]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-4aaff26b720cb0edd0e2c823272f04f4_l3.svg "Rendered by QuickLaTeX.com")  to position  ![\pi(i)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-eb6b6170c401bc20911166d405dbd32c_l3.svg "Rendered by QuickLaTeX.com")  )  
Informally, stability means that equivalent elements retain their relative positions, after sorting.
**Do we care for simple arrays like array of integers?**  
When equal elements are indistinguishable, such as with integers, or more generally, any data where the entire element is the key, stability is not an issue. Stability is also not an issue if all keys are different.

  

  

**An example where it is useful**  
Consider the following dataset of Student Names and their respective class sections.

![\\ (Dave, A)\\ (Alice, B)\\ (Ken, A)\\ (Eric, B)\\ (Carol, A)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-2022833a9be9c68490830f11574c863b_l3.svg "Rendered by QuickLaTeX.com")

If we sort this data according to name only, then it is highly unlikely that the resulting dataset will be grouped according to sections as well.

![\\ (Alice, B)\\ (Carol, A)\\ (Dave, A)\\ (Eric, B)\\ (Ken, A)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-4451468f4d77d13877495d21f005a234_l3.svg "Rendered by QuickLaTeX.com")

So we might have to sort again to obtain list of students section wise too. But in doing so, if the sorting algorithm is not stable, we might get a result like this-

![\\ (Carol, A)\\ (Dave, A)\\ (Ken, A)\\(Eric, B)\\(Alice, B)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-3350b3119f8eb7ab01ed3cdd583fd728_l3.svg "Rendered by QuickLaTeX.com")

The dataset is now sorted according to sections, but not according to names.  
In the name-sorted dataset, the tuple  ![(Alice, B)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-b86429f3831d700492e79608c69dd9c5_l3.svg "Rendered by QuickLaTeX.com")  was before  ![(Eric, B)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-c60867806a3621d1f5638c266311dda3_l3.svg "Rendered by QuickLaTeX.com"), but since the sorting algorithm is not stable, the relative order is lost.  
If on the other hand we used a stable sorting algorithm, the result would be-

![\\ (Carol, A)\\ (Dave, A)\\ (Ken, A)\\(Alice, B)\\(Eric, B)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-22d7e124e8ae07c168a6f8331c6effa5_l3.svg "Rendered by QuickLaTeX.com")

  
  

Here the relative order between different tuples is maintained. It may be the case that the relative order is maintained in an Unstable Sort but that is highly unlikely.

**Which sorting algorithms are stable?**  
Some Sorting Algorithms are stable by nature, such as  [Bubble Sort](https://www.geeksforgeeks.org/bubble-sort/),  [Insertion Sort](https://www.geeksforgeeks.org/insertion-sort/),  [Merge Sort](https://www.geeksforgeeks.org/merge-sort/),  [Count Sort](https://www.geeksforgeeks.org/counting-sort/)  etc.  
Comparison based stable sorts such as Merge Sort and Insertion Sort, maintain stability by ensuring that-  
Element  ![A[j]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-bb6437c5589f1ad4227e9191046ce643_l3.svg "Rendered by QuickLaTeX.com")  comes before  ![A[i]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-4aaff26b720cb0edd0e2c823272f04f4_l3.svg "Rendered by QuickLaTeX.com")  if and only if  ![A[j] < A[i]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-684f65ae1d3dd8d1e4c235ce0a52f233_l3.svg "Rendered by QuickLaTeX.com"), here i, j are indices and  ![i < j](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-b1defb86c67b74b14f33fe6eeb549bc3_l3.svg "Rendered by QuickLaTeX.com").  
Since  ![i<j](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-703cabd6e32ffadcd81985cc5dd18ff6_l3.svg "Rendered by QuickLaTeX.com"), the relative order is preserved  ![if A[i]\equiv A[j]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-0e0a7d4effb5635dcf90e9fb593eae45_l3.svg "Rendered by QuickLaTeX.com")  i.e.  ![A[i]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-4aaff26b720cb0edd0e2c823272f04f4_l3.svg "Rendered by QuickLaTeX.com")  comes before![ A[j]](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-bc58c90c6b04b4eeb97e44b1e6fef88d_l3.svg "Rendered by QuickLaTeX.com").  
Other non-comparison based sorts such as  [Counting Sort](https://www.geeksforgeeks.org/counting-sort/)  maintain stability by ensuring that the Sorted Array is filled in a reverse order so that elements with equivalent keys have the same relative position.  
Some sorts such as  [Radix Sort](https://www.geeksforgeeks.org/radix-sort/)  depend on another sort, with the only requirement that the other sort should be stable.

**Which sorting algorithms are unstable?**  
[Quick Sort](https://www.geeksforgeeks.org/quick-sort/),  [Heap Sort](https://www.geeksforgeeks.org/heap-sort/)  etc., can be made stable by also taking the position of the elements into consideration. This change may be done in a way which does not compromise a lot on the performance and takes some extra space, possibly  ![\theta(n)](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-2afd29ae12a2619ad56f4ef7a8695367_l3.svg "Rendered by QuickLaTeX.com").

**Can we make any sorting algorithm stable?**  
Any given sorting algo which is not stable can be modified to be stable. There can be sorting algo specific ways to make it stable, but in general, any comparison based sorting algorithm which is not stable by nature can be modified to be stable by changing the key comparison operation so that the comparison of two keys considers position as a factor for objects with equal keys.
More on:
[Stability of Sorting Algos](http://www.math.uic.edu/~leon/cs-mcs401-s08/handouts/stability.pdf), [Stability of Sorting Algos](http://en.wikipedia.org/wiki/Sorting_algorithm#Stability)
## Time Complexities of Sorting Algorithms

Efficiency of an algorithm depends on two parameters:

1. Time Complexity

2. Space Complexity

**Time Complexity:**  Time Complexity is defined as the number of times a particular instruction set is executed rather than the total time is taken. It is because the total time taken also depends on some external factors like the compiler used, processor’s speed, etc.

**Space Complexity:**  Space Complexity is the total memory space required by the program for its execution.

  

  

Both are calculated as the function of input size(n).

One important thing here is that in spite of these parameters the efficiency of an algorithm also depends upon the  **nature** and  **size of** the  **input.**

Following is a quick revision sheet that you may refer at last minute

|**Algorithm**|**Time Complexity**|
|--|--|
||**Best** - **Average** - **Worst** 
|[Selection Sort](http://geeksquiz.com/selection-sort/)|Ω(n^2) θ(n^2) O(n^2)|
|[Bubble Sort](http://geeksquiz.com/bubble-sort/)| Ω(n) θ(n^2) O(n^2)|
|[Insertion Sort](http://geeksquiz.com/insertion-sort/)|Ω(n) θ(n^2) O(n^2)|
|[Heap Sort](http://geeksquiz.com/heap-sort/)|Ω(n log(n)) θ(n log(n)) O(n log(n))|
|[Quick Sort](http://geeksquiz.com/quick-sort/)|Ω(n log(n)) θ(n log(n)) O(n^2)|
|[Merge Sort](http://geeksquiz.com/merge-sort/)|Ω(n log(n)) θ(n log(n)) O(n log(n))|

[Practice Sorting Questions here](https://practice.geeksforgeeks.org/topics/Sorting/)
[Sorting quiz](https://www.geeksforgeeks.org/algorithms-gq/searching-and-sorting-gq/)