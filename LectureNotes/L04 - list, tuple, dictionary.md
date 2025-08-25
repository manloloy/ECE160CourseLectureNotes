# Example Program without Lists
Write a program that takes in 6 inputs.

The program should display
the 1st, 3rd, and 5th inputs on the first output line delimited by space.
The 2nd, 4th, and 6th inputs on the second output line delimited by space.

Example Input:
```
1
2
3
4
5
6
```

Output:
```
1 3 5
2 4 6
```


So far, how we do this would be extremely inefficient. We may be using 6 variables here, but what if we had 100 or 1,000 or 100,000,000 variables?

# Introducing: Chapter 4 - ***Lists, Dictionaries, Tuples***


# ***List*** - [  ]
- A list can have many different types within it,
including **integers**, **floats**, **strings**, or **a mixed list**

For Example:

This list contains all integers.
```
intlst = [1, 2, 3]
```
This list contains floats (numbers that are not whole numbers).
```
floatlst = [3.14, 9.8]
```
This list contains only strings.
```
stringlst = ['hello','5', 'Chris']
```
Finally, this list contains a mix of an integer, float, and string.
```
mixlst = [1, 3.14, 'hello']
```
**You can mix types in a list (exclusive to python)**

## *Intlst (Integer List)*
```
intlst=[1, 2, 3]
print(f'intlst: {intlst} {type(intlst)}')
```
output
```
intlst: [1, 2, 3] <class 'list'>
```

- We can access individual elements in this list using an index [].
- A variables storing a list with brackets after it, this is accessing a specific index

**IMPORTANT: indexes start a 0**

Example:
```
intlst = [1, 2, 3]
print(f'intlst[0]: {intlst[0]} {type(intlst[0])}')
```
Output:
```
intlst[0]: 1 <class 'int'>
```


- We can modify individual elements by index

For example:

Taking the intlst from the previous example if we add this to the end of our previous code it will look something like this:
```
intlst = [1, 2, 3]
print(f'intlst[0]: {intlst[0]} {type(intlst[0])}')
intlst[1] = 100 # Updates value at index 1
print(f'intlst: {intlst} {type(intlst)}')
```
The output will be:
```
intlst[0]: 1 <class 'int'>
intlst: [1, 100, 3] <class 'list'>
```


# ***Tuple*** - (  )
Example:
```
inttpl = (1,2,3)
print(f'inttpl: {inttpl} {type(inttpl)}')
print(f'inttpl[2]: {inttpl[2]} {type(inttpl[2])}')
```

The output will be:
```
inttpl: (1, 2, 3) <class 'tuple'>
inttpl[2]: 3 <class 'int'>
```

- **Cannot change elements**
- inttple[1] = 100 will result in error
- but you can do inttple = (3,2,1)

# ***Dictionary*** - {  }
- Similar to a list but indexes are set by the programmer
- Indexes do not have to be integers starting at 0
- Usually these are called key - value pairs

An Example Dictionary:
```
intdct = {'key1': 1, 'key2': 2, 'key3': 3}
print(intdct, type(intdct))
print(intdct['key1'])
```
The output of this would be:
```
{'key1': 1, 'key2': 2, 'key3': 3} <class 'dict'>
1
```

# Other important list functions
- sum() - returns the sum of all elements within the list
- len() - returns the length of list
- min() - returns the smallest value in the list
- max() - returns the largest value in the list
- list.append() - adds new value to the end of the list
- list.remove() - removes first instance of a specific value from list
- list.pop() - by default removes the last element of a list, can be specified which element by index value

# Practice problems

Write a program that calculates the average grade out of a class of 5 students

Example Input:

```
56.78
95.25
86.36
91.53
78.26
```

Output:
```
81.64
```


Write a program that takes 5 grades from two sections and then calculates the average of section 1, section 2, and the total class average. The first 5 grades given are the first section, the second set of 5 grades are the second section.

Example Input:

```
56.78
95.25
86.36
91.53
78.26
63.16
84.27
96.26
72.96
43.83
```

Output:

```
Section 1 average: 81.64
Section 2 average: 72.10
Class average: 76.87
```


```python
lst = [1, 2, 3]
total = sum(lst)
print(total)
print(min(lst))
print('len(lst):',len(lst))
lst.append(100)
print('len(lst)2:',len(lst))
print(lst)
lst[1] = 200
print(lst)
```

    6
    1
    len(lst): 3
    len(lst)2: 4
    [1, 2, 3, 100]
    [1, 200, 3, 100]



```python
# get the first 5 scores and insert into a list
num1 = int(input())
num2 = int(input())
num3 = int(input())
num4 = int(input())
num5 = int(input())
section1 = [num1, num2, num3, num4, num5]
# get the second 5 scores abd insert into a list
section2 = []
num = int(input())
section2.append(num)
num = int(input())
section2.append(num)
num = int(input())
section2.append(num)
num = int(input())
section2.append(num)
num = int(input())
section2.append(num)


# create total list
course = section1 + section2
#print(section1)
#print(section2)
#print(course)
# calculate 3 different averages
#display

print(f'section 1 average: {sum(section1)/len(section1):.2f}')
print(f'section 2 average: {sum(section2)/5:.2f}')
print(f'course average: {sum(course)/10:.2f}')

```

    75
    75
    75
    75
    75
    50
    50
    75
    100
    100
    [75, 75, 75, 75, 75]
    [50, 50, 75, 100, 100]
    [75, 75, 75, 75, 75, 50, 50, 75, 100, 100]
    section 1 average: 75.00
    section 2 average: 75.00
    course average: 75.00



```python

```


```python

```
