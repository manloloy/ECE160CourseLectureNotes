# Plotting using Matplotlib
Data visualization plays a big part in the data science life cycle. In particular, data scientists often create data visualizations to gain insight on data and develop a scope for a machine learning task. While several data visualization packages are available in Python, Matplotlib is the most common. Matplotlib is a package used to create static, dynamic, and interactive plots. Seaborn, another common data visualization package used primarily for statistical graphs, is based on Matplotlib. Matplotlib can be downloaded and installed from https://matplotlib.org/stable/users/installing/index.html.

Matplotlib uses figures to hold plot elements, such as axes, labels, tick marks, and legends. Each element can be adjusted manually. Ex: Positions of minor and major tick marks can be controlled as well as the font sizes for the labels.

Figures can be created using the pyplot library, a state-based interface to the Matplotlib package that uses a syntax similar to MATLAB. Each line of code adds a plot element to the figure one at a time, while preserving previously added elements in the figure. To learn more about common functions within the pyplot library, see the pyplot documentation.




```python
# Matplotlib
import matplotlib.pyplot as plt

# this is y = x
x = [0, 1, 2, 3, 4, 5]
y = [0, 1, 2, 3, 4, 5]

plt.plot(x, y)

```




    [<matplotlib.lines.Line2D at 0x7e85e2aebaf0>]




    
![png](L28%20-%20Plotting%20%26%20Numpy_files/L28%20-%20Plotting%20%26%20Numpy_1_1.png)
    



```python
import matplotlib.pyplot as plt
# f(x) = x^2
# y = x^2
x=[]
y=[]
for i in range(-5, 6):
  x.append(i)
  y.append(i**2)
plt.plot(x, y)

```




    [<matplotlib.lines.Line2D at 0x7a9c6acfc190>]




    
![png](L28%20-%20Plotting%20%26%20Numpy_files/L28%20-%20Plotting%20%26%20Numpy_2_1.png)
    



```python
y=[]
x=[]
steps = list(range(-100,110))
steps = [j/10 for j in steps]
for i in steps:
  x.append(i)
  y.append(i**2)
plt.plot(x, y)
```




    [<matplotlib.lines.Line2D at 0x7e85e2de2260>]




    
![png](L28%20-%20Plotting%20%26%20Numpy_files/L28%20-%20Plotting%20%26%20Numpy_3_1.png)
    



```python
import matplotlib.pyplot as plt
# shifted parabola
# f(x) = (x-3)^2 + 5
# y = (x-3)^2 + 5


# let's try to generate from -10 to 10
x=[]
y=[]

r =  -10
while r <= 16:
  x.append(r)
  r += 0.25

for value in x:
  y.append((value-3)**2 + 5)
plt.plot(x, y)
```




    [<matplotlib.lines.Line2D at 0x7a9c6ab5cf40>]




    
![png](L28%20-%20Plotting%20%26%20Numpy_files/L28%20-%20Plotting%20%26%20Numpy_4_1.png)
    


# Numpy
The NumPy (pronounced "Num-pie") package provides tools for mathematical computations in Python. Ex: NumPy includes functions to perform common linear algebra operations, fast fourier transforms, and statistics. NumPy is used frequently in data science and statistical analysis. NumPy is also frequently used with other data science packages, such as pandas and Matplotlib. NumPy can be downloaded and installed from https://numpy.org/install/.

NumPy provides a multidimensional array object, conceptually similar to a list, consisting of an ordered set of elements of the same type. NumPy arrays benefit from having more mathematical support than lists and also perform mathematical operations faster than lists, because a NumPy array is a wrapper around fast native code that is compiled to run on a specific processor instead of in the Python interpreter.

To use NumPy in a program, the package is often imported with the alias np.


```python
# Numpy Example
import numpy as np

list1 = [15.5, 25.11, 19.0]
list2 = [12.2, 1.3, 6.38]

# Create two 1-dimensional (1D) arrays
# with the elements of the above lists
array1 = np.array(list1)
array2 = np.array(list2)

# Concatenate two lists python3
print('Concatenation of list1 and list2 =', end=' ')
print(list1 + list2)
print()

# Sum two lists in python3
print('Sum of list1 and list2 =', end=' ')
for i in range(len(list1)):
    print(list1[i] + list2[i], end=' ')
print('\n')

# Sum two 1D arrays use numpy
print('Sum of array1 and array2 =', end=' ')
print(array1 + array2)
```

    Concatenation of list1 and list2 = [15.5, 25.11, 19.0, 12.2, 1.3, 6.38]
    
    Sum of list1 and list2 = 27.7 26.41 25.38 
    
    Sum of array1 and array2 = [27.7  26.41 25.38]


