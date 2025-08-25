```python
def Rectangle_Area(width: float, length: float) -> float:
#def Rectangle_Area(width, length):
    #Given: the length and width of a rectangle (both float)
    #Return: return the area of the rectangle
    return width * length
if __name__ == '__main__':
  # get the length
  length = float(input())

  # while the length is not zero
  while length != 0:
    width = float(input())
    if width == 0:
      break
    # display the calculated area
    print('the area is:', Rectangle_Area(length, width))
    length = float(input())
  print('program ended')



```

    5
    30
    the area is: 150.0
    0
    program ended


# Classes
Recall functions.

Functions group a bunch of code together. Similarly, classes group a bunch of variables and functions together.
* when a function belongs to a class, we call it a method

## Method review & description
The list class has a method named append. The append function is a function that belongs to the list class
* so we call append() the append() method and not the append function()


```python
lst = [1, 2, 3]
print(type(lst), type(3.14), type(1), type(''), type({}))
lst.append(4) # using the append method
# the output of this program should be
# <class 'list'>
# recall that we have seen <class 'float'>, <class 'int'>,
# <class 'str'>, <class 'dict'>
```

    <class 'list'> <class 'float'> <class 'int'> <class 'str'> <class 'dict'>


# Classes
we've seen types that look like <class 'str'>. What is "class"? How we can build our own objects (not just int, float, list, etc..).

Let's build our first class to explore classes.

Our first class will be a Rectangle class.


```python
# we use the 'class' keyword to create a class
class Rectangle:
  # what goes in here are your method definitions
  pass
r1 = Rectangle()
type(r1)
```




    __main__.Rectangle




```python
# we use the 'class' keyword to create a class
class Rectangle:
  # the __init__ method is one of the most commonly used methods
  # self is a space to store internal data per object created
  def __init__(self, width, length):
    # We can put any amount of code here
    # of then this is used for initialization or instantiation
    print('The Rectangle.__init__() function was called')
    print(f'called with width={width} and length={length}')
    self.width = width
    self.length = length
    print('The init method is done!')
r1 = Rectangle(3,5) # this line runs the __init__() method
# r1 is a an object of class rectangle and has it's own self variable
r2 = Rectangle(300,500) # this also runs an __init() method
# r2 is an object of class rectangle and has it's own self variable
print(r1)
print(type(r1))
print(r1.width, r2.width)

```

    The Rectangle.__init__() function was called
    called with width=3 and length=5
    The init method is done!
    The Rectangle.__init__() function was called
    called with width=300 and length=500
    The init method is done!
    <__main__.Rectangle object at 0x7a20fb61db50>
    <class '__main__.Rectangle'>
    3 300


# Modifying our orignal Rectangle class with more methods
Let's add 3 new methods to our class called Area(), Perimeter(), and MultiplyAreaByN(). These functions should return a value that makes sense for their names.


```python
class Rectangle:
  def __init__(self, width, length):
    print('The Rectangle.__init__() function was called')
    print(f'called with width={width} and length={length}')
    self.width = width
    self.length = length
  # the Area() method
  def Area(self):
    # this function should return the area of the Rectangle
    return self.width * self.length
  # the Perimeter() method
  def Perimeter(self):
    return 2*self.width + 2*self.length
  # MultiplyAareaByN method
  def MultiplyAreaByN(self, n):
    return n*self.Area()
    '''
    # alternatively
    result = 2 * self.width * self.length
    return result
    '''
print('the following code tests the Area() and MultiplyAreaByN() methods')
r1 = Rectangle(3, 5)
r2 = Rectangle(300, 500)
print(r1.Area(), r2.Area())
print(r1.MultiplyAreaByN(6))
print(r1.Area())
r1.width = 5
print(r1.Area())
```

    the following code tests the Area() and MultiplyAreaByN() methods
    The Rectangle.__init__() function was called
    called with width=3 and length=5
    The Rectangle.__init__() function was called
    called with width=300 and length=500
    15 150000
    90
    15
    25


Let's try to fix printing out the class using the print() function.

**NOTE:** print() can be used on list, int, float, dictionary, tuples, etc...

Why can't we use print() on our own class like Rectangles(). It works but it only shows us the memory address. Printing a list shows the actual list and printing an int shows the integer.

To accomplish this, there is an internal method we can use named __str__(self).

The __str__() method must return a string because the print() function expxects a string.


```python
class Rectangle:
  def __init__(self, width, length):
    self.width = width
    self.length = length
  # adding the __str__() method
  def __str__(self):
    #return 'Hello From Rectangle'
    return f'This is a Rectanlge that has width {self.width} and length {self.length}'
  def Area(self):
    return self.width * self.length
  def Perimeter(self):
    return 2*self.width + 2*self.length
  def MultiplyAreaByN(self, n):
    return n*self.Area()

print('the following code is testing the __str__() method')
rx = Rectangle(3,5)
ry = Rectangle(7,1)
print('rx:',rx)
print(f'ry: {ry}')
```

    the following code is testing the __str__() method
    rx: This is a Rectanlge that has width 3 and length 5
    ry: This is a Rectanlge that has width 7 and length 1



```python
# list of rectangles

rx = Rectangle(3,5)
ry = Rectangle(7,1)
rz = Rectangle(10,3)

rectangles = [rx, ry , rz]
print(len(rectangles))
print(type(rectangles))
print(rectangles[0])
```

# Build a game
The gameboard will 10 by 10 squares
the user starts at a random postion
the user can use w,a,s,d to move. They cannot move outside game board.
a random postion in the board is selected to be the goal
the user can't see the goal
When the user finds the goal they win.




```python
print(type(11))
x = 3.14
print(type(x))
print(type([1,2,3]))

y = [1,2,3]
y.append(5)
```

    <class 'int'>
    <class 'float'>
    <class 'list'>

