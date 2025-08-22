# Introduction to NumPy
[Click](https://habr.com/ru/articles/768188/)
### How to download:
    pip install numpy
### How to connect library:
    import numpy as np
### How to create array:
```python
a = np.array([1, 2, 3, 4]) #One-dimensional array  
a = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]]) #Two-dimensional array  
print(a[0]) #One-dimensional array Output: 1  
print(a[1][2]) #Two-dimensional array Output: 7  
```
`the type of dates must be one type(dtype)`
### How to print array:
    print(a) 
    #Output:
    [[ 1  2  3  4]
    [ 5  6  7  8]
    [ 9 10 11 12]]
    print(*a)
    #Output:
    [1 2 3 4] [5 6 7 8] [ 9 10 11 12]
## Data types in NumPy
| Data Type | Description|
|:-----------:|:------------:|
|bool|True or False|
|int|whole number(like long, int64, int32 from C)|
|intc|(like int, int32, int64 from C)|
|intp|whole number which need for use like index|
|int8|byte from -128 to 127|
|int16|whole number from -32768 to 32767|
|int32|whole number from -2147483648 to 2147483647|
|int64|from -9223372036854775808 to 9223372036854775807|
|unit8|whole number from 0 to 255|
|unit16|whole number from 0 to 65535|
|unit32|whole number from 0 to 4294967295|
|unit64|whole number from 0 to 18446744073709551615|
|float|float64|
|float16|float number,5-bit exponent, 10-bit mantissa|
|float32|8-bit exponent, 23-bit mantissa|
|float64|11-bit exponent, 52-bit mantissa|
|complex|complex128|
|complex64|complex number 32 bit, float|
|complex128|complex number 64 bit, float|

## Most important attributes:
***a.ndim***-return count of  array dimensions  
Return: 2 if two dimensional array / 1 if one dimensional array  

***a.shape***-return tuple which show size of array in per dimension  
Return: (3, 4) it mean that array has 3 rows and 4 columns  

***a.dtype***-return type of elements in array  

***a.itemsize***-return the size of max eliment in array
If Array`s dtype is int32 this command will return 4, if float64 - 8

***a.diagonal()***-return diagonal of matrix 

***a.sum()***-return the sum of all elements

***a.mean()***-return math avarage of all elements

***a.min(), a.max()***-return max and min of elements

***argmin(), argmax()***-return their indexs

## Main function of NumPy:
***np.zeros((n, m), type of data)***-make an array size n*m which filled with zeros

***np.ones((n, m), type)***-make an array size n*m which filled with 1

***np.empty((n, m), ...)***-return empty an array size n*m which filled with trash

***np.copy(array)***-make copy of array

***np.array(a, copy=True)***-simmilar

***np.eye(n, data type)***-n is count of row and col where dioganal filled with 1 `

***np.dot(a, b)***-the scalar multiplie of two arrays.Or **a.dot(b)**, **a & b**

```python
import numpy as np
a = np.array([[1, 2, 3, 4.0],
[5, 6, 7, 8],
[9, 10, 11, 12],
[3, 4, 5, 6]])
b = np.eye(4)
print(np.dot(a, b))
print(a.dot(b))
print(a @ b)
```
Output:
```
[[1, 2, 3, 4.0],
[5, 6, 7, 8],
[9, 10, 11, 12],
[3, 4, 5, 6]]
```
`By the way, I want to draw your attention to an interesting property of a unit matrix. When multiplied by it, the array does not change, as for example here, array a after multiplying by a unit matrix b does not change. This feature is used quite often, for example, in deep learning.`

***np.prod(a)***-multiply all the elements in the array

***np.sin(), np.cos(), np.tan()***, etc. - will return a sine, cosine, tangent, etc., respectively. They can be applied to a single number or to an array with any number of dimensions

***np.sqrt()***-returns the square root of a number or array in parentheses

| Operation | Description |
|:---------:|:-----------|
| +  | Adding arrays or an array with a number |
| -  | Subtracting arrays or an array with a number, or used as a unary minus |
| *  | Multiplication of arrays or array with a number |
| /  | Dividing arrays or arrays with a number |
| // | Integer division of arrays or array with a number |
| ** | Exponentiation (either a number or an array is specified) |
| %  | Calculations of the remainder of division (specify either a number or an array) |
