# Binary (Base 2), Octal (Base 8), Hexadecimal (Base 16)

## First Discuss Decimal (Base 10) - 10 symbols (0-9)
```
000
001
002
...
009
010
011
...
019
020
...
099
100
```

## Base 2 - Binary (2 symbols 0 & 1)
```
000
001
010
011
100
101
110
111
```

# Boolean equations (True or False)
## Boolean Operators
unlike multiplication *, division /, addition +, subtractions -, assignment =
```
> Greater Than
< Less Than
>= Greater Than or Equal To
<= Less Than or Equal to
== is Equal to
!= not Equal to
```
All of these functions result in True or False


```python
x = 5 > 2
y = 2 > 5
print(x, y, type(x), type(y))

a =  100
b =  100
c = 200
d = 'hello'
e = 'hello'
f = 'bye'
print(a == b, a == c, a!=c, d==e, e==f)

b1 = True
b2 = False

```

    True False <class 'bool'> <class 'bool'>
    True False True True False


# If/Else Branching
Specificly if/else operates on booleans
if the condition evaluates to True, the if block runs

otherwsise the else block runs if it exists

If/Else layout
```
if <condition>:
  # anything tabbed in directly
  # under the if statement
  # is considered part of the
  # if block
  # end of if block
else:
  # anything tabbed in directly
  # under the else statement
  # is considered part of the
  # else block
  # end of else block
# the program contiues here
```






```python
# Build a program that allows a user to input a number (integer)
# if the integer is over 9000, print 2 statements to the screen praising their number
# otherwise print 2 statements that encourage them to increase their number
# at the end of the program display program ended

num = int(input())

if num > 9000:
  print("That's great!")
  print("It's over 9000!")
else:
  print("your number isn't very magical")
  print("It needs more magic")
print("program ended")


```

    5
    your number isn't very magical
    It needs more magic
    program ended


# If can exist by itself
Else cannot exist without an if statement


```python
num = int(input())
if num > 9000: #if True
  print("That's great!")
  print("It's over 9000!")
else:
  pass
```

    5



```python
num = int(input())
if num > 9000: #if True
  print("That's great!")
  print("It's over 9000!")
```

# More IF/Else Exploration


```python
print(True, type(True))
```


```python
if True:
    print('1 if block is running')
    print('1 ...')
    print('1 if block still running')
print('1 if ends here!')

if False:
    print('2 if block is running')
    print('2 ...')
    print('2 if block still running')
print('2 if ends here!')



```

    1 if block is running
    1 ...
    1 if block still running
    1 if ends here!
    2 if ends here!





```python
if True:
    print('if block is running')
    print('...')
    print('if block still running')
else:
    print('else block is running')
    print('...')
    print('else block still running')
print('if ends here!')
```


```python
if False:
    print('if block is running')
    print('...')
    print('if block still running')
else:
    print('else block is running')
    print('...')
    print('else block still running')
print('if ends here!')
```

Try Tracing the following example. Try various inputs and try to predcit the output.


```python
num = int(input())
if num <= 10:
  if num < 0:
    print('negative')
  else:
    if num <= 5:
      print('0-5')
  print('< 10')
else:
  if num < 100:
    print('10-100')
  else:
    if num < 1000:
      print('100-1000')
    else:
      print('big')



```

    -1
    negative
    < 10


# CP 4 - review the last cp solution



```python
# get 5 floats from the user
num1 = float(input())
num2 = float(input())
num3 = float(input())
num4 = float(input())
num5 = float(input())
# calculate the minimum, maximum, and average
numbers = [num1, num2, num3, num4, num5]
mi = min(numbers)
ma = max(numbers)
avg = sum(numbers)/len(numbers)
# display the results
print(f'Lowest: {mi:.2f}')
print(f'Average: {avg:.2f}')
print(f'Highest: {ma:.2f}')


```


```python
# attempt a solution using branching if/else
# get 1 float at a time
# track the min and max
# calculate the average
# display the results

# get float 1 from the user
num = float(input())
mi = num
ma = num
sum = num
num = float(input())
if num < mi:
  mi = num
if num > ma:
  ma = num
sum = sum + num # sum += num
num = float(input())
if num < mi:
  mi = num
if num > ma:
  ma = num
sum += num # sum = sum + num
num = float(input())
if num < mi:
  mi = num
if num > ma:
  ma = num
sum += num # sum = sum + num
num = float(input())
if num < mi:
  mi = num
if num > ma:
  ma = num
sum += num # sum = sum + num
avg = sum/5
# display the results
print(f'Lowest: {mi:.2f}')
print(f'Average: {avg:.2f}')
print(f'Highest: {ma:.2f}')
```


```python
numbers = []
numbers.append(float(input()))
numbers.append(float(input()))

```
