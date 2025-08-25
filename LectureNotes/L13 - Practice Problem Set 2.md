# Mini Mock Exam
This is a mock exam to understand the midterm process. The real midterm will have a different number of problems with more randomization.

Below are additional problems like the last class. This time from leetcode.com


# 1. Palindrome Number
Write a function.
Given an integer x, return True if x is a palindrome, and False otherwise.


Example 1:
```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```
Example 2:
```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
Example 3:
```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```


Constraints:
```
-231 <= x <= 231 - 1
```

Prototype
```
def isPalindrome(x: int) -> bool:
# generic prototype
def isPalindrom(x):
  '''
  x is an integer
  return type (rtype) is boolean
  '''
```


```python
def isPalindrome(x: int) -> bool:
  pass
if __name__ == '__main__':
  pass
```

# 2. Roman Numeral Converter
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

* Symbol       Value
* I             1
* V             5
* X             10
* L             50
* C             100
* D             500
* M             1000


For example, 2 is written as II in Roman numeral, just two ones added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:
```
    I can be placed before V (5) and X (10) to make 4 and 9.
    X can be placed before L (50) and C (100) to make 40 and 90.
    C can be placed before D (500) and M (1000) to make 400 and 900.
```
Given a roman numeral, convert it to an integer.



Example 1:
```
Input: s = "III"
Output: 3
```
Explanation: III = 3.


Example 2:
```
Input: s = "LVIII"
Output: 58
```
Explanation: L = 50, V= 5, III = 3.


Example 3:
```
Input: s = "MCMXCIV"
Output: 1994
```
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.


Constraints:
```
    1 <= s.length <= 15
    s contains only the characters ('I', 'V', 'X', 'L', 'C', 'D', 'M').
    It is guaranteed that s is a valid roman numeral in the range [1, 3999].
```

prototype
```
def romanToInt(s: str) -> int:

```


```python
def romanToInt(s: str) -> int:
  pass

if __name__ == '__main__':
  pass
```

# 3. Longest Common Prefix
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".



Example 1:
```
Input: strs = ["flower","flow","flight"]
Output: "fl"
```
Example 2:
```
Input: strs = ["dog","racecar","car"]
Output: ""
```
Explanation: There is no common prefix among the input strings.


Constraints:
```
    1 <= strs.length <= 200
    0 <= strs[i].length <= 200
    strs[i] consists of only lowercase English letters.
```

prototype
```
def longestCommonPrefix(strs: List[str]) -> str:
```



```python
def longestCommonPrefix(strs: List[str]) -> str:
  pass
if __name__ == "__main__":
  pass

```

# 4. Valid Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

* Open brackets must be closed by the same type of brackets.
* Open brackets must be closed in the correct order.
* Every close bracket has a corresponding open bracket of the same type.



Example 1:
```
Input: s = "()"
Output: true
```

Example 2:
```
Input: s = "()[]{}"
Output: true
```

Example 3:
```
Input: s = "(]"
Output: false
```


Constraints:

* 1 <= s.length <= 104
* s consists of parentheses only '()[]{}'.

prototype:
```
def isValid(self, s: str) -> bool:
```


```python
def isValid(self, s: str) -> bool:
  pass
if __name__ == '__main__':
  pass

```


```python

```
