#Numpy
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
* Even we dont need to type check for elements