# String slicing
- string.[start:stop]
*italicized text*
A basic technique that allows a programmer to isolate portions of a string.


```python
greeting ='Hello World!'

# we already know how to access by index
print(greeting[0])

# string slicing is very similar with start
# and stop indecies [start:stop]
# start inclusive and stop exclusive

print(greeting[8:11])
[x, y] = [1, 7] # x=1, y=7
a, b = [-1, -7]
print(f'x = {x}, y = {y}, a = {a}, b = {b}, greeting[x:y] = {greeting[x:y]}')


```

    H
    rld
    x = 1, y = 7, a = -1, b = -7, greeting[x:y] = ello W


# More String Formatting


```python
# we can use spacing in f strings to control output spacing
# commonly used for tables
#x = 'Hello'
#y = 'World'
#i = 'Bye'
#j = 'a'
[x, y, i, j] = ['Hello','World','Bye','a']
for k in [x, y, i, j]:
  print(f'{k:5} is the string stored in this variable')
for k in [x, y, i, j]:
  print(f'{k:10} is the string stored in this variable')
for k in [x, y, i, j]:
  print(f'{k:3} is the string stored in this variable')
for k in [x, y, i, j]:
  print(f'{k[0:3]:3} is the string stored in this variable')
```

    Hello is the string stored in this variable
    World is the string stored in this variable
    Bye   is the string stored in this variable
    a     is the string stored in this variable
    Hello      is the string stored in this variable
    World      is the string stored in this variable
    Bye        is the string stored in this variable
    a          is the string stored in this variable
    Hello is the string stored in this variable
    World is the string stored in this variable
    Bye is the string stored in this variable
    a   is the string stored in this variable
    Hel is the string stored in this variable
    Wor is the string stored in this variable
    Bye is the string stored in this variable
    a   is the string stored in this variable


# String Methods
- string.find()
- string.count()
- string.isdigit()
- string.islower()
- string.isupper()
- string.lower()
- string.upper()


```python
# find
greeting = 'Hello World!'
# string.find()
x = greeting.find('o')
print(f'the first o is at index {x}')
print(x, type(x))
y = greeting[x+1:-1]
print(y)
z = y.find('o')
print(z)
print(f'the next o is at index {x+z+1}')

```

    the first o is at index 4
    4 <class 'int'>
     World
    2
    the next o is at index 7



```python
# count
gretting = 'Hello World!'
print(f'o-count: {greeting.count("o")}')
print(f'l-count: {greeting.count("l")}')


```

    o-count: 2
    l-count: 3



```python
a = 'Z'
b = 'z'
c = '1'

print(f'a.isupper(): {a.isupper()}, b.isupper(): {b.isupper()}')
print(f'a.islower(): {a.islower()}, b.islower(): {b.islower()}')
print(f'a.isdigit(): {a.isdigit()}, c.isdigit(): {c.isdigit()}')


print(f'a: {a}, a.lower(): {a.lower()}')
print(f'b: {b}, b.upper(): {b.upper()}')
```

    a.isupper(): True, b.isupper(): False
    a.islower(): False, b.islower(): True
    a.isdigit(): False, c.isdigit(): True
    a: Z, a.lower(): z
    b: z, b.upper(): Z



```python
greeting1 = 'Hello World!'
greeting2 = 'HELLOWORLD'
other = '1234567890'

print(f"greeting1: {greeting1}, greeting1.isupper(): {greeting1.isupper()}")
print(f"greeting2: {greeting2}, greeting2.isupper(): {greeting2.isupper()}")
print(f"other: {other}, other.isdigit(): {other.isdigit()}")
print(f"greeting1: {greeting1}, greeting1.upper(): {greeting1.upper()}")
print(f"greeting1: {greeting1}, greeting1.lower(): {greeting1.lower()}")


```

# String Splitting string.split()

* allows us to split a string by a given character
* the default character is space
* the return type is a list of strings


```python
greeting = 'Hello World!'
split1 = greeting.split()
split2 = greeting.split('o')
print(f'split1: {type(split1)} : {split1}\nsplit2: {type(split2)} : {split2}')

```

    split1: <class 'list'> : ['Hello', 'World!']
    split2: <class 'list'> : ['Hell', ' W', 'rld!']



```python
# more split examples
# example input data
'''
length,width,temperature
2,5,6
1,4,10
5,4,100
'''
header = input()
firstrow = input()
# build a program to calculate average of the first row
fr = firstrow.split(',')
print(fr)

for i in range(len(fr)):
  fr[i] = int(fr[i])
newlist = []
for i in fr:
  newlist.append(int(i))

print(fr)
print(newlist)
print(f'avg1stRow =  {sum(fr)/len(fr)}')



```

    l, w, t
    2,5,6
    ['2', '5', '6']
    [2, 5, 6]
    [2, 5, 6]
    avg1stRow =  4.333333333333333



```python
# Using the data above, calculate the area of all 3 objects

```
