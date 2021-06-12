# Ternary Search

* for sorted lists
* a divide and conquer algorithm
* We divide the given array into three parts and determine which has the key (searched element). We can divide the array into three parts by taking mid1 and mid2 which can be calculated as shown below. Initially, l and r will be equal to 0 and n-1 respectively, where n is the length of the array. 

```
mid1 = l + (r-l)/3 
mid2 = r – (r-l)/3 
```
## Steps to perform Ternary Search: 
* First, we compare the key with the element at mid1. If found equal, we return mid1.
* If not, then we compare the key with the element at mid2. If found equal, we return mid2.
* If not, then we check whether the key is less than the element at mid1. If yes, then recur to the first part.
* If not, then we check whether the key is greater than the element at mid2. If yes, then recur to the third part.
* If not, then we recur to the second (middle) part.

---
## The complexity of Ternary Search Technique

* Time Complexity: O(log3 n)
* Space Complexity: O(1)

---

**Input:**
```cpp
#include<iostream>
using namespace std;

int ternarySearch(int array[], int start, int end, int key) {
   if(start <= end) {
      int midFirst = (start + (end - start) /3); //mid of first and second block
      int midSecond = (midFirst + (end - start) /3); //mid of first and second block
      if(array[midFirst] == key)
         return midFirst;
      if(array[midSecond] == key)
         return midSecond;
      if(key < array[midFirst])
         return ternarySearch(array, start, midFirst-1, key);
      if(key > array[midSecond])
         return ternarySearch(array, midSecond+1, end, key);
      return ternarySearch(array, midFirst+1, midSecond-1, key);
   }
   return -1;
}

int main() {
   int n, searchKey, loc;
   cout << "Enter number of items: ";
   cin >> n;
   int arr[n]; //create an array of size n
   cout << "Enter items: " << endl;

   for(int i = 0; i< n; i++) {
      cin >> arr[i];
   }

   cout << "Enter search key to search in the list: ";
   cin >> searchKey;
   if((loc = ternarySearch(arr, 0, n, searchKey)) >= 0)
      cout << "Item found at location: " << loc << endl;
   else
      cout << "Item is not found in the list." << endl;
}
```

**Output:**
```
Enter number of items: 8
Enter items:
12 25 48 52 67 79 88 93
Enter search key to search in the list: 52
Item found at location: 3
```

---
[Why is Binary Search preferred over Ternary Search?](https://www.geeksforgeeks.org/binary-search-preferred-ternary-search/)

> For more information about ternary search, visit: [TutorialsPoint](https://www.tutorialspoint.com/Binary-Search), [GeeksForGeeks](https://www.geeksforgeeks.org/ternary-search/).
