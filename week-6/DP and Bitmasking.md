# DP AND BITMASKING

---

### Suppose we have a collection of elements which are numbered from 1 to N. If we want to represent a subset of this set then it can be encoded by a sequence of N bits (we usually call this sequence a “mask”). In our chosen subset the i-th element belongs to it if and only if the i-th bit of the mask is set i.e., it equals to 1. For example, the mask 10000101 means that the subset of the set [1… 8] consists of elements 1, 3 and 8. We know that for a set of N elements there are total 2N subsets thus 2N masks are possible, one representing each subset. Each mask is, in fact, an integer number written in binary notation.

### Our main methodology is to assign a value to each mask (and, therefore, to each subset) and thus calculate the values for new masks using values of the already computed masks. Usually our main target is to calculate value/solution for the complete set i.e., for mask 11111111. Normally, to find the value for a subset X we remove an element in every possible way and use values for obtained subsets X’1, X’2… ,X’k to compute the value/solution for X. This means that the values for X’i must have been computed already, so we need to establish an ordering in which masks will be considered. It’s easy to see that the natural ordering will do: go over masks in increasing order of corresponding numbers. Also, We sometimes, start with the empty subset X and we add elements in every possible way and use the values of obtained subsets X’1, X’2… ,X’k to compute the value/solution for X.

### To read more about Bitmasking and DP , click [here](https://www.geeksforgeeks.org/bitmasking-and-dynamic-programming-set-1-count-ways-to-assign-unique-cap-to-every-person/)

---

# DIGIT DP

### There are many types of problems that ask to count the number of integers ‘x‘ between two integers say ‘a‘ and ‘b‘ such that x satisfies a specific property that can be related to its digits.
### So, if we say G(x) tells the number of such integers between 1 to x (inclusively), then the number of such integers between a and b can be given by G(b) – G(a-1). This is when Digit DP (Dynamic Programming) comes into action. All such integer counting problems that satisfy the above property can be solved by digit DP approach.
 

## Key Concept:

### Let given number x has n digits. The main idea of digit DP is to first represent the digits as an array of digits t[]. Let’s say a we have tntn-1tn-2 … t2t1 as the decimal representation where ti (0 < i <= n) tells the i-th digit from the right. The leftmost digit tn is the most significant digit. 
 
### Now, after representing the given number this way we generate the numbers less than the given number and simultaneously calculate using DP, if the number satisfy the given property. We start generating integers having number of digits = 1 and then till number of digits = n. Integers having less number of digits than n can be analyzed by setting the leftmost digits to be zero. 

### To read more about this special problem type [here](https://www.geeksforgeeks.org/digit-dp-introduction/)
### For hard question practice , click [here](https://codeforces.com/blog/entry/67679)
