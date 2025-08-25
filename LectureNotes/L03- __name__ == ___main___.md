# if ```__name__ == "__main__"```: - What is this?
Our material introduces this. We can study it much later

There are two ways to write main code.
- I'm going to show two variations of code
- I will show they are equivalent so far
- Give a brief explanation on what is the real difference





```python
# A program to multiply 2 numbers
# Get two numbers
x = int(input())
y = int(input())

# Calculate the product
p = x * y

# Display the result rounded to 2 decimal
print(f'{p: .2f}')
```

    1
    2
     2.00



```python
# using if __name__ == "__main__":

if __name__ == "__main__": # if this statement is true, the whole block runs
  # Get two numbers
  x = int(input())
  y = int(input())
  # Calculate the product
  p = x * y
  # Display the result rounded to 2 decimal
  print(f'{p: .2f}')

```

    1
    2
     0.50


# What's the difference
All the code tabbed in under the "if statement" are all under the same block of code



```python
print(__name__, type(__name__))
```

    __main__ <class 'str'>



```python
if __name__ == "__main__":
  print('Hello from "if"')
  print(__name__, type(__name__))
print('heLLO')
print(__name__)

```

    Hello from "if"
    __main__ <class 'str'>
    heLLO
    __main__



```python
if __name__ == "x":
  print('Hello from "if"')
  print(__name__)
print('heLLO')
print(__name__)
```

    heLLO
    __main__


# when to use ```if __name__ == '__main__'```
This is easier explained on a local installation using multiple files and imports. Since this is a beginner class just understand that if you are running a single file program, the ```__name__``` variable is always set to ```__main__```. If you are running a multiple file python program then only the executed file's name will be ```__main__```.

If you are still confused by this, wait until we reach functions for a better explanation. For now, you may use to identify your main program. You will be responsible to understand this use by midterm 1.
