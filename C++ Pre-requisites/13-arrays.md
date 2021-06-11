# Arrays In C++

C++ provides a data structure,  **the array**, which stores a fixed-size sequential collection of elements of the same type. An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.

Instead of declaring individual variables, such as number0, number1, ..., and number99, you declare one array variable such as numbers and use numbers[0], numbers[1], and ..., numbers[99] to represent individual variables. A specific element in an array is accessed by an index.

All arrays consist of contiguous memory locations. The lowest address corresponds to the first element and the highest address to the last element.

## Declaring Arrays

To declare an array in C++, the programmer specifies the type of the elements and the number of elements required by an array as follows −

```type arrayName [ arraySize ];```

This is called a single-dimension array. The  **arraySize**  must be an integer constant greater than zero and  **type**  can be any valid C++ data type. For example, to declare a 10-element array called balance of type double, use this statement −

```double balance[10];```
## Initializing Arrays

You can initialize C++ array elements either one by one or using a single statement as follows −

```double balance[5] = {1000.0, 2.0, 3.4, 17.0, 50.0};```

The number of values between braces { } can not be larger than the number of elements that we declare for the array between square brackets [ ]. Following is an example to assign a single element of the array −

If you omit the size of the array, an array just big enough to hold the initialization is created. Therefore, if you write −

```double balance[] = {1000.0, 2.0, 3.4, 17.0, 50.0};```

You will create exactly the same array as you did in the previous example.

```balance[4] = 50.0;```
The above statement assigns element number 5th  in the array a value of 50.0. Array with 4th  index will be 5th, i.e., last element because all arrays have 0 as the index of their first element which is also called base index. Following is the pictorial representaion of the same array we discussed above −

![Array Presentation](https://www.tutorialspoint.com/cplusplus/images/array_presentation.jpg)

## Accessing Array Elements

An element is accessed by indexing the array name. This is done by placing the index of the element within square brackets after the name of the array. For example −

double salary = balance[9];

The above statement will take 10th  element from the array and assign the value to salary variable. 

Arrays are important to C++ and should need lots of more detail. There are following few important concepts, which should be clear to you −
|Sr. No| Concept and Description|
|--|--|
|1|[Multi-dimensional arrays](https://www.tutorialspoint.com/cplusplus/cpp_multi_dimensional_arrays.htm "Multi-dimensional arrays in C++") C++ supports multidimensional arrays. The simplest form of the multidimensional array is the two-dimensional array.|
|2|[Pointer to an array](https://www.tutorialspoint.com/cplusplus/cpp_pointer_to_an_array.htm "Pointer to an array in C++") You can generate a pointer to the first element of an array by simply specifying the array name, without any index.|
|3|[Passing arrays to functions](https://www.tutorialspoint.com/cplusplus/cpp_passing_arrays_to_functions.htm "Passing arrays to functions as arguments in C++") You can pass to the function a pointer to an array by specifying the array's name without an index.|
|4|[Return array from functions](https://www.tutorialspoint.com/cplusplus/cpp_return_arrays_from_functions.htm "Return array from functions in C++") C++ allows a function to return an array.|

> For more information, visit: [GeeksForGeeks](https://www.geeksforgeeks.org/arrays-in-c-cpp/)
