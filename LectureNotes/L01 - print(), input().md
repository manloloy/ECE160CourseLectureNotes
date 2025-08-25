### **Lecture 1**


```python
# This is a one line comment
# Anything after a pound sign on the same line, will be a comment

''' This
is a multi line
comment. \n is a newline character that moves output to a newline.
'''

"""
This also works
as
a multi line comment
"""

```




    '\nThis also works\nas \na multi line comment\n'



First let's learn how to print to the screen. The function to print to the screen is named **print()**.

'Hello World!' below is called a *string*. Any characters between apostrophes or quotes is a *string*.

The **print()** functions prints any string between the parentheses to the display.



```python
# Output desired phrase
# the function is named print()
print('Hello World!')


```

    Hello World!



```python
print('3')
print('2')
print('1\nHappy New Year!')
```

    3
    2
    1
    Happy New Year!


# Variables
To store the string 'Hello Python' into a variable named x we can execute the following code.

x = 'Hello Python!'

The **'='** is the assignment operator. Store what's on the right into the variable on the left

Variables can only hold one item at a time. We will discuss storing groups of items later in the class.

We can also print variables to the screen. This is show in the code below.



```python
# let's print x

# assign a string to x
x = 'Hello!'

# Output x
print(x)

# Repeat same process as above: get x from input then output x
x = 'Bye!'
print(x)

```

    Hello!
    Bye!


# User Input
How do we get input from the user?

The **input()** funtion.

This function takes 1 line of input from the user as a string



```python
# we can store the input into a variable
# input() allows the user to enter an input as a string
x = input() # The input is a string that is stored in x

# we can print the contents of the variable x by using the print function
print(x)

```

    chris
    chris


## For the code above, what is the **difference** between print(x) and print('x')?
**print(x)** - this prints the contents of the variable x to the screen.

***print('x')*** - this prints the string 'x' to the screen





```python
# x is given from input
x = 'A Random String.'

# However, output 'x' by itself, disregarding what was given from input
print('x')

# Output from given input
print(x)
```

    x
    A Random String.



```python

```

# Prompting
The input function can also take a string as an argument. The string will be printed to the screen to prompt the user for an input.




```python
# Assign y as input from given string
y=input('Enter your name:\n')

# Output desired input
print(y)
```

    Enter your name:chris
    chris



```python
print('Enter your name:')
z = input()
print(z)
```

    Enter your name:
    chris
    chris


# How to print multiple variables and strings to the display.
This can be accomplished by separating print items with commas





```python
# Get x from input given string
x = input('Enter your Nickname: ')

# Get y from input given string
y = input('Enter your Full Name: ')

# Output x and y on the same line, there will not be a comma
print(x,y)

# Output sentence using given words and x and y from input
print('hello', x,'.', 'Is your full name',y,'?')


```

    Enter your Nickname: chris
    Enter your Full Name: manloloyo
    chris manloloyo
    hello chris . Is your full name manloloyo ?


# How to combine strings.
Doing this will allow you to combine two separate string variables into one variable.


```python
# Get x from input given string
x = input('Enter your first name: ')

# Get y from input given string
y = input('Enter your last name: ')

# Output x and y separately
print(x, y)

# Combine x and y into a new variable
# Use ' ' to add a space inbetween the two variables
z = x + ' ' + y

# Print z variable to the screen
print('hello, my name is', z)

# The same can also be acomplished without combining the variables
# Combining variables has many uses later in this class
print('hello, my name is', x, y)
```

    Enter your first name: chris
    Enter your last name: manloloyo
    chris manloloyo
    hello, my name is chris manloloyo
    hello, my name is chris manloloyo

