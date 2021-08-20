# Hashing
Hashing is the method by which we can map any length data element to a fixed size key. hashing works as key-value pairs.

![image](https://www.geeksforgeeks.org/wp-content/uploads/HashingDataStructure-min-768x384.png)


Hashing function is the function that does the mapping in a hash map. The data elements that are given as input to the Hash Function may get same hash key. 
In this case the elements may overlap. To avoid overlapping of elements which have the same hash key the concept of chaining was introduced.

In C++, we can implement hashing with unordered_map in stl. e.g. unordered_map<int,int> var;

For arrays and linked lists, we need to search in a linear fashion, which can be costly in practice. 
If we use arrays and keep the data sorted, then a number can be searched in O(Logn) time using Binary Search,
but insert and delete operations become costly as we have to maintain sorted order. 

With balanced binary search tree, we get moderate search, insert and delete times. All of these operations can be guaranteed to be in O(Logn) time. 
Hashing is the solution that can be used in almost all such situations and performs extremely well compared to above data structures like Array, Linked List, Balanced BST in practice.
With hashing we get O(1) search time on average (under reasonable assumptions) and O(n) in worst case. 

An array that stores pointers to records corresponding to a given phone number. 
An entry in hash table is NIL if no existing phone number has hash function value equal to the index for the entry. 

---
> To learn how to implement a hashing go [here](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/) and go [here](https://www.geeksforgeeks.org/hashing-data-structure/) to understand hashing better.

> Solve this [question](https://binarysearch.com/problems/Hash-Table) to gain better understanding of the concept.
