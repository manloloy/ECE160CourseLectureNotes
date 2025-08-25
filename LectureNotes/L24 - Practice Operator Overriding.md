Classes: Trace the program below to practice your understanding

Pay attention to the ```__add__()``` and ```__sub()__``` methods.





```python
class Circle:
  def __init__(self, radius, pos): # radius is float, pos is a tuple with floats
  # pos is the (x, y) position of the circle
    self.radius = radius
    self.pos = pos
  def Area(self):
    return 3.14*(self.radius**2)
  def __sub__(self, other):
    if isinstance(other, Circle):
      return ((self.pos[0] - other.pos[0])**2+(self.pos[1] - other.pos[1])**2)**(1/2)
  def __add__(self, other):
    if isinstance(other, Circle):
      return self.Area() + other.Area()
  def Intersecting(self, other):
    if isinstance(other, Circle):
      if (self - other) < (self.radius + other.radius):
        return True
      else:
        return False
    else:
      return False

if __name__ == '__main__':
  r1 = float(input())
  [x1, y1] = [float(x) for x in input().split(',')]
  r2 = float(input())
  [x2, y2] = [float(x) for x in input().split(',')]
  c1 = Circle(r1, (x1, y1))
  c2 = Circle(r2, (x2, y2))
  #print(type(c1), type(c23))
  print(c1.Area())
  print(c2.Area())
  print(c1 - c2)
  print(c1 + c2)
  print(c1.Intersecting(c2))

# example input
'''
5
3,4
3
0,0
'''
```

# Modification
What if adding 2 circles creates a new circle. The new circle has the same x position as circle 1 and the same y position as circle 2. The radius is the sum of both radius.


If an integer is added to the circle, the result should be an integer that represents the radius plus that integer value.


If a float is added to the circle, the result will be a float that represents the area plus the float value.



```python
class Circle:
  def __init__(self, radius, pos): # radius is float, pos is a tuple with floats
  # pos is the (x, y) position of the circle
    self.radius = radius
    self.pos = pos
  def Area(self):
    return 3.14*(self.radius**2)
  def __sub__(self, other):
    if isinstance(other, Circle):
      return ((self.pos[0] - other.pos[0])**2+(self.pos[1] - other.pos[1])**2)**(1/2)
  ## Modifying for the new problem
  def __add__(self, other):
    if isinstance(other, Circle):
      x = self.pos[0]
      y = other.pos[1]
      r = self.radius + other.radius
      newC = Circle(r, (x, y))
      return newC
      # alternatively
      # return Circle(self.radius+other.radius,(self.pos[0], other.pos[1]))
    if isinstance(other, int):
      return self.radius + other
    if isinstance(other, float):
      return self.Area() + other

  def Intersecting(self, other):
    if isinstance(other, Circle):
      if (self - other) < (self.radius + other.radius):
        return True
      else:
        return False
    else:
      return False

if __name__ == '__main__':
  r1 = float(input())
  [x1, y1] = [float(x) for x in input().split(',')]
  r2 = float(input())
  [x2, y2] = [float(x) for x in input().split(',')]
  c1 = Circle(r1, (x1, y1))
  c2 = Circle(r2, (x2, y2))
  #print(type(c1), type(c23))
  print(c1.Area())
  print(c2.Area())
  print(c1 - c2)
  print(c1 + c2)
  # modification
  c3 = c1 + c2
  print(c3.radius, c3.pos)
  print(c3 + 2)
  print(c3.Area(),c3 + 100.0)
  print(c1.Intersecting(c2))

# example input
```

    5
    0,0
    5
    10,0
    78.5
    78.5
    10.0
    <__main__.Circle object at 0x7d08b870b400>
    10.0 (0.0, 0.0)
    12.0
    314.0 414.0
    False



```python

```
