# CP 10




```python
def IsValidEmail(email):
  # Given an email as a string
  # return True if Valid, False otherwise

  # does it include '=' or '!'
  if '=' in email or '!' in email:
  # alternatively if email.count('=')>0 or email.count('!')>0:
    return False

  # check the last 4 characters
  if email[-4] != '.' or email[-3] != 'c' or email[-2] != 'o' or email[-1] != 'm':
  # alternatively if email[-4:] == '.com':
    return False

  # check position of the @ symbol
  # not the first character and not the last 4
  for i in range(0, -5, -1):
    if email[i] == '@':
      return False
  # alternativly if email.startswith('@') or '@' in email[-4:]:

  # loop through email string
    # count number of '@'
  at_count = 0
  for c in email:
    if c == '@':
      at_count += 1
  if at_count != 1:
    return False
  return True

if __name__ == '__main__':
  # Get input from the user
  useremail = input()
  # while the email is invalid
  while not IsValidEmail(useremail):
    # print Invalid
    print('Invalid')
    # get a new email from the user
    useremail = input()
  # print Valid
  print('Valid')
```

# Introduction to Matrices. (Matrix)

X below, is called a matrix. X has 3 rows and 3 columns so we say that it's densions are 3 x 3 (3 by 3 which represents 3 rows and 3 columns). The elements in this matrix are $$x_{ij}$$ where i and j represent the row and column number respectively.

$$X = \begin{bmatrix}x_{11} & x_{12} & x_{13}\\
x_{21} & x_{22} & x_{23}\\
x_{31} & x_{32} & x_{33}
\end{bmatrix}$$



## What are the deminsions of the matrix B below? ##
$$B = \begin{bmatrix}-8 & -4\\
23 & 12\\
18 & 10
\end{bmatrix}$$
- answer: 3 x 2 (3 rows and 2 columns)



## what are the deminsions of C below? ##
$$C = \begin{bmatrix}-2 & 6 & 1 & 3\\
0 & -8 & 3 & 10
\end{bmatrix}$$
-answer: 2 x 4




# Matrix Elements
A matrix element is simply a matrix entry. Each element in a matrix is identified by naming the row and column in which it appears. Consider the matrix G below.

$$G = \begin{bmatrix}-8 & -4 & 2\\
5 & 23 & 12\\
0 & 18 & 10
\end{bmatrix}$$

We can see the element $$G_{12} = -4$$ and the element $$G_{33} = 10 $$

# How can we represent Matrices in python?

- Numpy is a library that is commonly used to handle matrix data (This is a section later in the book and you may cover this later if needed)
- For now, we can handle matrices by using nested lists
if we want to represent the matrix G below
$$G = \begin{bmatrix}-8 & -4 & 2\\
5 & 23 & 12\\
0 & 18 & 10
\end{bmatrix}$$

we could use the following code


```python

```


```python
G = [[-8, -4, 2], [5, 23, 12], [0, 18, 10]]
print(G)
```

# Access individual **elements**


```python
G = [[-8, -4, 2], [5, 23, 12], [0, 18, 10]]

print(G[1][2])
print(G[0][1])
G[1][1] = 99
print(G)
```

    12
    -4
    [[-8, -4, 2], [5, 99, 12], [0, 18, 10]]


# Use loops to access all elements


```python
G = [[-8, -4, 2], [5, 23, 12], [0, 18, 10]]
for i in range(3):
  for j in range(3):
    print(G[i][j], end=' ')
print()


# a good exercise for students try looping through each column instead of each row
# an example output would be
# -8 5 0 -4 23 18 2 12 10

for i in range(3):
  for j in range(3):
    print(G[j][i], end=' ')

```

    -8 -4 2 5 23 12 0 18 10 
    -8 5 0 -4 23 18 2 12 10 

# Print out the nested list by matrix


```python
G = [[-8, -4, 2], [5, 23, 12], [0, 1024, 10]]
for i in range(3):
  for j in range(3):
    print(f'{G[i][j]:5}', end =' ')
  print()
```

       -8    -4     2 
        5    23    12 
        0  1024    10 



```python
''' Example input - first line represents rows and columns
3 3
-8 -4 2
5 23 12
0 18 10
'''
# We know an input is a 3 x 3 matrix where each element in the row is separated
# by spaces
[r, c] = input().split()
[r, c] = [int(r), int(c)]
#[r, c] = [int(x) for x in input().split()] # this is list comprehension
matrix = []
for i in range(r):
  matrix.append(input().split())
  #matrix.append([int(x) for x in input().split()]) #this is list comprehension
print(matrix)
```

# List Comprehension
This is a way to do an operation on every element in a list and return a list


```python
z = ['1', '2', '3']

# the old way
for i in range(3):
  z[i] = int(z[i])
print(z)

y = [int(x) for x in z]
print(y)

w = [1, 2, 3, 4, 5]
print([x**2 for x in w])
```


```python
# build a 3x3 matrix
m = []
for i in [1,2,3]:
  row = []
  for j in [1,2,3]:
    row.append(i*j)
  m.append(row)
print(m)

```
