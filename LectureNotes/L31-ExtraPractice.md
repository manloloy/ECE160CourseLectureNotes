# 1.
Write a program that will allow the user to enter an email address.
Our particular system will not work with certain characters so we will not allow users to use the characters '=' and '!'. If any of those characters is detected then the email is invalid.
In addition the email must contain only 1 '@' symbol. The '@' symbol must not be the first character or part of the last 4 characters. In this example, we will assume the last 4 characters will be '.com'. A valid email will have the '.com' portion at the end.

If the email is valid, the output of the program should be "Valid Email".
If the email is invalid, the output of the program should be "Invalid Email" and the program should ask the user to input an email. The program should continue until the user puts in a valid email.
NOTE: this system does not work to find all invalid emails. This is just what
we decided to check.

Ex:

The input is:
```
EE160Rocks@gmail.com

```
The output should be:
```
Valid Email
```

Ex:

The input is:
```
johndoe@hawaii.edu
johndoe@gmail.com
```
The output should be:
```
Invalid Email
Valid Email
```

Ex:

The input is:
```
@UHManoa!!@gmail.com
UHManoa@gmail.com
```
The output should be:
```
Invalid Email
Valid Email
```


```python
# Code for problem 1

# def IsValidEmail(str: email) -> bool
def IsValidEmail(email):
  '''
  Given: email as string
  Return: True if email is valid. Flase Otherwise
  '''
  # cannont have '@' at index 0
  if email[0] == '@':
    return False
  # only 1 @
  at_count = 0
  for i in range(len(email)):
    if email[i] == '@':
      at_count += 1
  if at_count != 1:
    return False
  # last 4 must be '.com'
  if (email[-4] != '.') or (email[-3] != 'c') or (email[-2] != 'o') or (email[-1] != 'm'):
    return False
  # no '=' or '!'
  if ('=' in email) or ('!' in email):
    return False

  '''
  badSymbols = ['=', '!']
  for symbol in badSymbols:
    if symbol in email:
      return False
  '''
  return True

if __name__ == '__main__':
  email = input()
  while not IsValidEmail(email):
    print('Invalid Email')
    email = input()
  print('Valid Email')


```

    chris@hawaii.edu
    Invalid Email
    chirs@hawaii.com
    Valid Email


# 2.
Write a program that takes data entered by a user and display the data as a table. The user will enter the number of rows followed by
the number of columns. After that the user will enter the exact amount of data to fill the table. The data is given in floats and should be displayed with 2 decimal places. The data is also guaranteed to be between 10 and 99.

NOTE: If the input could be any number, there is still a way to build a nice table. Could you do that?

Example 1
# Example Input:
```
3
5
10.551
67.413
15.5742
15.8931
75.2831
10.551
67.413
15.5742
15.8931
75.2831
10.551
67.413
15.5742
15.8931
75.2831
```

#Example Output:
```
10.55 67.41 15.57 15.89 75.28
10.55 67.41 15.57 15.89 75.28
10.55 67.41 15.57 15.89 75.28
```

Example 2
#Example Input:
```
2
2
15.261
45.7912
13.9632
93.571
```

#Example Output
```
15.26 45.79
13.96 93.57
```

####################################################


```python
# get row and column
row  = int(input())
col = int(input())
data = []
for i in range(row*col):
  data.append(float(input()))

count = 0
for i in range(row*col):
  if count != col-1:
    print(f'{data[i]:.2f}', end=' ')
    count += 1
  else:
    print(f'{data[i]:.2f}')
    count = 0





```

    3
    5
    10.0
    11.1
    12.12
    13.13
    14.14
    15.15
    16.16
    17.17
    18.18
    19.19
    20.20
    21.21
    22.22
    23.23
    24.24
    10.00 11.10 12.12 13.13 14.14
    15.15 16.16 17.17 18.18 19.19
    20.20 21.21 22.22 23.23 24.24


# 3
Write a function named Rectangle_Area(width, length) with the following specifications:
```
Rectangle_Area(width: float, length: float) -> float:
    #Given: the length and width of a rectangle (both float)
    #Return: return the area of the rectangle
```
For the main program make sure you use:
```
if __name__ == '__main__':
```
In the same file write a program that uses your function to ask users for a length and a width in meters. The program should display the area of the resulting rectangle. The program should continue to ask the user to enter a new length and width. The program will continue until the user enters 0 for either length or width. Print "Program Ended!" before the program ends.

Ex:

The input is:
```
5.1
11.2
11.2
5.1
5.1
0
```

The output is
```
The area of the rectangle is 57.12 square meters
The area of the rectangle is 57.12 square meters
Program Ended!
```


```python
def Rectangle_Area(width: float, length: float) -> float:
    #Given: the length and width of a rectangle (both float)
    #Return: return the area of the rectangle
    return width * length

if __name__ == '__main__':
  length = float(input())
  while length != 0:
    width = float(input())
    if width == 0:
      break
    print(Rectangle_Area(width, length))
    length = float(input())
  print('Program Ended!')
```

    1
    1
    1.0
    1
    0
    Program Ended!



