# Linked Lists & Doubly Linked Lists

Using Classes to store data. Each object can only store individual data.





```python
class node:
  def __init__(self, value):
    self.value = value
    self.next = None


head = node(1)
curr_node = head
for i in range(2,6):
  curr_node.next = node(i)
  curr_node = curr_node.next

curr_node = head
print(curr_node.value)

while curr_node.next != None:
  curr_node = curr_node.next
  print(curr_node.value)



print('\nThe output blelow might not be as you expect')
curr_node = head
while curr_node.next != None:
  print(curr_node.value)
  curr_node = curr_node.next

print('\nThis would work instead')
curr_node = head
while curr_node != None:
  print(curr_node.value)
  curr_node = curr_node.next

```

    1
    2
    3
    4
    5
    
    The output blelow might not be as you expect
    1
    2
    3
    4
    
    This would work instead
    1
    2
    3
    4
    5


# Exceptions
If there is a portion of code that may error or
may be affected by variables outside of your control
it can be hard for your program to continue.

If your program runs into an error, the user will find
the program unusable.

Some example of things can't control:
- user input
- internet connection or data retrieval from a database


```
try:
  # try out some code
  # if it works, that's great. move on ( Do not execute the except block)
except:
  # this block runs only if the code in the try block fails
  # This code is skipped if the try code executed properly
```




```python
# Build a division program

[num, den] = [int(x) for x in input().split()]
while num != 0:
  q = num/den
  print(q)
  [num, den] = [int(x) for x in input().split()]



# Try entering 1 0
```

    1 0



    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-4-799ee16a83c5> in <cell line: 4>()
          3 [num, den] = [int(x) for x in input().split()]
          4 while num != 0:
    ----> 5   q = num/den
          6   print(q)
          7   [num, den] = [int(x) for x in input().split()]


    ZeroDivisionError: division by zero



```python
# Build a division program
[num, den] = [int(x) for x in input().split()]
print('Input was wrong. Try again')
while num != 0:
  try:
    q = num/den
  except:
    q = 'There was an error'
  print(q)
  [num, den] = [int(x) for x in input().split()]


```

# A quick debugging technique
Use an one line if statement with a variable to turn on/off
debug statements


```python
isDebugOn = True
print(f'debug = {isDebugOn}' if isDebugOn else 'Debug is OFF')
[num, den] = [int(x) for x in input().split()]
if isDebugOn:
  print(f'debug: num = {num}, den = {den}')
while num != 0:
  q = num/den
  if isDebugOn:
    print(f'debug: q = {q}')
  print(q)
  [num, den] = [int(x) for x in input().split()]
  if isDebugOn:
    print(f'debug: num = {num}, den = {den}')


```

    debug = True
    3 2
    debug: num = 3, den = 2
    debug: q = 1.5
    1.5
    1 2
    debug: num = 1, den = 2
    debug: q = 0.5
    0.5
    0 1
    debug: num = 0, den = 1


# Big O Notation
A simple way to describe time complexity of your algorithms.
There are some rules. We will discuss a few basics


```python
# given n we want to loop through all n values
n = int(input())
for i in range(n):
  # do something
  print(i)
# We say this algorthim runs in O(n)

n = int(input())
for i in range(n):
  for j in range(n):
    # do something
    print(i, j)
# O(n^2)

n = int(input())
for i in range(n):
  for j in range(n):
    for k in range(n)
      # do something
      print(i, j)
# O(n^3)


n = int(input())
for x in range(7):
  for i in range(n):
    # do something
    print(i)
# O(7n) => O(n)
```

# Searching and Sorting Algorithms
- selction sort
- insertion sort
- quick sort
- merge sort

 [Youtube Visualize Sorting Algorithms](https://www.youtube.com/watch?v=kPRA0W1kECg). Why do we need many different sorting algorithms?


```python
# sorting algorthims aim to sort values

# quick sort
# [1 6 5 4 7 3 2]

# pick a pivot = 4
# move the pivot to the end
#   [1 6 5 2 7 3 4]
# Find a number bigger than the pivot from the left
# 6
# Find a number smaller than the pivot from the right
# 3
# Swap the two numbers found
# [1 3 5 2 7 6 4]
```
