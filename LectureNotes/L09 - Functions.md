'''
User defined functions

Functions actually work very similar to functions you learned in your math.

in your math class you've seen
f(x) = x^2 - we call this the function definition


f(2) = ? -> 4 # f(2) is calling (using) the function with 2 as the parameter

f(3) = ? -> 9

f(5) = ? -> 25

How can we build this in python?
'''


```python
# the def keyword defines a function
# f is the name of the function
# x is called a parameter - the function below has only 1 parameter
def f(x):
  # everything tabbed under def belongs to the function
  result = x*x
  return result
  # the return keyword immediately ends the function. It is optional
  # if there is no return, the function ends when the code block ends
if __name__=='__main__':
  z = f(2) # function call
  y = f(3) # function call
  print(z, y, f(5))

```

'''
We can put any amount of valid python code into a function.

we can also define a function with more than 1 parameters

return is optional.
If return is executed in a function. the function ends and returns to the place the function was called. If no return is executed, the function ends when the code block is finished executing and returns nothing (None) to where it was called.

Many examples are shown below
'''


```python
def ReturnNone():
  print('this function is running')

returnValue = ReturnNone()
print(returnValue, type(returnValue))
```


```python
# build the same function above using differnt names and additional code
def pow2(a):
  result = a*a
  return result
z = pow2(2) # function call
print(z, pow2(5))
```

    4 25



```python
# build a function similar to the math power function
# something that calculates and returns x^n
# protype def pown(x: int, n: int) -> int
# genericall def pown(x, n) works but it's not specific
# def pown(x: int, n: int) -> int:
def pown(x, n):
  result = x**n
  return result
z= pown(2,10)
print(z, pown(6,2))
print(pown(4, 3))
```

    1024 36
    64



```python
# this is a function that prints a list
# Given: nothing , print a list
# Returns None
def f1():
  print([1,2,3])

# this is a function that prints 'Hello' and returns a list
# Given nothing , print 'Hello
# Return a list
def f2():
  print('Hello')
  return [1,2,3]


```


```python
# build a function that calculate the area of a rectangle and return that area.
# Name the function Rect_Area(). It should have 2 parameters that are integers.
# prototype : def Rect_Area(width: int, height: int) -> int
# genericly - def Rect_Area(width, height)
def Rect_Area(width, height):
  area = width * height
  return area
  # alternatively
  # return width * height
w = int(input())
h = int(input())
while w != 0 and h != 0:
  print(Rect_Area(w, h))
  w = int(input())
  h = int(input())
# variables are localized. area in the function is not the same as area in the
# main program
```

    1
    5
    5
    2
    3
    6
    3
    4
    12
    0
    1



```python
# consider the area of a circle and circumfrence of a cirle functions
# variables in each function belong to their respective functions
# variables are local. This means variables are only available in their respective
# function
def Circle_Area(radius):
  result = 3.14 * radius * radius
  return result
def Circle_Circ(radius):
  result = 2*3.14*radius
  return result

#instead of putting my main function tabbed to the left
# we can use if __name__ == '__main__':
if __name__ == '__main__':
  result1 = Circle_Area(1)
  result2 = Circle_Circ(99)
  radius = 5
  print(result1, result2, radius)
  #print(result)

```

    3.14 621.72 5



```python
# Another example
def mypow(base, exp):
    result = 1
    while exp > 0:
        result *= base # result = result*base
        exp -= 1
    return result
if __name__ == "__main__":
    # test mypow
    print(__name__)
    print(mypow(2,2), mypow(2,3), mypow(2,10))
```
