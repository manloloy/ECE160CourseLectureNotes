Today, we're going to build a custom Date class in Python that allows us to do arithmetic on dates — like subtracting one date from another or adding days to a date. This is a practical exercise that combines object-oriented programming, conditionals, helper functions, and operator overloading.

Although we can use Python’s built-in datetime library to do this in one line, we’re doing this manually to practice core programming skills.

Build a program. Given two dates, display how many days are in between those two dates. The dates should be objects and executing date1 - date2 should give you the number of days between.

class Date:
  def __init__(self, month, day, year):
    pass
  def __str__(self):
    pass
  def DaysPassed(self):
    pass

d1 = Date(12,25,2009)
d2 = Date(3,25,2024)

# let's try to make this work
daysbetween = d2 - d1 # or d1 - d2
print(daysbetween) # This should be 5204
# including d1 but not including d2
```

Disclaimer: This can be written using just 1 single main program. Functions and classes are likely not needed. But let's try to make use of many of the techniques we learned.

The program should include the following functions:
- IsLeapYear()
  - Checks whether a given year is a leap year.
  - Rule: Divisible by 4, not divisible by 100 unless also divisible by 400.
- DaysInMonth()
  - Returns how many days are in a given month for a given year.
  - February changes depending on leap year.
- DaysBetweenYears()
  - Calculates total days between Jan 1 of year1 and Dec 31 of year2.
  - Loop through each year and add 365 or 366 depending on leap year.


The program should also include a class named Date. The date should be printed in month/day/year format if the print() function is used. This class encapsulates a single date and supports useful methods like formatting, calculating days passed in the year, and operator overloading to subtract or add dates and integers

The Class should include the following methods:

- __str__()
  - Format as "mm/dd/yyyy" using 2-digit padding.

- DaysPassed()
  - Total number of days from Jan 1 up to but not including the current date.

- DaysLeft()
  - Total number of days from this date through Dec 31, including this day.

- __sub__() method
  - If the operand is another Date, compute the number of days between them.
  - If the operand is an int, return a new Date that many days earlier.

- __add__() method
  - Return a new Date that many days later.


# Discussion Questions
What happens when dates cross over years?

In what scenarios do leap years matter?

Do you see a general algorithm that makes use of these methods and functions to solve the problem?

```
In general
starting from the earliest date
get the days left
accumulate the number of days in the years between the start and end year
add the days passed for the end date
```

Are there edge cases? What if dates are in the same year?



```python
# Here's a description of all thats needed based on the problem statement
# My algorithm including function stubs
def IsLeapYear(year):
  # Given a year as an integer
  # Return True or False
  pass
def DaysInMonth(month, year):
  # Given the month and year as integers
  # Return the number of days in that year as an integer
  pass
def DaysBetweenYears(year1, year2):
  # Given 2 specific years as integers
  # Return the amount of days between Year1 and Year2
  # From Jan1 of the earlier year to Dec31 of the later year
  pass
class Date:
  def __init__(self, month, day, year):
    # store the month day and year
    pass
  def __str__(self):
    # return a string in the month(2-digits)/day(2-digits)/year(4-digits) format
    pass
  def DaysPassed(self):
    # return the integer day from Jan 1 of the same year not including the current date
    pass
  def DaysLeft(self):
    # return the amount of days from this date to Dec 31 of the same year including this date.
    pass
  def __sub__(self, other):
    # Given another Date Object
    # Return an integer which represents the number of days between both dates.

    # Given an integer n
    # Return a new Date Object which represents the date n days before this date
    pass
  def __add__(self, other):
    # Given an integer n
    # Return a new Date Object which represents the date n days after this date
    pass

```

#Algoirthm for overriding  ```__sub__()```
d1 - d2, where d1 and d2 are date objects using the class above
```
# the algorith for Date.__sub__() given another Date

# Decide which is earlier (d1 or d2)
# assign earlier to dayA and later to dayB
# difference is dayA.DaysLeft() + dabB.DaysPassed()+ DaysBetweenYears(dayA.year + 1, dayB.year - 1)
```


Complete Code below


```python
def IsLeapYear(year):
    return (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)

def DaysInMonth(month, year):
    if month == 2:
        return 29 if IsLeapYear(year) else 28
    elif month in [1,3,5,7,8,10,12]:
        return 31
    else:
        return 30

