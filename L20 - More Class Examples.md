# More Classes and Examples

# Using classes to implement an airline seat reservation system.

The following example implements an airline seat reservations system using classes with instance data members and methods. Ultimately, the use of classes should lead to programs that are easier to understand and maintain.


```python
class Seat:
    def __init__(self):
        self.first_name = ''
        self.last_name = ''
        self.paid = 0.0

    def reserve(self, f_name, l_name, amt_paid):
        self.first_name = f_name
        self.last_name = l_name
        self.paid = amt_paid

    def make_empty(self):
        self.first_name = ''
        self.last_name = ''
        self.paid = 0.0

    def is_empty(self):
        return self.first_name == ''

    def print_seat(self):
        print(f'{self.first_name} {self.last_name}, Paid: {self.paid:.2f}')
# functions that can be used
def make_seats_empty(seats):
  # given a list of seats
  # returns nothing but makes all seats in a list emptpy
    for s in seats:
        s.make_empty()

def print_seats(seats):
    for i in range(len(seats)):
        print(f'{i}:', end=' ')
        seats[i].print_seat()

if __name__ == '__main__':
  num_seats = 5

  available_seats = []
  for i in range(num_seats):
    available_seats.append(Seat()) # s1 = Seat(); available_seats.append(s1)

  command = input('Enter command (p/r/c/q):\n')
  while command != 'q':
    if command == 'p':  # Print seats
        print_seats(available_seats)

    elif command == 'r':  # Reserve a seat
        seat_num = int(input('Enter seat num for reservation:\n'))
        if not available_seats[seat_num].is_empty():
            print('Seat not empty')
        else:
            fname = input('Enter first name:\n')
            lname = input('Enter last name:\n')
            paid = float(input('Enter amount paid:\n'))
            available_seats[seat_num].reserve(fname, lname, paid)
    elif command == 'c':  # Cancel A Reservation
          seat_num = int(input('Enter seat num for cancellation :\n'))
          available_seats[seat_num].make_empty()
    else:
        print('Invalid command.')

    command = input('Enter command (p/r/c/q):\n')



```

    Enter command (p/r/c/q):
    r
    Enter seat num for reservation:
    3
    Enter first name:
    Chris
    Enter last name:
    M
    Enter amount paid:
    1000000
    Enter command (p/r/c/q):
    p
    0:  , Paid: 0.00
    1:  , Paid: 0.00
    2:  , Paid: 0.00
    3: Chris M, Paid: 1000000.00
    4:  , Paid: 0.00
    Enter command (p/r/c/q):
    r
    Enter seat num for reservation:
    3
    Seat not empty
    Enter command (p/r/c/q):
    r
    Enter seat num for reservation:
    0
    Enter first name:
    david
    Enter last name:
    M
    Enter amount paid:
    1
    Enter command (p/r/c/q):
    p
    0: david M, Paid: 1.00
    1:  , Paid: 0.00
    2:  , Paid: 0.00
    3: Chris M, Paid: 1000000.00
    4:  , Paid: 0.00
    Enter command (p/r/c/q):
    c
    Enter seat num for cancellation :
    3
    Enter command (p/r/c/q):
    p
    0: david M, Paid: 1.00
    1:  , Paid: 0.00
    2:  , Paid: 0.00
    3:  , Paid: 0.00
    4:  , Paid: 0.00
    Enter command (p/r/c/q):
    q


# A Product Class
In main.py define the Product class that will manage product inventory. Product class has three attributes: a product code, the product's price, and the number count of product in inventory.

Implement the following methods:

- A constructor with 3 parameters that sets all 3 attributes to the value in the 3 parameters
- set_code(self, code) - set the product code (i.e. SKU234) to parameter code
- get_code(self) - return the product code
- set_price(self, price) - set the price to parameter price
- get_price(self) - return the price
- set_count(self, count) - set the number of items in inventory to parameter count
- get_count(self) - return the count
- add_inventory(self, amt) - increase inventory by parameter amt
- sell_inventory(self, amt) - decrease inventory by parameter amt

Ex. If a new Product object is created with code set to "Apple", price set to 0.40, and the count set to 3, the output is:
```
Name: Apple
Price: 0.40
Count: 3
```
Ex. If 10 apples are added to the Product object's inventory, but then 5 are sold, the output is:
```
Name: Apple
Price: 0.40
Count: 8
```
Ex. If the Product object's code is set to "Golden Delicious", price is set to 0.55, and count is set to 4, the output is:

Name: Golden Delicious
Price: 0.55
Count: 4


