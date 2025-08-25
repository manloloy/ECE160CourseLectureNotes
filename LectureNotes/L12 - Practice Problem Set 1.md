[link text](https://)
Some practice problems from codewars.com

# 1. Neutralisation






Given two strings comprised of + and -, return a new string which shows how the two strings interact in the following way:

* When positives and positives interact, they remain positive.
* When negatives and negatives interact, they remain negative.
* But when negatives and positives interact, they become neutral, and are shown as the number 0.
* The strings will always be the same size

**Description of the function**
```
("+-+", "+--") ➞ "+-0"
# Compare the first characters of each string, then the next in turn.
# "+" against a "+" returns another "+".
# "-" against a "-" returns another "-".
# "+" against a "-" returns "0".
# Return the string of characters.
```

**Examples**
```
("--++--", "++--++") ➞ "000000"
("-+-+-+", "-+-+-+") ➞ "-+-+-+"
("-++-", "-+-+") ➞ "-+00"
```

**Prototype**
```
def neutralise(s1, s2):
```


```python
def neutralise(s1, s2):
  pass
if __name__ == '__main__':
  pass
```


      File "<ipython-input-2-2dc7c9f715b3>", line 3
        if __name__ == '__main__':
        ^
    IndentationError: expected an indented block after function definition on line 1



#2. A Letter's Best Friend

Build a function. Given a string, return if a given letter always appears immediately before another given letter.

**Description**
```
("he headed to the store", "h", "e") ➞ True

# All occurences of "h": ["he", "headed", "the"]
# All occurences of "h" have an "e" after it.
# Return True

('abcdee', 'e', 'e') ➞ False

# For first "e" we can get "ee"
# For second "e" we cannot have "ee"
# Return False
```

**Examples**
```
("i found an ounce with my hound", "o", "u") ➞ True

("we found your dynamite", "d", "y") ➞ False
```

**Notes**
* All senetences will be given in lower case


**Prototype**
```
def best_friend(txt, a, b):
```


```python
def best_friend(txt, a, b):
  pass
if __name__ == '__main__':
  pass
```

#3. Flick Switch


Create a function that always starts by returning True/true for every item in a given list.
However, if an element is the word 'flick', switch to always returning the opposite boolean value.

**Examples**
```
['codewars', 'flick', 'code', 'wars'] ➞ [True, False, False, False]

['flick', 'chocolate', 'adventure', 'sunshine'] ➞ [False, False, False, False]

['bicycle', 'jarmony', 'flick', 'sheep', 'flick'] ➞ [True, True, False, False, True]
```

**Notes**
* "flick" will always be given in lowercase.
* A list may contain multiple flicks.
* Switch the boolean value on the same element as the flick itself.

**Prototype**
```
def flick_switch(lst):
```


```python
def flick_switch(lst):
  pass
if __name__ == '__main__':
  pass
```

#4. Quadrants


Build a Function. Given a point in a Euclidean plane (x and y axis), return the quadrant the point exists in: 1, 2, 3 or 4 (integer). x and y are non-zero integers, therefore the given point never lies on the axes.

**Reference**

![quadrant image](https://raw.githubusercontent.com/manloloy/EE160Images/main/quadrant.png)

There are four quadrants:

1. First quadrant, the quadrant in the top-right, contains all points with positive X and Y
2. Second quadrant, the quadrant in the top-left, contains all points with negative X, but positive Y
3. Third quadrant, the quadrant in the bottom-left, contains all points with negative X and Y
4. Fourth quadrant, the quadrant in the bottom-right, contains all points with positive X, but negative Y


**Examples**
```
(1, 2)     => 1
(3, 5)     => 1
(-10, 100) => 2
(-1, -9)   => 3
(19, -56)  => 4
```


**Prototype**
```
def quadrant(x,y):
```


```python
# def quadrant(x: int, y: int) -> int:
def quadrant(x, y):
  pass
if __name__ == '__main__':
  pass
```

#5. Check same case


Write a function that will check if two given characters are the same case.

* If either of the characters is not a letter, return -1
* If both characters are the same case, return 1
* If both characters are letters, but not the same case, return 0

**Examples**
'a' and 'g' returns 1

'A' and 'C' returns 1

'b' and 'G' returns 0

'B' and 'g' returns 0

'0' and '?' returns -1

**Prototype**
```
def same_case(a, b):
```


```python
def same_case(a, b):
  pass
if __name__ == '__main__':
  pass
```



```
# This is formatted as code
```

# 6. Multiply by the number

Build a function. Jack really likes his number five: the trick here is that you have to multiply each number by 5 raised to the number of digits of each numbers, so, for example:
```
multiply(3) == 15 # 3 * 5¹
multiply(10) == 250 # 10 * 5²
multiply(200) == 25000 # 200 * 5³
multiply(0) == 0 # 0 * 5¹
multiply(-3) == -15 # -3 * 5¹
```

**Prototype**
```
def mutiply(n):
```


```python
def multiply(n):
  pass
if __name__ == '__main__':
  pass
```

#7. Convert a string to a number

We need a function that can transform a string into a number. What ways of achieving this do you know?

Note: Don't worry, all inputs will be strings, and every string is a perfectly valid representation of an integral number.

**Examples**
```
"1234" --> 1234
"605"  --> 605
"1405" --> 1405
"-7" --> -7
```


```python
def string_to_number(s):
  # your code here
  pass
if __name__ == '__main__':
```


      File "<ipython-input-6-b6b7383e38a4>", line 4
        if __name__ == '__main__':
                                  ^
    SyntaxError: incomplete input


