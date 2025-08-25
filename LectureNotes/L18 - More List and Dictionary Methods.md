# List Sorting
- There are in depth sorting methods that will be discussed later in the class
- sorting time complexity depends on the sorting technique used
- check chapter 18
- for now let's explore the list.sort() method


```python
lst = [1, 5, 3, -10, 11, 12, 6]
# prints the original list
print(lst)
# sort the list - this returns None
print(lst.sort())
# the list should now be sorted
print(lst)

# Can you build your own sort algorthim for small lists?
```

    [1, 5, 3, -10, 11, 12, 6]
    None
    [-10, 1, 3, 5, 6, 11, 12]


# List Reversing
The reverse() method can be used to reverse a list (list.reverse())


```python
lst = [1, 5, 3, -10, 11, 12, 6]
# prints the original list
print(lst)
# The reverse method returns None
print(lst.reverse())

# the list should now be reversed
print(lst)
```

    [1, 5, 3, -10, 11, 12, 6]
    None
    [6, 12, 11, -10, 3, 5, 1]


# List slicing
This is similar to string slicing



```python
lst = [1, 5, 3, -10, 11, 12, 6]
# prints the original list
slc = lst[2:6]
print(slc, type(slc))

```

    [3, -10, 11, 12] <class 'list'>


# Dictionary Methods
- testing for key


```python
# to test for a key in a dictionary, you can use the "in" keyword
dct = {'chris': 76.5, 'david': 99.2, 'emily': 83.4}
print(dct, type(dct))
print('Is "david" a key in the dictionary?','david' in dct)
print('Is "nikki" a key in the dictionary?', 'nikki' in dct)

# example of usage
if 'david' in dct:
  print("david's records are in the dictionary")
else:
  print("david's records were not found")
```

- iterating over all keys


```python
dct = {'chris': 76.5, 'david': 99.2, 'emily': 83.4}
for i in dct:
  print(i, end=' ')
print()
for key in dct:
  print(key, end=' ')
print()
for key in dct:
  print(dct[key], end= ' ')

print(dct.values, type(dct.values))


```

    chris david emily 
    chris david emily 
    76.5 99.2 83.4 <built-in method values of dict object at 0x7dc2ce64adc0> <class 'builtin_function_or_method'>


dictionary method dictionary.get()

* dictionary.get(key)
* dictionary.get(key, default)


```python
dct = {'chris': 76.5, 'david': 99.2, 'emily': 83.4}
print(dct.get('chris'))

# the issue is what if the key doesn't exist
print(dct.get('nikki'))
# it should return None.

# if you want a default value for non existant keys
print(dct.get('nikki', 'default string'))

```

    76.5
    None
    default string


# Nested Dictionaries


```python
dct = {'chris': {'hw': [55, 67, 88], "exams": 68.1, 'lab': 73.9}, 'david': {'hw': [99, 97, 98], "exams": 88.1, 'lab': 93.9}, 'emily': {'hw': [87, 81, 80], "exams": 82.0, 'lab': 83.9}}
print(dct)
print(dct['emily'])
print(dct['emily']['hw'])
print(dct['emily']['hw'][1])

cmplx = [dct, dct, dct]
print(cmplx)

for cdct in cmplx:
  print(cdct['david']['hw'][2])
```

    {'chris': {'hw': [55, 67, 88], 'exams': 68.1, 'lab': 73.9}, 'david': {'hw': [99, 97, 98], 'exams': 88.1, 'lab': 93.9}, 'emily': {'hw': [87, 81, 80], 'exams': 82.0, 'lab': 83.9}}
    {'hw': [87, 81, 80], 'exams': 82.0, 'lab': 83.9}
    [87, 81, 80]
    81
    [{'chris': {'hw': [55, 67, 88], 'exams': 68.1, 'lab': 73.9}, 'david': {'hw': [99, 97, 98], 'exams': 88.1, 'lab': 93.9}, 'emily': {'hw': [87, 81, 80], 'exams': 82.0, 'lab': 83.9}}, {'chris': {'hw': [55, 67, 88], 'exams': 68.1, 'lab': 73.9}, 'david': {'hw': [99, 97, 98], 'exams': 88.1, 'lab': 93.9}, 'emily': {'hw': [87, 81, 80], 'exams': 82.0, 'lab': 83.9}}, {'chris': {'hw': [55, 67, 88], 'exams': 68.1, 'lab': 73.9}, 'david': {'hw': [99, 97, 98], 'exams': 88.1, 'lab': 93.9}, 'emily': {'hw': [87, 81, 80], 'exams': 82.0, 'lab': 83.9}}]
    98
    98
    98



```python

```
