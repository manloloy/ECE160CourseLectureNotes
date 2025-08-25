# f-strings
f-strings: these are strings that allow us to format output and format variables that are being printed

f-string example:
```
'Hello World' - normal string
f'Hello World' - an f-string
```
A simple example of printing a variable.
```
pi = 3.14
print(f'pi = {pi}')
print(f'pi={pi}')
```

Between the curly braces, you can put any valid python commands/functions



```python
pi = 3.14
print(f"pi = {pi}")
print(f'pi={pi}')
gravity = 9.8
print(f'pi: {pi}, gravity: {gravity}\n')
ob = '{'
cb = '}'
print(ob+f'{pi} = '+'{3.14}' +cb)
print(f'pi = {{pi}}')
print(f'pi = {{{pi}}}')
```

    pi = 3.14
    pi=3.14
    pi: 3.14, gravity: 9.8
    
    {3.14 = {3.14}}
    pi = {pi}
    pi = {3.14}


# Types and the type() function
This function returns the type of an object. The object can be stored in a variable



```python
x = 'Hello World!'
print(type(x), type('Hello World!'))

ten_bit = 1024
pi = 3.13

print(type(ten_bit), type(pi))
y = '10'
print(type(y))
```

# Math
- addition | subtraction (+ | -)
- multiplation | division (* | /)
- floor division (//)
- modulus (%)


```python
# addition and subtraction
x = 5
y =  10
sum = x + y
diff = x - y
print(5+10)
print(x+y)

print(f'total: {sum}, sub: {diff}')
print(f'sum is a variable with type: {type(sum)}')
```


```python
x = 5
y =  10
product = x * y
quotient = x / y
print(x*y, x/y)
print(f'prod: {product}, quo: {x/y}')
print(f'prod: {type(product)}, quo: {type(quotient)}')
```

    50 0.5
    prod: 50, quo: 0.5
    prod: <class 'int'>, quo: <class 'float'>



```python
# Floor division //
# division with an integer result
# normal division throwing away the decimal values

print(f'3/5: {3/5}, 3//5: {3//5}')
print(f'4/5: {4/5}, 4//5: {4//6}')
print(f'12/5: {12/5}, 12//5: {12//5}')
print(type(12//5))

```


```python
# modulus
# this is the remainder result from division
# 5/3 =  1 remainder 2 that is 1 2/5. So 5%3  = 2
print(f'5%3 = {5%3}')
print(f'6%2 = {6%2}')
#x % n = what is the range of the output?
print(527 % 12)
```

# Last topic- decimal rounding using f-strings
This is discussed more thoroughly in chapter 4. For now let's learn a basic way to round using f-strings.
```
num = 123.456789
print(f'the number is: {num}')
print(f'the number is: {num:.2f}')
```

check table 4.10.2



```python
num = 123.556789
print(f'the number is: {num}')
print(f'the number is: {num:.2f}')
print(f'the number is: {int(num)}')
```

# Example
Build a program the takes 2 numbers from the user (float). The program should display the product of the 2 number rounded to 2 decimal places.


```python
# Algorithm
# get 2 numbers from the user
# change inputs to floats
# calculate the product
# display the product with 2 decimal places
```


```python
# get 2 numbers from the user
num1 = input()
num2 = input()
# change inputs to floats
x = float(num1)
y = float(num2)
# calculate the product
prod = x*y
# display the product with 2 decimal places
print(f'{prod:.2f}')
```

    3.1
    2.1
    6.51



```python
print(f'{float(input())*float(input()):.2f}')
```

    3.1
    2.1
    6.51



