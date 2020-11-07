# Numpy

![image](./numpy.png)

NumPy is the fundamental package needed for scientific computing with Python.

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
```python
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


# Arange() to initialize the array
np.arange(4)   # this will give an array [0,1,2,3]

np.arange(4,10)   # this will give an array [4,5,6,7,8,9]

np.arange(4,20,3)    # this will give an array [4,7,10,13,16,19] that is arange(start, stop, size)


# Linspace: similar to arrange() but here instead of range of the output it takes number of dispaces that it has to leave between start and stop term.
a = np.linspace(1,2,11)   # It will create an array of [1. , 1.1, 1.2, 1.3, 1.4, 1.5, 1.6, 1.7, 1.8, 1.9, 2. ]

```



#### Coppying arrays
```python
a = np.array([1,2,3])
b = a
b[0] = 100
# Here a also changes with b

b = a.copy()
b[0] = 123
# Now it is safe to copy a to b
```

#### Mathematics
```python
a = np.array([1,2,3,4])
a + 2 #add 2 to each element
a - 2 #subtract 2 from each element
a * 2 #multiply 2 from each element
a / 2 #divide 2 by each element
a += 2

b = np.array([1,0,1,0])
a + b

a ** 2 #power of 2

np.sin(a) #takes sin of all values in array a

np.cos(a) #takes cos of all values in array a

```

#### Linear Algebra
```python
a = np.ones((2,3))
b = np.full((3,2),2)
np.matmul(a,b)
# Multiply matrices

#Finding the determinant
c = np.identity(3)
np.linalg.det(c)
```

##### Found that axis=0 is for coloumn wise values and axis=1 is for row wise values.


#### Statistics
```python
stats = np.array([[1,2,3],[4,5,6]])
np.min(stats, axis=1) 

np.max(stats, axis=1)

np.sum(stats, axis=0)
```

#### Reorganizing arrays
```python
before = np.array([[1,2,3,4],[5,6,7,8]])
after = before.reshape((2,2,2)) 
# It changes the shape of the matrix as long as the matrix could be converted to the shape provided. That is it has that much elements


# Vertically stacking vectors
v1 = np.array([1,2,3,4])
v2 = np.array([5,6,7,8])

np.vstack([v1,v2,,v1,v2,v2])

# Horizontal stack
h1 = np.ones((2,4))
h2 = np.zeros((2,2))

np.hstack((h1,h2))

```


#### Miscellaneous
```
filedata = np.genfromtext('data.txt',delimiter=',')

filedata = filedata.astype('int32')


# Boolean Masking and advanced indexing

filedata>50
filedata[filedata>50]

#Could index with a list in numpy
np.array([1,2,3,4,5,6,7,8,9])
a[[1,2,8]]
# Outputs 2,3,9 because they are present in the index of 1,2,8


np.any(filedata>50, axis=0)
np.all(filedata>50, axis=0)

(~((filedata>50) & (filedata<100)))
((filedata>50) & (filedata<100))
```


Major part of this page i learnt from https://www.youtube.com/watch?v=GB9ByFAIAH4


