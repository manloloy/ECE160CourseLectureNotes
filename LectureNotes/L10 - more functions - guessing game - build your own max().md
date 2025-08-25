# More Functions Example 1
Build a function that has 1 parameter. The parameter must be an integer between 1 and 100. If the number given is not between 1 and 100 the function should return -1. If the function is given a valid number then the function should return the result of following the algorithm below.

Use the following algorithm on the given integer
- multiply the int by 4
- add 12
- multiply by 2
- add 16
- divide by 8
- subtract the original number

```
def magic(number):
def magic(number: int) -> int:
```

Test you function with multiple inputs and see what the outputs are. Hint: (5).


```python
# write your code here
def magic(number):
  if number <= 1 or number >= 100:
    return -1
  # multiply the int by 4
  x = number*4
  # add 12
  x += 12 # x = x + 12
  # multiply by 2
  x *= 2 # x = x*2
  # add 16
  x += 16
  # divide by 8
  x /= 8
  # subtract the original number
  x = int(x) - number
  return x

if __name__ == '__main__':
  print(magic(-5))
  x = magic(10)
  print(x)
  tests = list(range(-10,111))
  correct = 0
  for test in tests:
    #print(test)
    if test <= 1 or test >=100:
      if magic(test) == -1:
        correct +=1
    else:
      if magic(test) == 5:
        correct += 1
      #print(magic(test))
  print(f'correct answers: {correct}')
```

    -1
    5
    correct answers: 121


# More Function Examples
Build a function that works like the max() function you use on lists without using the max() function itself.

```
# recall the output of the max function
print(max([1,2,3]))
lst = [9,10,8,0,1,2,3]
m = max(lst)
print(m)
```

Name your function ListMax(lst). It takes one parameter named lst which represents a list of integers or floats. The function should return the
maximum value in the list. Again, you may not use the max() function



```python
def ListMax(lst):
  # given a list of numbers (int or float)
  # return the highest value in that list.
  if len(lst) == 0:
    return None
  # set the maximum
  ma = lst[0]
  # loop through all values
  for num in lst:
    # if a value is larger than the current max
    if num > ma:
      # set as maximumn
      ma = num
  return ma
```


```python
def ListMax(lst):
  if len(lst) == 0:
    return None
  for i in range(len(lst)):
    if i == 0:
      ma = lst[i]
    else:
      if lst[i] > ma:
        ma = lst[i]
  return ma
```

## Let's revisit ```if __name__ == "__main__":```
Take a look at the code below. There appears to be no difference in running.
I will redo these examples in class using different files as well.


```python
# Build me a function that calculates the area of a circle

# understand the difference between the two progams below.

def Circle_Area(radius):
  return 3.14*radius*radius
print(Circle_Area(5))

def Circle_Area(radius):
  return 3.14*radius*radius
if __name__ == '__main__':
  print(Circle_Area(5))
```

# In Class examples To clarify ```__name__```

In class you can try separating the functions and tests into different files.
You can see how imports work and why ```if __name__ == "__main__":``` is needed.

If you still need help with this, make sure to ask your instructor to clarify.


# Generic Guessing game. (without functions. We will implement functions in a larger example later)
Build a Guessing game. When the program starts the user will be given 3 chances to guess the random number generated between 1 and 100. If the user guesses lower or higher than number given them a hint by printing 'too low' or 'too high' after their guess.


```python
import random
# generate a random number between 1 and 100
number = random.randint(1,100)

# loop 3 times (3 chances)
for i in range(3):
  print(f'debug-remove before deploying: {number}')
  # get the user input
  guess = int(input())
  # compare user input to the random number
  # if the user wins, we stop (break)
  if guess == number:
    print('You Win!')
    break
  # otherwise 'try again' - give a hint(too low, or too high)
  elif guess < number:
    print('too low!')
  elif guess > number:
    print('too high!')
if guess != number:
  print('You Lose!')
print('Game Over!')


```


```python

```
