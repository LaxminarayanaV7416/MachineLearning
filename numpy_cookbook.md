### Lets begin our numpy Cookbook

```Python
import numpy as np
```

#### Visit Numpy documentation for more information other than examples here
```Python
#lets create some arrays using numpy
# row vector
row = np.array([1,2,3])
# column vector 
col = np.array([[1],
                [2],
                [3]])

# well to summarize numpy arrays as multidimensional arrays just for simplicity we have created a one dimensional
# arrays but we will see how to dwell deep into numpy's multidimensional arrays. and these arrays represent 
# horizontally -> rows and vertically -> columns 
```
* now lets work with the two dimensional arrays which are like matrix, lets walk through them
```Python
#well we can call array also as matrix 
mat = np.array([[1,2],
                [3,4],
                [5,6]])
#or else we can use np.mat to call it matrix (well np.mat is traditional matrix option in numpy)
matri = np.mat([[1,2],
                [3,4],
                [5,6]])
# NOTE : use of matrix isnt recommended since most of the numpy options returns arrays not matrixs
# we can have a look at sparse matrix from scipy.sparse where it has options like csr,csc to store only non zero values
```
* now lets talk about describing the arrays
```Python
#lets create a three dimensional array 
three_d = np.array([
    [
        [1,2,3],
        [4,5,6]
    ],
    [
        [7,8,9],
        [10,11,12]
    ]
                  ])
# for better understanding of the three dimensional array
three_d.shape # outputs (2,2,3)
# which says that it has (2 -> rows{i},(2,3) -> columns{}i) for diggning deep (2 -> rows{ii},3 -> columns{ii})
three_d.size # outputs 12 -> which is basically multiplication of all dimensions
three_d.ndim # outputs 3 -> indicates we have created a 3D array succesfully
three_d.dtype # outputs dtype('int32') 
# NOTE : visit the numpy documentation for better undestanding of numpy datatypes
```
* Now lets see how to access the variables also known as array slicing 

```Python
x = np.array([[1,2,3],
              [4,5,6]])
#lets see how to access only four its simple remember rows X columns 
x[1,0] #ouputs 4
#lets print the 10,11,12 from 3d array above
three_d[1,1,:] #outputs array([10,11,12])
```

* Now lets talk about broadcasting technque and how its used in numpy : in traditional lists we can access an element and apply some function over that element, but numpy uses broadcasting technique which is nothing but if we apply any function it will applied to every element in the array (we can restrict no doubt, but default mechanism is broadcasting). lets see some vectorise examples how to apply some fucntions over numpy arrays
  
```python
# lets create an array
array = np.array([[1,2,3],
                  [4,5,6],
                  [7,8,9]])
# now lets create a fucntion which will consume one element and multiply with 10
def ten_mul(ele):
    return ele*10
#### (OR) ####
ten_mul = lambda x : x*10
#now lets make this python function behave like numpy broadcasting function its nothing but we are making normal function to numpy vectorize fucntion
ten_mul_numpy = np.vectorize(ten_mul)

#now we can go and apply this vectorized fucntion to our array
ten_mul_numpy(array)
# outputs array([[10,20,30],
#                [40,50,60],
#                [70,80,90]])
#### (OR) ####
array*10 # will also give you same results
```
* now lets get into satistics part of arrays, we will try to find min, max, mean, variance, standard deviation,median of the array defined above
```Python
np.max(array) # outputs 9
np.min(array) # outputs 1
np.max(array,axis=1) #outputs array([3,6,9])
np.max(array,axis=0) # outputs array([7, 8, 9])
np.mean(array) # outputs 5.0
np.median(array) # outputs 5.0
np.var(array) # outputs 6.666666666666667
np.std(array) # outputs 2.581988897471611

# NOTE : we can use axis to find out row wise or column wise stats in numpy array by default the axis is set to None
```
* Now lets talk about reshaping of arrays
``` Python 
# NOTE : the reshape dimensions should match with the size of array we are going to reshape, cheat purpose we can make use of -1 if thez size is unknown in first place
array.reshape(1,-1) # outputs array([[1, 2, 3, 4, 5, 6, 7, 8, 9]])
array.flatten() # does the same thing as above
array.reshape(9,1) # creates a column vector
three-d.reshape(6,2) #here we are converting 3D to 2D array

#lets talk about transpose of array also -> whcih means converting volumns to rows and rows to columns
array.T #this transpose of the array
```
* now lets get into some linear algebra which are very much useful during machine learning and deep learning

```Python 
#finding rank of the array
np.linalg.matrix_rank(array) #simpliest way to find the rank of matrix or array

#calculating determinent of array
np.linalg.det(array)

#getting diagonal elements in the array
array.diagonal() # we can use offset options as 1 to indicate above diagonal elements , -1 to refer below diagonal elements, please refer the numpy documentation

#eigen values and eigen vectors of the array
eigvalues ,eigvectors = np.linalg.eig(array)

# Dot product of two arrays
np.dot(array1,array2)
#### (OR) ####
array1 @ array2 #(python >3.5+)

np.add(array1,array2) # array1 + array2
np.subtract(array1,array2) # array1 - array2

# for element wise multiplication use * 
array1 * array2

#inverse of the array 
np.linalg.inv(array)
```
* Now lets talk about random numbers generation
* we can use numpy random methods to generate the random numbers here are important use cases

```python 
# NOTE : to set the seed so that next time your program will generate same numbers again
seed=42

# to generate numbers between 0.0 and 1.0 for 10 random numbers
np.random.random(10)

# to generate only integers use randint
np.random.randint(10)

# to genrate numbers with normal distribution of mean 0.0, and std 1.0
np.random.normal(0.0, 1.0, 10) # generates 10 numbers

#to generate logistic distribution with mean 0.0 and sacle 1.0
np.random.logistic(0.0, 1.0, 10)

#to uniformaly genrate numbers between specified numbers here we are using 1 and 2
np.random.uniform(1, 2, 10)
```