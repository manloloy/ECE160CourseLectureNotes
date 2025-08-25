# Overriding Operators in Classes
Consider we have a class definition for a Box
```
class Box:
  # code for the box class
  ...
```

Review the following code.
What does the code mean or do?
```
b1 = Box()
b2 = Box()
x = b1 - b2 # what does this do?
print(x)
```
What is happening above? what does it mean?

With numbers like integers,

5-3 is a very natural statement. We understand this.

But what is b1 - b2, where b1 and b2 are both of type \<class Box\>.

In programming we can completely define what happens when two user defined class objects are subtracted. This is called overloading the subtraction operator. In fact, we can overload many different operators such as +, /, *, %, etc. In general, it's called overlaoding an operator.

There are some that cannot be overloaded. These operators that can be overloaded should be discussed in your Homework.

Consider the Rectangle class created earlier. It's shown below. But we can overload the subtraction operator be defining the __sub__ method.


```python
class Rectangle:
  def __init__(self, width, length):
    print('The Rectangle.__init__() function was called')
    print(f'called with width={width} and length={length}')
    self.width = width
    self.length = length
  def __str__(self):
    return f'This is a Rectanlge that has width {self.width} and length {self.length}'
  def Area(self):
    return self.width * self.length
  def Perimeter(self):
    return 2*self.width + 2*self.length
  def MultiplyAreaByN(self, n):
    return n*self.Area()
  # overriding the subtraction operator
  def __sub__(self, other):
    if not isinstance(other, Rectangle):
      return f'Error: the first obj is a Rectangle\nErrorContinued: the second obj is {type(other)}'
    # subtraction between two rectangles can be defined any way we want or need
    # in this case let's define it as the magnitude of the difference of areas
    a = self.Area() - other.Area()
    b = other.Area() - self.Area()
    return a if a >= 0 else b

print('the following code is testing the __str__() method')
rx = Rectangle(3,5)
ry = Rectangle(7,1)
print('rx:',rx)
print(f'ry: {ry}')
# let's test subtraction of Rectangles
print('rx-ry:',rx - ry)
print('ry-rx:',ry - rx)
print('rx-5:',rx - 5)
print("ry-'hello':",ry - 'hello')
```

    the following code is testing the __str__() method
    The Rectangle.__init__() function was called
    called with width=3 and length=5
    The Rectangle.__init__() function was called
    called with width=7 and length=1
    rx: This is a Rectanlge that has width 3 and length 5
    ry: This is a Rectanlge that has width 7 and length 1
    rx-ry: 8
    ry-rx: 8
    rx-5: Error: the first obj is a Rectangle
    ErrorContinued: the second obj is <class 'int'>
    ry-'hello': Error: the first obj is a Rectangle
    ErrorContinued: the second obj is <class 'str'>



```python
class Rectangle:
  def __init__(self, width, length):
    print('The Rectangle.__init__() function was called')
    print(f'called with width={width} and length={length}')
    self.width = width
    self.length = length
  def __str__(self):
    return f'This is a Rectanlge that has width {self.width} and length {self.length}'
  def Area(self):
    return self.width * self.length
  def Perimeter(self):
    return 2*self.width + 2*self.length
  def MultiplyAreaByN(self, n):
    return n*self.Area()
  # overriding the subtraction operator
  def __sub__(self, other):
    if isinstance(other, Rectangle):
      # subtraction between two rectangles can be defined any way we want or need
      # in this case let's define it as the magnitude of the difference of areas
      a = self.Area() - other.Area()
      b = other.Area() - self.Area()
      return a if a >= 0 else b
    elif isinstance(other, int):
      return self.Area()*other
    elif isinstance(other, float):
      return self.Area() - other
    else:
      return 'Subtracton only works with Rectangles, Integers, & Floats'

print('the following code is testing the __str__() method')
rx = Rectangle(3,5)
ry = Rectangle(7,1)
print('rx:',rx)
print(f'ry: {ry}')
# let's test subtraction of Rectangles
print('rx-ry:',rx - ry)
print('ry-rx:',ry - rx)
print('rx-5:',rx - 5)
print('rx-5:',rx - 3.14)
print("ry-'hello':",ry - 'hello')
```

    the following code is testing the __str__() method
    The Rectangle.__init__() function was called
    called with width=3 and length=5
    The Rectangle.__init__() function was called
    called with width=7 and length=1
    rx: This is a Rectanlge that has width 3 and length 5
    ry: This is a Rectanlge that has width 7 and length 1
    rx-ry: 8
    ry-rx: 8
    rx-5: 75
    rx-5: 11.86
    ry-'hello': Subtracton only works with Rectangles, Integers, & Floats