# NumPy arrays
The NumPy array data type is called ndarray, where "nd" stands for N-dimensional and N can be any number of dimensions.

A zero-dimensional array consists of a scalar object. Ex: 2.
A one-dimensional array consists of a container of scalars. Ex: [2, 4, 6, 8].
A two-dimensional array consists of a container of containers of scalars. 2D arrays have rows and columns. Ex: [ [2, 4, 6, 8], [12, 14, 16, 18] ], which appears as
```
[[2 4 6 8]
 [12 14 16 18]]
```
 when output to the screen.
An N-dimensional array has N levels of nested containers. At each level, all containers must have the same number of elements. The shape of an array is a tuple of the lengths of each of the array's dimensions. The size of an array is the total number of elements in an array. Ex: The shape of the 2D array [ [2, 4, 6, 8], [12, 14, 16, 18] ] is (2, 4) and the size of the array is 8.
An array is created using NumPy's array() function.




```python
import numpy as np
# Create 2D array
my_array = np.array([[1, 2, 3], [21, 22, 23]])

print('my_array:')
print(my_array)
print(f'my_array shape: {my_array.shape}')
print(f'my_array size: {my_array.size}')

```

    my_array:
    [[ 1  2  3]
     [21 22 23]]
    my_array shape: (2, 3)
    my_array size: 6


# Array axis
A NumPy array axis is a direction along each array dimension. 1D arrays have 1 axis, 2D arrays have 2 axes, etc. Discussion of axes occurs most frequently when dealing with 2D arrays. In a 2D array, axis 0 is the first axis that runs down the array's rows and axis 1 is the second axis that runs across the array's columns.

Many NumPy functions and methods take an axis argument which determines along which axis the function should operate.

1. In a 2D array, axis 0 indicates the direction along the array's rows and axis 1 indicates the direction along the array's columns.
2. Many NumPy array functions and methods, such as numpy.delete() and ndarray.sort(), take an axis argument to indicate which axis to work along.
3. The delete() function removes the row (axis 0) or column (axis 1) indicated by the index. When index is 1 and axis is 1, the second column is removed. The returned array has a (4, 2) shape.
4. The array sort() method can take an axis argument to indicate which axis to sort along. If axis is 0, sorting happens ascending order in each column downwards along the rows.


# Creating and modifying arrays
A NumPy array is an ordered, indexed, and mutable container. NumPy provides many functions to create and modify arrays. Though mutable, NumPy arrays have a fixed shape, so any operation to change an array's shape actually creates a new version (a new Python object) of the array with the intended modification, leaving the original unchanged.

If the elements in the array are unknown before creation, certain NumPy functions create placeholder values that can be changed during a program's run. Ex: np.zeros((1, 3)) creates a (1, 3) shape array filled with 0s and np.ones((1, 3)) creates a (1, 3) shape array filled with 1s.

Some NumPy operations are instance methods of the object, Ex: array.sort(), while other NumPy operations are functions of the NumPy module, Ex: np.delete(). This material takes an object-oriented approach and uses array methods. NumPy functions are used where array methods don't exist.


```python

```


```python
# numpy 3 x 3 addition example
# compare with python3

import numpy as np
lst1 = [[1,2,3],[4,5,6],[7,8,9]]
lst2 = [[1,2,3],[4,5,6],[7,8,9]]

# the python way
# result = element by element addition of lst1 and lst2
result = []
for i in range(len(lst1)):
  row = []
  for j in range(len(lst1[0])):
    row.append(lst1[i][j] + lst2[i][j])
  result.append(row)
print(type(result))
print(result)


arr1 = np.array(lst1)
arr2 = np.array(lst2)
result = arr1 + arr2
print(type(result))
print(result)

# the code below doesn't work
#result.append([20, 22, 26])
```

    <class 'list'>
    [[2, 4, 6], [8, 10, 12], [14, 16, 18]]
    <class 'numpy.ndarray'>
    [[ 2  4  6]
     [ 8 10 12]
     [14 16 18]]


# Extra Time in Lecture - Hints on Final Project Problems
