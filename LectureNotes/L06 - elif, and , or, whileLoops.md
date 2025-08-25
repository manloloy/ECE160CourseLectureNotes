# nested if/else
consider we want to build a program where we allow the user to input a color. We can say if they input 'red' or 'not red'

```
color = input()
if color == 'red':
  print('input was "red"')
else:
  print('input NOT "red"')

```


Consider we want to build a program that allows a user to input red, green, or blue. Other colors are not considered. In this case a simple if/else will not work. In this case we can nest if/else


when working with if/else. Only the if block or else block will run.



```python
color = input() # the user should enter a color
if (color == 'red'):
  print('red')
else:
  if color == 'green':
    print('green')
  else:
    if color == 'blue':
      print('blue')
    else:
      print('not red, green, or blue')
```

# elif
The above program as a bunch of else: followed by if. This can be very common in program so python implements a simplification using an elif block. elif behaves like else: if(condition):. The command elif cannot exist without an initial if statement.


```python
color = input() # the user should enter a color
if (color == 'red'):
  print('red')
elif color == 'green':
  print('green')
elif color == 'blue':
  print('blue')
else:
  print('not red, green, or blue')
```


```python
# can tell me the difference between the above program and the program below
color = input() # the user should enter a color
if (color == 'red'):
  print('red')
if color == 'green':
  print('green')
if color == 'blue':
  print('blue')
else:
  print('not red, green, or blue')
```


```python
num = int(input())

if num > 10:
  print('>10')
if num % 2  == 0:
  print('even')
else:
  print('odd')


```


```python
num = int(input())
if num > 10:
  print('>10')
elif num % 2  == 0:
  print('even')
elif num % 2 == 1:
  print('odd')
elif num == 7:
  print('seven')

```

# and / or
You probably use 'and'/'or' in your daily speech and it operates on boolean statements the same way.

Truth table for 'and'
```
x and y = result
False and False = False
False and True = False
True and False = False
True and True = True
```
Truth table for 'or'
```
x or y = result
False or False = False
False or True = True
True or False = True
True or True = True
```


```python
color = input()
if color == 'red' or color =='blue':
  print('red or blue was entered')
else:
  print('a different color was entered')
```


```python
# something is wrong with this program. Can you see why?
color = input()
if color == 'red'and color =='blue':
  print('red and blue was entered')
else:
  print('a different color was entered')
```


```python
num = int(input())
if num > 10 and num % 2 == 0:
  print(num, 'is greater >10 and even')
else:
  print('not > 10 or not even')
```

# Loops - While loop

Loops allow programmers to run the same code blocks until a certain event or a certain number of times.

The important parts of the while loop (we will look at a for loop soon)

1. Condition variable initialization
2. Condition itself
3. The while loop body
4. The condition update






```python
i = 0 # 1. i is my condition variable initialized to 0
while i < 3: # 2. The condition is i < 3. while is the keyword to start a while loop
  # 3. the while loop body is the block tabbed in under the while loop
  print(i, i*2)
  print('hello')
  # inside the while loop body the condition update must take place
  i = i + 1 # 4. The condition update
  # alternativel i += 1
# the program continues here after the while
print('the while loop ended')
print('goodbye')
```


```python
i = 0
while i < 3:
  i += 1 # i = i + 1
  print(i)
print('the while loop ended')
print('goodbye')
```

    1
    2
    3
    the while loop ended
    goodbye


Example: build a program that takes user input (integers) until the user enters 0. All numbers entered should be stored in a list (not including the 0). The program will end after printing the list of numbers to the screen



```python
# initialize list for storing the numbers
numbers = []
# get the first input
num = int(input())
# while the input is not 0
while num != 0:
  # append to a list
  numbers.append(num)
  # get a new input
  num = int(input())
print(numbers)
```

    1
    -10
    -5
    5
    3
    0
    [1, -10, -5, 5, 3]



```python
# initialize list for storing the numbers
numbers = []
# get the first input
num = int(input())
# while the input is not 0
while num != 0:
  # append to a list
  numbers.append(num)
  # get a new input
  num = int(input())
print(numbers)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-6413f8f86839> in <cell line: 0>()
          4 # num = int(input())
          5 # while the input is not 0
    ----> 6 while num != 0:
          7   # append to a list
          8   numbers.append(num)


    NameError: name 'num' is not defined



```python
# initialize list for storing the numbers
numbers = []
num = 10
while num != 0:
  # get input
  num = int(input())
  # append to a list
  numbers.append(num)

print(numbers)
```

    1
    2
    3
    0
    [1, 2, 3, 0]


# If inside of a while


```python
# Build a program where the user enters an integer. If the integer is even,
# print the value to the screen. If odd, do nothing. The user can continue to
# input integers until the user inputs 0
num  = int(input())
while num != 0:
  if num % 2 == 0:
    print(num)
  num = int(input())

```

# nested while


```python
i = 0
j = 0
while i < 2:
  while j < 2:
    print(f'{i}{j}')
    j+=1
  print(f'i,j: {i},{j}')
  i+=1
print(f'i,j: {i},{j}')

```


```python
i = 0
while i < 2:
  j=0
  while j < 2:
    print(f'{i}{j}')
    j+=1
  i+=1
```
