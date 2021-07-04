# Declaring Arrays
To declare an array in C++, the programmer specifies the type of the elements and the number of elements required by an array as follows −

```
type arrayName [ arraySize ];
```

This is called a single-dimension array. The arraySize must be an integer constant greater than zero and type can be any valid C++ data type.  
For example, to declare a 10-element array called balance of type double, use this statement −
```cpp
double balance[10];
```

---
# Initializing Arrays

You can initialize C++ array elements either one by one or using a single statement as follows −

```cpp
double balance[5] = {1000.0, 2.0, 3.4, 17.0, 50.0};
```
**Note:** The number of values between braces { } can not be larger than the number of elements that we declare for the array between square brackets [ ].

If you *_omit the size of the array_*, an array just big enough to hold the initialization is created. Therefore, if you write −

```cpp
double balance[] = {1000.0, 2.0, 3.4, 17.0, 50.0};
```

You will create exactly the same array as you did in the previous example.

---

# Accessing Array Elements

An element is accessed by indexing the array name. This is done by placing the index of the element within square brackets after the name of the array. For example −
```cpp
double salary = balance[9];
```
The above statement will take 10th element from the array and assign the value to salary variable.

---

> Practice questions on arrays [here](https://practice.geeksforgeeks.org/explore/?category%5B%5D=Arrays&page=1&category%5B%5D=Arrays).
