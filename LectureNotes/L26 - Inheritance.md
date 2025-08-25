# Inheritance

Inheritance deals classes. Classes can inherit methods and variables from other classes.

This is normally refered to as an "is-a" relationship.

- "has-a" relationship
  - Car is a class. It has internally other classes like tires, an engine, wheels.
- "is-a" relationship (Inheritance)
  - Shape is a class. A circle is a shape and a rectangle is a shape
### "has-a" - Composition
- Think of this as nested classses
- These are classes with variables that are other classes

Example:
We have the following classes
- wheel
- cylinder ( a part of a reciprocating engine)
- engine
- car

```
class engine:
  ...
  self.numOfCylinders = 2
  self.cylinder1 = cylinder()
  self.cylinder2 = cylinder()
  #or
  self.cylinders = [cylinder(), cylinder()]
  ...
  # self.cylinders = [cylinder(), cylinder()]
  # an engine "has-a" cylinder  or many cylinders
class car:
  ...
  self.wheel1 = wheel()
  self.wheel2 = wheel()
  self.wheel3 = wheel()
  self.wheel4 = wheel()
  # or
  self.wheels = [wheel(), wheel(), wheel(), wheel()]
  self.engine = engine()
  ...
  # a car "has-a" wheel(s) and "has-a" engine(s)
```

### "is-a" - Inheritance
We have the following classes:
- Shape
- Circle
- Recangle

A shape could be just something that has a postion and area. Position can be represented the same way amoung all shapes but area is calculated differently.


Both Circle and Rectangle have a position but they are represented in the same manner so why write the same code for multiple classes

```
class Shape:
  ...
  self.x  = 0
  self.y = 0
  def getPos(self):
    # return the position of a shape as a tuple
    return (self.x, self.y)
  ...

# Circle "is-a" shape
class Circle(Shape):
  ...
  self.radius = 0
  def Area(self):
    return 3.14 * (self.radius**2)
  ...

# Rectangle "is-a" shape
class Rectangle(Shape):
  ...
  self.width = 0
  self.height = 0
  def Area(self):
    return self.width * self.height

if __name__ == "__main__":
  r1 = Rectangle()
  c1 = Circle()

  r1.getPos()
  c1.getPos()
  # NOTE: getPos is part of the Shape class
  # but both r1 and c1 inherit from Shape
  # r1 "is-a" rectangle which "is-a" Shape
  # The Shape class is known as the parent class
  # The Rectangle class is known as the child
  # parent is sometimes called base
  # child is soemtimes called derived
```


```python
# Shapes as an example
class Shape:
  def __init__(self, x=0, y=0):
    self.x = x
    self.y = y
    print('A shape was created')
  def getPos(self):
    return (self.x, self.y)
class Rectangle(Shape):
  def __init__(self, width=0, height=0, x=0, y=0):
    self.width = width
    self.height = height
    print('A Rectangle was created')
    super().__init__(x,y)
  def Area(self):
    return self.width * self.height
if __name__ == "__main__":
  r = Rectangle()
  print(r.width, r.height, r.x, r.y)

  r1 = Rectangle(5, 10, 200,200)
  print(r1.width, r1.height, r1.getPos())

  print(r1.Area())
  r1.x = 100
  r1.y = 250
  print(r1.getPos())
```

    A Rectangle was created
    A shape was created
    0 0 0 0
    A Rectangle was created
    A shape was created
    5 10 (200, 200)
    50
    (100, 250)


## Sharing Examples Of My Own Work