```python
class Product:
    def __init__(self, code, price, count):
        self.code = code
        self.price = price
        self.count = count

    def set_code(self, code):
        self.code = code

    def get_code(self):
        return self.code

    def set_price(self, price):
        self.price = price

    def get_price(self):
        return self.price

    def set_count(self, count):
        self.count = count

    def get_count(self):
        return self.count

    def add_inventory(self, amt):
        self.count += amt

    def sell_inventory(self, amt):
        self.count -= amt

if __name__ == "__main__":
    name = 'Apple'
    price = 0.40
    num = 3
    p = Product(name, price, num)

    # Test 1 - Are instance attributes set/returned properly?
    print(f'Name: { p.get_code() }')
    print(f'Price: {p.get_price():.2f}')
    print(f'Count: { p.get_count() }')

    # Test 2 - Are attributes set/returned properly after adding and selling?
    num = 10
    p.add_inventory(num)
    num = 5
    p.sell_inventory(num)
    print(f'Name: { p.get_code() }')
    print(f'Price: {p.get_price():.2f}')
    print(f'Count: { p.get_count() }')

    # Test 3 - Do setters work properly?
    name = 'Golden Delicious'
    p.set_code(name)
    price = 0.55
    p.set_price(price)
    num = 4
    p.set_count(num)
    print(f'Name: { p.get_code() }')
    print(f'Price: {p.get_price():.2f}')
    print(f'Count: { p.get_count() }')

    # Test 4
    products = [Product('apple', 0.4, 8), Product('pear', 0.5, 10), Product('mango', .8, 4), Product('Avocado', 1.2, 1)]
    for p in products:
      print(p.get_code(), p.get_count())

```

    Name: Apple
    Price: 0.40
    Count: 3
    Name: Apple
    Price: 0.40
    Count: 8
    Name: Golden Delicious
    Price: 0.55
    Count: 4
    apple 8
    pear 10
    mango 4
    Avocado 1


# Student Class
In main.py define the Student class that has two attributes: name and gpa

Implement the following instance methods:

- A constructor that sets name to "Louie" and gpa to 1.0
- set_name(self, name) - set student's name to parameter name
- get_name(self) - return student's name
- set_gpa(self, gpa) - set student's gpa to parameter gpa
- get_gpa(self) - return student's gpa

Ex. If a new Student object is created, the default output is:
```
Louie / 1.0
```
Ex. If the student's name is set to "Felix" and the gpa is set to 3.7, the output becomes:
```
Felix / 3.7
```


```python
class Student:
    def __init__(self):
        self.name = "Louie"
        self.gpa = 1.0

    def set_name(self, name):
        self.name = name

    def get_name(self):
        return self.name

    def set_gpa(self, gpa):
        self.gpa = gpa

    def get_gpa(self):
        return self.gpa

if __name__ == "__main__":
    initial_student = Student()
    print(f'{ initial_student.get_name() } / { initial_student.get_gpa() }')

    initial_student.set_name('Felix')
    initial_student.set_gpa(3.7)
    print(f'{ initial_student.get_name() } / { initial_student.get_gpa() }')
```

    Louie / 1.0
    Felix / 3.7


# Print Student Roster
Complete the Course class by implementing the print_roster() instance method, which outputs a list of all students enrolled in a course and also the total number of students in the course.

Given the following:
- The main function for testing the program.
- Class Course represents a course, which contains a list of Student objects as a course roster. (Type your code in here.)
- Class Student represents a classroom student, which has three attributes: first name, last name, and GPA.

Ex: If the program has 4 students enrolled in the course, the output looks like:
```
Henry Cabot ( GPA: 3.5 )
Brenda Stern ( GPA: 2.0 )
Jane Flynn ( GPA: 3.9 )
Lynda Robison ( GPA: 3.2 )
Students: 4
```


```python
class Student:
    def __init__(self, first, last, gpa):
        self.first = first # first name
        self.last = last   # last name
        self.gpa = gpa     # grade point average

    def get_gpa(self):
        return self.gpa

    def get_last(self):
        return self.last

class Course:
    def __init__(self):
        self.roster = []  # list of Student objects

    def add_student(self, student):
        self.roster.append(student)

    def course_size(self):
        return len(self.roster)

    # Outputs each student in the course roster, and then the total size of the course
    def print_roster(self):
        for student in self.roster:
            print(f'{ student.first } { student.last } ( GPA: { student.gpa } )')
        # print total number of students in the course
        print(f'Students: { len(self.roster) }')

if __name__ == "__main__":
    course = Course()
    course.add_student(Student('Henry', 'Cabot', 3.5))
    course.add_student(Student('Brenda', 'Stern', 2.0))
    course.add_student(Student('Jane', 'Flynn', 3.9))
    course.add_student(Student('Lynda', 'Robison', 3.2))

    course.print_roster()
```
