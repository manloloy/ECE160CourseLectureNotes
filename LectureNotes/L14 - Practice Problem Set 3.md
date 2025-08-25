# More Examples Before The Midterm
Problems taken from various sources

# Sum without highest and lowest
list and array are used interchangebly here.

Build a function that wil sum all the numbers of a given array ( or list ), except the highest and the lowest element ( by value, not by index! ). The function should return the calculated sum given a list of integers.

The highest or lowest element respectively is a single element at each edge, even if there are more than one with the same value.

Mind the input validation.

Example
```
[ 6, 2, 1, 8, 10 ] the function returns 16
[ 1, 1, 11, 2, 3 ] the function returns 6
```
Input validation
If an empty value ( null, None, Nothing etc. ) is given instead of an array, or the given array is an empty list or a list with only 1 element, return 0.

Prototype:
```
def sum_array(arr):
```


```python
def sum_array(arr):
  pass
if __name__ == '__main__':
  pass
```

# Can this shape possibly be a cube?
To find the volume (centimeters cubed) of a cuboid you use the formula:

$Volume = Length * Width * Height$

But someone forgot to use proper record keeping, so we only have the volume, and the length of a single side!

It's up to you to find out whether the cuboid might possibly have equal s`ides (= is a cube).

Build a function that returns the following given the length of a single side and the volume:

* Return true if the cuboid could have equal sides, return false otherwise.
* Return false for invalid numbers too (e.g volume or side is less than or equal to 0).

Note: side will be an integer

Prototype:
```
def cube_checker(volume, side):
```


```python
def cube_checker(volume, side):
  pass
if __name__ == '__main__':
  pass
```

# powers of 2
Build a function that takes a non-negative integer n as input, and returns a list of all the powers of 2 with the exponent ranging from 0 to n ( inclusive ).

Examples
```
n = 0  ==> [1]        # [2^0]
n = 1  ==> [1, 2]     # [2^0, 2^1]
n = 2  ==> [1, 2, 4]  # [2^0, 2^1, 2^2]
```
Prototype
```
def powers_of_two(n):
```


```python
def powers_of_two(n):
  pass
if __name__ == '__main__':
  pass
```

# Majority Element
Build a function.
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array and there is also only 1 majority element.



Example 1:
```
Input: nums = [3,2,3]
Output: 3
```
Example 2:
```
Input: nums = [2,2,1,1,1,2,2]
Output: 2
```

Constraints:

* n == nums.length
* 1 <= n <= 5 * 104
* -109 <= nums[i] <= 109

Prototype
```
def majorityElement(nums: list) -> int:
```





```python
#def majorityElement(nums: list) -> int:
def majorityElement( nums ):
    """
    :type nums: List[int]
    :rtype: int
    """
```

# Valid Anagram
Build a Function which given two strings s and t, returns True if t is an anagram of s, and False otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.


Example 1:
```
Input: s = "anagram", t = "nagaram"
Output: true
```
Example 2:
```
Input: s = "rat", t = "car"
Output: false
```

Constraints:

* 1 <= s.length, t.length <= 5 * 104
* s and t consist of lowercase English letters.

prototype:
```
def isAnagram(s: str, t: str) -> bool:
```


```python
# def isAnagram(s: str, t: str) -> bool:
def isAnagram(s, t):
    """
    :type s: str
    :type t: str
    :rtype: bool
    """
    pass
```
