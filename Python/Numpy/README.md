# Numpy

![image](./numpy.png)

## Why numpy over list?
* List are very slow as compared to Numpy

## Why is numpy faster?
* Every information is converted to binary.
* Numpy by default converts our number from integer to binary of int32/ int16/ int8
* Lists convert every data type or objects into bytes and then stores:
    * Size
    * Reference count
    * Object Type
    * Object Value
* Because numpy uses less bytes of memory hence it is faster
* Even we dont need to type check for elements in numpy as we have to do in list because it can contain various object types.
* Numpy utilises contiguous memory whereas list could take scattered memory spaces. Hence finding element and iterating takes time in list. Benefits:
    * SIMD(single instruction multiple data) vector processing 
    * Effective cache utilization

## Applications
* Many mathematical computations
* Plotting 
* Backend of many applications (Pandas)
* Machine learning



### Installing Numpy
Type
``` 
pip install numpy 
```
in your terminal or bash shell



## Running our first code

####  Arrays
```
import numpy as np

a = np.array([1,2,3])
print(a)
```

```
b  = np.array([[9.0,8.0,7.0],[23.0,5.9,65]])

# getting dimesions like a is 1D array and b is 2D array
a.ndim

# get shape
b.shape
# prints (2,3) because 2 is the rows and 3 coloumns

#Get type
a.dtype
# int32 by default is the type of numpy array


# changing dtype
a = np.array([1,2,3], dtypes='int16')
a.dtype
# gives int16 as data type


#Get Size
a.itemsize
# prints 2 as it is 16bits that is 2 bytes data type
