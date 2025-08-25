# Lists
So far we've learned 3 data types. We can store ints, floats, and strings into a variable and manipulate them. A list is simply a group of items.

to create a list we use '[]'
```
x = [] # x is a empty list
```




```python
lst = []
print(lst, type(lst))
lst2 = [1, 2, 3] # separate values by commas - a list of integers
print(lst2)

# because the list is a special list object, it comes with built in methods (functions)
# we will learn the difference later
# list class has methods
# list.append() - where append is a list method

lst2.append(4)
print(lst2)
lst2.remove(2)
lst2.append(100)
print(lst2)
# make sure you study the different list methods in the textbook.


#There are some other functions we can use that are useful
# len()
# sum()
# max()
# min()
lst3 = [-2, 0, 2]
l = len(lst3)
print(l)
s = sum(lst3)
ma = max(lst3)
mi = min(lst3)
print(f'length: {l}, sum: {s}, max: {ma}, min: {mi}')
```

    [] <class 'list'>
    [1, 2, 3]
    [1, 2, 3, 4]
    [1, 3, 4, 100]
    3
    length: 3, sum: 0, max: 2, min: -2



```python
lst4 = [3.14, 9.8, 1024.0]
index0 = lst4[0]
print(index0, lst4[1])
print(lst4[2])

lst4[1] = -12.7

print(lst4)

# weird stuff in python
x = [1, 3.14, 'hello']
print(x)
lst4[1] = 'hi'
print(lst4)

z = 10
x = [1, 2, z]
print(x)


```

    3.14 9.8
    1024.0
    [3.14, -12.7, 1024.0]
    [1, 3.14, 'hello']
    [3.14, 'hi', 1024.0]
    [1, 2, 10]


# Tuple
A tuple uses '()' instead of square brackets. The main difference between a tuple and a list is that a tuple is immuatable.


```python
t = (1,2,3)
print(t, t[2], type(t))

#mainly we cannont do the following
#t[1] = 0
```

    (1, 2, 3) 3 <class 'tuple'>


# Dictionary
For dictionaries we use '{}'
usually we refer to items in a dictionary as key/value pairs. You can think of this as index/value pairs.

key/value pairs
index/value pairs



```python
x = {} # a empty dictionary
print(x, type(x))

dct = {'chris': 77.1, 'emily': 85.4, 'david': 99.1} # keys are strings and values are float
print(dct)

c = dct['chris']
print(c)


dct = {0: 77.1, 1: 85.4, 2: 99.1} # keys are strings and values are float
print(dct[2])

```

    {} <class 'dict'>
    {'chris': 77.1, 'emily': 85.4, 'david': 99.1}
    77.1
    99.1


# Nesting examples
This concept actually follows through basic programming a lot



```python
lst= [1,2,3]
dct = {'a':0, 'b': 1, 'c': 2}
tpl = (-3, -2, -1)
lstn = [lst, lst, lst]
print(lstn)
print(lstn[2])
print(lstn[1][0])
lstn1=[lst,tpl,dct]
print(lstn1)



dct = {'a':{'a':0, 'b': [0,[1,{"a": 0, "b": 1},3],0], 'c': 2}, 'b': 1, 'c': 2}
print(dct['a']['b'][1][1]['b'])



```

    [[1, 2, 3], [1, 2, 3], [1, 2, 3]]
    [1, 2, 3]
    1
    [[1, 2, 3], (-3, -2, -1), {'a': 0, 'b': 1, 'c': 2}]
    1

