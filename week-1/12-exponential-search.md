# Exponential Search (a.k.a. doubling or galloping search)

* The name comes from the way it searches an element.
* If L and U are the upper and lower bound of the list, then L and U both are the power of 2. For the last section, the U is the last position of the list. For that reason, it is known as exponential.
* particularly useful for _unbounded searches_, where size of array is infinite.
* It works better than Binary Search for bounded arrays, and also when the element to be searched is closer to the first element.
---

Exponential search involves two steps:  
* Find range where element is present
* Do Binary Search in above found range.

## How to find the range where element may be present? 

The idea is to start with subarray size 1, compare its last element with x, then try size 2, then 4 and so on until last element of a subarray is not greater. 
Once we find an index i (after repeated doubling of i), we know that the element must be present between i/2 and i (Why i/2? because we could not find a greater value in previous iteration)
Given below are the implementations of above steps.

---

## The complexity of Exponential Search Technique
* Time Complexity: O(1) for the best case. O(log2 i) for average or worst case. Where i is the location where search key is present.
* Space Complexity: O(1)
---
**Input:**
```cpp
// C++ program to find an element x in a
// sorted array using Exponential search.
#include <bits/stdc++.h>
using namespace std;

int binarySearch(int arr[], int, int, int);

// Returns position of first occurrence of
// x in array
int exponentialSearch(int arr[], int n, int x)
{
	// If x is present at firt location itself
	if (arr[0] == x)
		return 0;

	// Find range for binary search by
	// repeated doubling
	int i = 1;
	while (i < n && arr[i] <= x)
		i = i*2;

	// Call binary search for the found range.
	return binarySearch(arr, i/2,
							min(i, n-1), x);
}

// A recursive binary search function. It returns
// location of x in given array arr[l..r] is
// present, otherwise -1
int binarySearch(int arr[], int l, int r, int x)
{
	if (r >= l)
	{
		int mid = l + (r - l)/2;

		// If the element is present at the middle
		// itself
		if (arr[mid] == x)
			return mid;

		// If element is smaller than mid, then it
		// can only be present n left subarray
		if (arr[mid] > x)
			return binarySearch(arr, l, mid-1, x);

		// Else the element can only be present
		// in right subarray
		return binarySearch(arr, mid+1, r, x);
	}

	// We reach here when element is not present
	// in array
	return -1;
}

// Driver code
int main(void)
{
int arr[] = {2, 3, 4, 10, 40};
int n = sizeof(arr)/ sizeof(arr[0]);
int x = 10;
int result = exponentialSearch(arr, n, x);
(result == -1)? printf("Element is not
							present in array")
				: printf("Element is present
								at index %d",
									result);
return 0;
}

```
**Output:**
```
Element is present at index 3
```
---

> Learn more about Exponential search [here](https://www.tutorialspoint.com/Exponential-Search) and [here](https://www.geeksforgeeks.org/exponential-search/).




