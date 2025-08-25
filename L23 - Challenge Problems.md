# Challenge Problem 1

Build a function that takes in a matrix ( as a nested list). The function should also take the row and column position of 2 elements as tuples. The function should swap the two values at the positions given.

```
prototype:
def Swap2(matrix, pos1, pos2):
  pass
def Swap2(matrix: list, pos1: integer tuple, pos2: integer tuple) -> list
  pass

```
```
1 2 3
4 5 6
7 8 9
```
represented as a nested list
matrix=[[1, 2, 3],[4, 5, 6],[7, 8, 9]]

Swap2(matrix, (0,0), (2,2))
- (0, 0) - row 0, column 0.
- matrix[0][0] has the value 1

The return value should be a new matrix with the swapped values
```
9 2 3
4 5 6
7 8 1
```
return value would be:
[[9, 2, 3],[4, 5, 6],[7, 8, 1]]




```python
def Swap2(mtx, pos1, pos2):
  tmp = mtx[pos1[0]][pos1[1]]
  mtx[pos1[0]][pos1[1]] = mtx[pos2[0]][pos2[1]]
  mtx[pos2[0]][pos2[1]] = tmp
  return mtx
matrix=[[1, 2, 3],[4, 5, 6],[7, 8, 9]]
r = Swap2(matrix, (0,0), (2,2))
print(matrix)


def f(x):
  x += 1
  return x**2

y = 2
print(f(y), y)


```

    [[9, 2, 3], [4, 5, 6], [7, 8, 1]]
    9 2


# Challenge 2
Build a class called Circle which takes the following parameters:
 - (x, y) as tuple representing the x and y position of the center in a 2D plane
 - r - the radius of the circle

 The following Methods:
 - ```__init__```(self, pos, r). pos is a tuple (x,y) and r is the radius.
 - Area() - returns the area of the circle
 - isIntersecting() - given another circle object return True if the 2 circles are intersecting. Returns False
 otherwise
 - ```__str__```(self). This method should return a string that shows the position of the circle's center and the circle's radius.

 Finally, test all methods using a main program. Create at least 3 circles and test if all methods are returning the correct information.


```python
class Circle:
  def __init__(self, pos, r):
    self.pos = pos
    self.r = r
  def Area(self):
    return 3.14*(self.r**2)
  def __str__(self):
    return f'Circle Center: x={self.pos[0]},y={self.pos[1]}, radius={self.r}'
  def isIntersecting(self, c):
    if isinstance(c, Circle):
      dist = ((self.pos[0] - c.pos[0])**2 + (self.pos[1]-c.pos[1])**2)**(1/2)
      if dist <= (self.r + c.r):
        return True
      else:
        return False
    else:
      print('Error')
      return

c1 = Circle((0,0), 5)
c2 = Circle((10.000001,0), 5)

print(c1)
print(c2)
print(c1.isIntersecting(c2))
```

    Circle Center: x=0,y=0, radius=5
    Circle Center: x=10.000001,y=0, radius=5
    False