def DaysBetweenYears(year1, year2):
    total = 0
    for y in range(min(year1, year2), max(year1, year2)):
        total += 366 if IsLeapYear(y) else 365
    return total

class Date:
    def __init__(self, month, day, year):
        self.month = month
        self.day = day
        self.year = year

    def __str__(self):
        return f"{self.month:02d}/{self.day:02d}/{self.year:04d}"

    def DaysPassed(self):
        total = 0
        for m in range(1, self.month):
            total += DaysInMonth(m, self.year)
        total += self.day - 1
        return total

    def DaysLeft(self):
        total = 0
        for m in range(self.month, 13):
            total += DaysInMonth(m, self.year)
        total -= (self.day - 1)
        return total

    def __sub__(self, other):
        if isinstance(other, Date):
          if (self.year, self.month, self.day) == (other.year, other.month, other.day):
              return 0
          if (self.year, self.month, self.day) < (other.year, other.month, other.day):
            start, end = [self, other]
          else:
            start, end = [other, self]
          if start.year == end.year:
              return end.DaysPassed() - start.DaysPassed()
          days = start.DaysLeft() + end.DaysPassed() + DaysBetweenYears(start.year + 1, end.year)
          return days
        elif isinstance(other, int):
            return self.__add__(-other)

    def __add__(self, other):
        if isinstance(other, int):
          m, d, y = self.month, self.day, self.year
          d += other
          while d > DaysInMonth(m, y):
              d -= DaysInMonth(m, y)
              m += 1
              if m > 12:
                  m = 1
                  y += 1
          while d <= 0:
              m -= 1
              if m < 1:
                  m = 12
                  y -= 1
              d += DaysInMonth(m, y)
          return Date(m, d, y)

if __name__ == "__main__":
  d1 = Date(12, 25, 2009)
  d2 = Date(3, 25, 2024)
  print("d1:", d1)
  print("d2:", d2)
  print("Days between:", d2 - d1)  # Should print 5204

  print("d2 - 5:", d2 - 5)
  print("d1 + 3:", d1 + 3)

  print("Running Date class tests...")

  # Basic formatting
  d1 = Date(12, 25, 2009)
  d2 = Date(3, 25, 2024)
  assert str(d1) == "12/25/2009"
  assert str(d2) == "03/25/2024"

  # DaysPassed and DaysLeft
  assert d1.DaysPassed() == sum([DaysInMonth(m, 2009) for m in range(1, 12)]) + 24
  assert d1.DaysLeft() == 7  # Dec 25 to Dec 31 inclusive
  assert d2.DaysPassed() == sum([DaysInMonth(m, 2024) for m in range(1, 3)]) + 24
  assert d2.DaysLeft() == 282  # March 25 to Dec 31 inclusive

  # Subtracting same date should be 0
  #assert (d1 - d1) == 0
  #assert (d2 - d2) == 0

  # Days between known values
  assert (d2 - d1) == 5204
  assert (d1 - d2) == 5204

  # Leap year handling
  assert IsLeapYear(2000) == True
  assert IsLeapYear(1900) == False
  assert IsLeapYear(2024) == True
  assert DaysInMonth(2, 2024) == 29
  assert DaysInMonth(2, 2023) == 28

  # Adding and subtracting days
  assert str(d2 - 5) == "03/20/2024"
  assert str(d1 + 3) == "12/28/2009"

  # Crossing a year boundary
  d3 = Date(12, 31, 2023)
  assert str(d3 + 1) == "01/01/2024"
  assert str(d3 - 1) == "12/30/2023"

  # Crossing a leap year boundary
  d4 = Date(2, 28, 2020)
  assert str(d4 + 1) == "02/29/2020"
  assert str(d4 + 2) == "03/01/2020"

  # Backward leap year
  d5 = Date(3, 1, 2020)
  assert str(d5 - 1) == "02/29/2020"
  assert str(d5 - 2) == "02/28/2020"

  # Long-range subtraction
  d6 = Date(1, 1, 1900)
  d7 = Date(1, 1, 2000)
  assert (d7 - d6) == 36524  # 100 years, including leap years

  print("All tests passed!")


```

    d1: 12/25/2009
    d2: 03/25/2024
    Days between: 5204
    d2 - 5: 03/20/2024
    d1 + 3: 12/28/2009
    Running Date class tests...
    All tests passed!

