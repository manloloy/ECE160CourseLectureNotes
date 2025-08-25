## For Loops
In python, for loops generally run on lists. A for loop repeats the block code under it and at every loop (repeat) changes a variable to a new item from the list
```
lst = [1, 2, 3]
for i in [1, 2, 3]: #This will print through ALL numbers in [1,2,3]
    print(i)
for j in lst: #This will perform the same print, but in the varaible 'lst'
    print(j)
```




```python
lst = [1, 2, 3]
for i in [1, 2, 3]: #This will print through ALL numbers in [1,2,3]
    print(i)
for j in lst: #This will perform the same print, but in the varaible 'lst'
    print(j)
```

In for loops, the range() and list() functions often come in handy.

The command list() simply turns something into a list if possible.
list() is similar to int(), float(), string().

The range() function creates a list depending on the parameters.

There are 3 ways to use the range function. You may use
- one parameter
- two parameters
- three parameters


```python
# 1 parameter: range(n) creates a list from 0 to n-1 in increments of 1

print(list(range(3)))
# Creates a list from 0 to 2 with increments of 1 - [0, 1, 2]

print(list(range(5)))
# Most useful in for loops, especially if we want a loop over 1000 elements 0-999.
# Typing the entire list is inefficient
```


```python
#2 parameters: range(s,e) - creates a list from s to e-1 in increments of 1

print(list(range(2,5)))
# Creates a list from 2 to 4 with increments of 1 - [2,3,4]
print(list(range(-5,5)))
# Creates a list from -5 to 5 with increments of 1 - [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
```


```python
# 3 parameters: range(s,e,i) - creates a list from s to (e - 1) in increments of i

print(list(range(2,10,2)))
# Creates a list from 2 to 10 with increments of 2 - [2, 4, 6, 8, 10]
print(list(range(10,1,-3)))
# Creates a list from 10 to 1 with increments decreasing by 3 - [10, 7, 4, 1]
```

The following are examples with for loops and the range() function


```python
#this loop will print i in numbers 0-2

for i in range(3):
    print(i, end='')
print(3)

#this loop will print i in numbers, starting from 1-8

for i in range(1,9):
    print(i, end='')
print(9)

#this loop will print i in numbers by increments of 2, from 1-8

for i in range(1,9,2):
    print(i, end='')
print(9)
```


```python
# Nested for loops
for i in range(2):
    for j in range(2):
        print(f'{i}{j}')
```


```python
# This code loops for each i, j, and k within the range.
for i in range(2):
    for j in range(2):
        for k in range(2):
            print(f'{i}{j}{k}')
#This will print out the numbers in the form of BINARY code.
#See the professor if still confused!
```


```python
for i in range(8): #This will print from numbers 1-7 in binary form
    print(f'{i}:{i:02b}')
```

##Break
A way to immediately exit the most recent loop.

Consider this while loop.


```python
# Break is not used below. Trace this program to understand it before using break.
i = 0
while i < 4:
    print(i, end='')
    #This will print the i values UNTIL i is NOT less than 4
    i += 1
print(4) #This print will show up at the end
```

    01234



```python
# Break is now used below in a similar program.
i = 0
while i < 4:
    print(i, end='')
    i += 1
    if (i >= 2):
        break # what did this do?
    #This will stop printing i once i is greater than or equal to 2
print(4)
```

    014



```python
# Can you trace this?
i = 0
while i < 4:
    j = 0
    while j < 4:
        print(f'{i}{j}, ', end ='')
        j += 1
        if j >=2:
            break
    i += 1
print('end')
```

    00, 01, 10, 11, 20, 21, 30, 31, end



```python
# Can you trace this?
for i in range(4):
    for j in range(4):
        print(f'{i}{j}, ', end ='')
        if j >=2:
            break
print('end')

# can you make the output the same as the program above?
```

    00, 01, 10, 11, 20, 21, 30, 31, end


##Continue
Immediately check the condition and restart the loop from the top of the body.
Consider a similar while loop used for break above


```python
# Can you trace this before using continue?
i = 0
while i < 10:
    print(i, end='')
    i += 1
print('end')
```

    0123456789end



```python
# continue is used below. Can you see explain what happened?
i = 0
while i < 10:
    if (i % 2) == 1:
        i += 1
        continue # what did this do?
    print(i, end='')
    i += 1
print('end')
```

    02468end



```python
# you can use break and continue in any looping stucture.
for i in range(10):
    if i % 2 == 1:
        continue
    print(i, end='')
print('end')
```

    02468end

