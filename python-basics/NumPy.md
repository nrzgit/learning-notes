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

***np.unique()***-get all unique elements from the array

## Sorting the NumPy array:
***np.sort(a)***-it return sorted an array `array does not change`

***np.argsort(a)***-returns an "array with indexes" indicating how the array was sorted

## Features
***np.random.random(n)***- return an array of float numbers in the range from 0.0 to 1.0

***np.random.randint(0, 10, size=10)***-returns a random integer within the specified range. The third parameter size can be used to pass the length of the returned array. By default, it is 1

***np.random.rand(n, m)***- takes two parameters as input and returns an array filled with random numbers of size n*m

***np.random.normal(n, m, size=(x, y))***-- returns a sample from a normal (Gaussian) distribution, where n is the "center" of the distribution, m is the deviation, and the tuple in the size parameter is the size of the returned array (x*y).

***np.arange(n, m, x)***-n-start, m-end, x-step.

# Additional Useful NumPy Features for ML/AI Engineers

Below are some highly useful NumPy functions for ML/AI engineers, with copy-paste ready Python code examples.

---

## 1. Advanced Indexing and Slicing

```python
import numpy as np
a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
print(a[0, :])         # First row
print(a[:, 1])         # Second column
print(a[a > 4])        # Elements greater than 4
```

---

## 2. Broadcasting

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
b = np.array([1, 0, 1])
print(a + b)   # Adds b to each row of a (broadcasting)
```

---

## 3. Reshaping and Transposing

```python
a = np.arange(12)
b = a.reshape(3, 4)    # Reshape to 3x4
print(b)
print(b.T)             # Transpose
print(b.flatten())     # Flatten to 1D
```

---

## 4. Linear Algebra (`numpy.linalg`)

```python
from numpy.linalg import inv, eig, svd, det

A = np.array([[1, 2], [3, 4]])
print(inv(A))          # Inverse
vals, vecs = eig(A)    # Eigenvalues and eigenvectors
print(vals, vecs)
U, S, Vt = svd(A)      # SVD decomposition
print(U, S, Vt)
print(det(A))          # Determinant
```

---

## 5. Statistics

```python
a = np.array([1, 2, 3, 4, 5])
print(np.median(a))        # Median
print(np.std(a))           # Standard deviation
print(np.var(a))           # Variance
print(np.percentile(a, 50))# 50th percentile
print(np.cov(a))           # Covariance
print(np.corrcoef(a))      # Correlation coefficient
```

---

## 6. Stacking and Splitting

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
print(np.vstack([a, b]))      # Vertical stack
print(np.hstack([a, b]))      # Horizontal stack
c = np.array([[1, 2], [3, 4], [5, 6]])
print(np.split(c, 3))         # Split into 3 arrays
```

---

## 7. Saving and Loading Data

```python
a = np.array([[1, 2], [3, 4]])
np.save('my_array.npy', a)        # Save to .npy file
b = np.load('my_array.npy')       # Load from .npy file
np.savetxt('my_array.txt', a)     # Save to .txt file
c = np.loadtxt('my_array.txt')    # Load from .txt file
```

---

## 8. Where and Conditional Logic

```python
a = np.array([1, 2, 3, 4, 5])
b = np.where(a > 3, a, 0)         # Replace elements <=3 with 0
print(b)
```

---

## 9. Unique & Counting

```python
a = np.array([1, 2, 2, 3, 3, 3])
print(np.unique(a))               # Unique values
print(np.bincount(a))             # Count occurrences of each value
print(np.count_nonzero(a == 3))   # Count elements equal to 3
```

---

## 10. Advanced Random Sampling

```python
print(np.random.choice([1, 2, 3, 4], size=2)) # Randomly choose 2 elements
a = np.arange(10)
np.random.shuffle(a)                          # Shuffle array in-place
print(a)
```
