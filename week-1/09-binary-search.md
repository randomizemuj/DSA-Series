# Binary Search

* to search a sorted array
* repeatedly divide the search interval in half (hence "binary")
* We basically ignore half of the elements after each comparison.

To perform a binary search:
* Compare x with the middle element.
* If x matches with the middle element, we return the mid index.
* Else If x is greater than the mid element, then x can only lie in the right half subarray after the mid element. So we recur for the right half.
* Else (x is smaller) recur for the left half.
---
## The complexity of Binary Search Technique

* Time Complexity: O(1) for the best case. O(log2 n) for average or worst case.
* Space Complexity: O(1) 
---
**Input:**

```cpp
// C++ program to implement recursive Binary Search
#include <bits/stdc++.h>
using namespace std;

// A recursive binary search function. It returns
// location of x in given array arr[l..r] is present,
// otherwise -1
int binarySearch(int arr[], int l, int r, int x)
{
	if (r >= l) {
		int mid = l + (r - l) / 2;

		// If the element is present at the middle
		// itself
		if (arr[mid] == x)
			return mid;

		// If element is smaller than mid, then
		// it can only be present in left subarray
		if (arr[mid] > x)
			return binarySearch(arr, l, mid - 1, x);

		// Else the element can only be present
		// in right subarray
		return binarySearch(arr, mid + 1, r, x);
	}

	// We reach here when element is not
	// present in array
	return -1;
}

int main(void)
{
	int arr[] = { 2, 3, 4, 10, 40 };
	int x = 10;
	int n = sizeof(arr) / sizeof(arr[0]);
	int result = binarySearch(arr, 0, n - 1, x);
	(result == -1) ? cout << "Element is not present in array"
				: cout << "Element is present at index " << result;
	return 0;
}
```

**Output:**
```
Element is present at index 3
```

---
> Practice Binary Search [here](https://www.hackerearth.com/practice/algorithms/searching/binary-search/practice-problems/) and [here](https://leetcode.com/tag/binary-search/).
