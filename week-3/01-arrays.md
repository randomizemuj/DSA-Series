# Introduction to Arrays

An array is a collection of items stored at contiguous *(adjacent)* memory locations. The idea is to store multiple items of the same type together. This makes it easier to calculate the position of each element by simply adding an offset to a base value *(the memory location of the first element of the array).*  
The base value is index 0 and the difference between the two indexes is the offset.  
__Remember: “Location of next index depends on the data type we use”.__

<div align='center'>
<img src=https://beginnersbook.com/wp-content/uploads/2018/10/array.jpg>
</div>

---

## Why do we need arrays?

We can use normal variables (v1, v2, v3, ..) when we have a small number of objects, but if we want to store a large number of instances, it becomes difficult to manage them with normal variables. The idea of an array is to __*represent many instances in one variable.*__

## Array’s size

In C++, array has a fixed size meaning once the size is given to it, it cannot be changed i.e. you can’t shrink it neither can you expand it. The reason was that for expanding, if we change the size we can’t be sure ( it’s not possible every time) that we get the next memory location to us as free. The shrinking will not work because the array, when declared, gets memory statically allocated, and thus compiler is the only one can destroy it.

## Indexing

Elements can be accessed randomly using indices of an array. The various types of indexing are as follows:

*     0 (zero-based indexing): The first element of the array is indexed by a subscript of 0.
* 1 (one-based indexing): The second element of the array is indexed by the subscript of 1.
* n (n-based indexing): The base index of an array can be freely chosen. Usually, programming languages allowing n-based indexing also allow negative index values, and other scalar data types like enumerations, or characters may be used as an array index.
---

## Advantages of using arrays:

* Arrays allow random access to elements. This makes accessing elements by position faster.
* Arrays have better cache locality. When you access memory, a chunks of it are cached at various levels. Cache locality refers to the likelihood of successive operations being in the cache and thus being faster. In an array, you maximize the chances of sequential element access being in the cache.
* Arrays represent multiple data items of the same type using a single name.

## Disadvantages of using arrays:
You can’t change the size i.e. once you have declared the array you can’t change its size because of static memory allocation. Here Insertion(s) and deletion(s) are difficult as the elements are stored in consecutive memory locations and the shifting operation is costly too.

___

> To read more about Arrays, visit [GeeksForGeeks](https://www.geeksforgeeks.org/introduction-to-arrays/).

>Learn more about cache locality [here](https://stackoverflow.com/questions/12065774/why-does-cache-locality-matter-for-array-performance).
