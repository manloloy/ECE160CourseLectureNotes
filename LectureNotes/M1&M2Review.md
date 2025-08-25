# Miderm 1 & Midterm 2 Review
To be filled in over the next few days

# 1.
Write a program that will convert a user's input from Pounds to Kilograms. The user input will be integer or float. If the user enters a negative number the program should output "Error". All output values should contain 2 decimal places.

- 1 Kilogram = 2.20462 Pounds

Example Input:
```
1
```
Example Output:
```
1.00 Pounds = 0.45 Kilograms

```

Another Example
Example Input:
```
-1.5
```
Example Output:
```
Error

```


```python
if __name__ == '__main__':
  pass
```

#2.
Write a program that will allow a user to keep on inputting integers until the user enters the special integer -789. When the user enters the special integer the program should display the count of how many numbers the user entered (not including the special integer).
In addition to the total count, the program should also display the count and average of all numbers less than 100. The average should be displayed with 2 decimal places.


Example Input:
```
25
100
10
125
75
300
5
525
1
-789
```
Example Output:
```
Total Count: 9
Less Than 100 Count: 5
Less Than 100 Average: 23.20

```


```python
if __name__ == '__main__':
  pass
```

# 3.
Write a program that allows a user to input a radius in feet. The program should output the volume and the surface area of the hemisphere with the corresponding radius. After displaying the results, the program should ask the user to input another radius in feet. If the user inputs a negative number, the program should print "Error" and ask for a new radius. If the user inputs 0, the program should exit and display "Good Bye". Display all floats with 2 decimal places. Do not use the Math library. Use a variable to set $$\pi = 3.14$$

Useful Information:
$$
Volume_{hemisphere} = \frac{2}{3}\,\pi r^3
$$

$$
SurfaceArea_{hemisphere} = 3 \pi r^2
$$


Example Input:
```
4.6
0
```
Example Output:
```
Radius: 4.60, Volume: 203.76, SA: 199.33
Good Bye

```


```python
if __name__ == '__main__':
  pass
```

# 4.
Design a FUNCTION named Function5 which takes one parameter named numbers. The numbers parameter should be a list containing integers. The function should return a list of all Even Integers greater than 10. If there are no integers to return, the function should return an empty list.
```
# A function named Function5 that takes one parameter (list) and returns a list
def Function5(numbers: lst) -> lst:
```

Example Function Call:
```
Function5( [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20] )
```
Function Returns:
```
[12, 14, 16, 18, 20]
```



```python
def Function5(numbers):
  pass
if __name__ == '__main__':
  pass
```

# 5.
Write a program to calculate the average of all data entered. The user will enter floats separated by semicolons or a newline. When the user is done entering data, the user will enter the string "finish". The "finish" string will always be on a newline by itself and will never occur after valid input.

The input can have any number of rows and any amount of data on each row. The output should be rounded to 2 decimal places. If no numbers are entered the average should be 0.00

Example Input:
```
1;2;3;4;5
6;7
8;9;10
finish
```
Example Output
```
5.50
```


```python
if __name__ == '__main__':
  pass
```

# 6.
Fill in the function MinAverage(matrix). The parameter matrix is a nested list representing a matrix. An example matrix parameter sent to this function could be [ [1, 2, 3] , [4, 5, 6] , [7, 8, 9] ]. This represents the matrix
```
1.0 2.0 3.0
4.0 5.0 6.0
7.0 8.0 9.0
```

The MinAverage function should calculate which column in the matrix has the minimum average and return a list. The returned
list should have 2 values. The first value is the column number (starting with 0 just like indexing lists) and
the second value is the minimum average. Round all values to 1 decimal place.

Example 1: MinAverage with matrix = [ [1, 2, 3] , [4, 5, 6] , [7, 8, 9] ]
```
MinAverage([ [1, 2, 3] , [4, 5, 6] , [7, 8, 9] ])
```
Example 1 Return Value:
```
[0, 4]
```

In example 1 above, column 0 has a average of 4, column 1 has a average of 5, and
column 2 has a average of 6. The function MinAverage would return [0, 4] in this case, where 0 is the col
number and 4 is the average of col 0.

Example 2: MinAverage with matrix =[[10, 5.5], [3.1, -2.7], [2.8, 6.4]]
```
MinAverage([[10, 5.5], [3.1, -2.7], [2.8, 6.4]])
```
Example 2:  Return Value
```
[1, 3.1]
```

In Example 2 above, the MinAverage method should return [1, 3.1] where 1 is the column number and 3.1 is
the average of column 1. NOTE: the average of column 0 is 5.3




```python
def MinAverage(matrix):
  pass
if __name__ == '__main__':
  pass
```

# 7.
Write a Class definition for a rectangle shape.

- The name of the class will be named Rectangle.

- To initialize a Rectangle you will need the Rectangle's width,  height, and center position (The center is given as a tuple (x,y)). All values will be float.

- Write a method that returns the area of the rectangle (Rectangle.Area() returns the area of the Rectangle).

- Write a method that returns the perimeter of a rectangle (Rectangle.Perimeter() returns the perimeter of the Rectangle)

- Overload the subtraction operator so that you can subtract two Rectangles from each other. Subtracting 2 rectangles should  result in the distance between the 2 rectangle's centers

- Overload the addition operator so that you can use the '+' operator with rectangles. If two rectangles are used with '+', this should result in the sum of the two rectangle's perimeters. If a rectangle is added with a float value,  this should result in the sum of the area and the value

- Write a method named Intersecting(self, other) . If the other parameter is not of type Rectangle, return None. If the other parameter is of type Rectangle, then return True only if the rectangles are intersecting each other on the 2D xy-plane. Return False otherwise. HINT: You can try doing hand examples by drawing rectangles. Check their center positions and compare their values to both rectangle's widths and height. Widths correspond to x distances and heights correspond to the y distances.




```python
class Rectangle:
    def __init__(self, width, height, pos):
        pass
    def Intersecting(self, other):
        pass

if __name__ == '__main__':
    #you can write your test code here
    pass
```
