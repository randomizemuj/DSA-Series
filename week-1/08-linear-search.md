# Linear (a.k.a. Sequential Search)

* the simplest search technique
* "linear" because the time complexity is O(n)
* "sequential" because items are searched one by one
* also applicable for unsorted dataset.


To do a linear search :
 * Start from the leftmost element of arr[] and one by one compare x with each element of arr[]
 * If x matches with an element, return the index.
 * If x doesn’t match with any of elements, return -1.

---
**Input:**
```cpp
#include<iostream>
using namespace std;

int linSearch(int array[], int size, int key) {
   for(int i = 0; i<size; i++) {
      if(array[i] == key) //search key in each places of the array
         return i; //location where key is found for the first time
   }
   return -1; //when the key is not in the list
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

   if((loc = linSearch(arr, n, searchKey)) >= 0)
      cout << "Item found at location: " << loc << endl;
   else
      cout << "Item is not found in the list." << endl;
}
```

**Output:**
```
Enter number of items: 8
Enter items:
20 4 89 75 10 23 45 69
Enter search key to search in the list: 10
Item found at location: 4
```

---
> For more about linear search, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/linear-search/), [TutorialsPoint](https://www.tutorialspoint.com/Linear-Search)
> Practice [here](https://www.hackerearth.com/practice/algorithms/searching/linear-search/practice-problems/)
