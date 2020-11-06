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



## Diving into code

####  Arrays
```python
import numpy as np

a = np.array([1,2,3])
print(a)
```

```python
b  = np.array([[9.0,8.0,7.0],[23.0,5.9,6.5]])

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

# Get Total size
a.size * a.itemsize
#or
a.nbytes
#Gives the same output

```


#### Accessing/CHanging specific elements, rows, columns, etc
```
a = np.array([[1,2,3,4,5,6,7],[8,9,10,11,12,13,14]])

# Get specific element
a[1][5] #prints 13

a[1][-2] #prints 13


# Get specific row
a[0, :]  #prints whole first row

#Get specific column
a[:,2]


# [startindex:endindex:stepsize]
a[0, 1:6:2]
# prints [2,4,6]


# Updating elements
a[1,5] = 20

a[:,2] = 5


# Getting specific elements
b = np.array([[[1,2],[3,4]],[[5,6],[7,8]]])
b[0,1,1] # prints 4


# Initialize all 0s matrix
np.zeros((2,3))
# Gives a matrix with 2 rows and 3 columns and all values as 0


# All 1s matrix
np.ones((4,2,2), dtype='int32')
# dtype is optional


# Any other number matrix
np.full((2,2),99)
# matrix of 2X2 with all values 99


# Any other number (full_like)
np.full_like(a.shape,4)


# Random decimal numbers between 0 and 1
np.random.rand(4,2)
np.random_sample(a.shape)


# Random integer values
np.random.randint(7, 90, size=(3,3))
# 7 is start value and 90 is ending


# Identity matrix
np.identity(5)


arr = np.array([[1,2,3]])
r1 = np.repeat(arr,3, axis=0)
print(r1)
