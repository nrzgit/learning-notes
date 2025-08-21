# NumPy
### How to download:
    pip install numpy
### How to connect library:
    import numpy as np
### How to create array:
    a = np.array([1, 2, 3, 4]) #One-dimensional array
    a = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]]) #Two-dimensional array
    print(a[0]) #One-dimensional array Output: 1
    print(a[1][2]) #Two-dimensional array Output: 7
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
  
