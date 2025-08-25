# While Loops Again
here's an an example of a while loop in an if statement.
if the user enteres a postive number, n(0 exclusive), then the program should
output '0123...n'. If the user enters a negative number, -n, the output should be n...3210
utilize while loops just for the sake of example


```python
num = int(input())
if num > 0:
  i = 0
  while i < num + 1:
    #print(i)
    print(i, end='')
    i += 1
elif num < 0:
  i = num*-1
  while i > -1:
    print(i, end='')
    i -= 1
else:
  print('User enetered "0"')
```

# For loops
For loops are similar to while loop in most languages. In python, for loops operate on lists. For loops use a variable that is set to the first item in the list. The loop body is executed and the variable is then set to the second item in the list. This continues until the for loop body runs for all items in the list.



```python
lst = [1, 2, 3]
for i in lst:
  print('we are in the for loop body')
  print(i)
  print('i was printed to the screen')
```


```python
colors = ['red', 'green', 'blue']
for color in colors:
  print(color[0])
```

# The range() function
The range function can be used in 3 ways.
- 1 parameter
- 2 parameters
- 3 parameters
The reason we use the range function is because it becomes useful in for loops.

## 1 parameter where n is an integer
range(n) - this produces a list from 0 to n-1 in steps of 1. [0, 1, 2, ..., n-1]

## 2 parameters where start and stop are integers
range(start, stop) - produces a list from start to stop -1 in steps of 1. [start, start+1, start+2, ..., end -1]

## 3 parameters where start, stop, and step are integers
range(start, stop, step) - procuces a list from start to stop -1 in steps of step. [start, start+step, start+2*step, (x, where x is start +n*step < end -1)]



```python
# 1 parameter
lst = list(range(3))
print(lst)
print(list(range(5)))
```


```python
# 2 parameters
lst = list(range(5, 10))
print(lst)
print(list(range(3, 13)))
```


```python
# 3 parameters
lst = list(range(2, 12, 2))
print(lst)
print(list(range(-1, 12, 2)))
print(list(range(0, 11, 3)))
print(list(range(10, -1, -1)))
```

# For loops using range


```python
for i in range(3):
  print(i, end=' ')
  print(i+1, end=' ')
  print(i+2)
```

# Just a review of while loop binary counting


```python
i = 0
while i < 2:
  j = 0
  while j < 2:
    print(i,j)
    j += 1
  i += 1
```

    0 0
    0 1
    1 0
    1 1



```python
i = 0
while i < 2:
  j = 0
  while j < 2:
    k = 0
    while k < 2:
      print(i,j, k)
      k += 1
    j += 1
  i += 1
```

    0 0 0
    0 0 1
    0 1 0
    0 1 1
    1 0 0
    1 0 1
    1 1 0
    1 1 1


# using for loops instead


```python
for i in range(2):
  print(i)
```

    0
    1



```python
for i in range(2):
  for j in range(2):
    print(i,j)
```

    0 0
    0 1
    1 0
    1 1



```python
for i in range(2):
  for j in range(2):
    for k in range(2):
      print(i,j,k)
```

    0 0 0
    0 0 1
    0 1 0
    0 1 1
    1 0 0
    1 0 1
    1 1 0
    1 1 1



```python
for i in range(8):
  print(f'{i:b}')
```

    0
    1
    10
    11
    100
    101
    110
    111


# Build a program
where you are already given a list of numbers. Let's square all the numbers and create a new list with those numbers.
### This can be accomplished using list comprehension but this learned later in the text book. We'll just see how we can accomplish this with the tools we already have.



```python
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
# produce a resulting list wih [1, 4, 9, 16, 25, 36 ...]

result = []
for num in lst:
  result.append(num**2)
print(result)
```

    [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]


# Some variations of problems


```python
# Same program as above but we only want to square index 4
# easily do lst[4] = lst[4]**2 but let's use a loop to practice
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in range(len(lst)):
  if i == 4:
    lst[i] = lst[i]**2
print(lst)
```

    [1, 2, 3, 4, 25, 6, 7, 8, 9, 10]



```python
# Same program as above but only square even numbers
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in range(len(lst)):
  if lst[i] %2 == 0:
    lst[i] = lst[i]**2
print(lst)
```

    [1, 4, 3, 16, 5, 36, 7, 64, 9, 100]



```python
# Same program as above but only square even indices. 0 is even
lst = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in range(len(lst)):
  if i % 2 == 0:
    lst[i] = lst[i]**2
print(lst)
```

    [1, 2, 9, 4, 25, 6, 49, 8, 81, 10]

