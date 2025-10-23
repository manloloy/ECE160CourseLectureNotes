# A simple graphical example using classes
For this example, we used z.shocode.com
Here we use composition to build a MyCircle Class. We start by initially using an existing class named Circle(). this class draws a circle with given parameters and has members and methods.
We also made use of the a special function called OnFrameUpdate() which runs as many frames per second.
```python
import random as r

class MyCircle:
    def __init__(self):
        colors = ['red', 'green', 'blue', 'yellow', 'black', 'brown']
        
        # Circle(x, y, radius, rotation, fillColor, borderColor, degrees)
        # x,y - center. # optional-fillColor, borderColor, degrees
        self.circle = Circle(r.randint(5,395), r.randint(5,395), r.randint(5,20), 0, colors[r.randint(0,len(colors)-1)], None, 360)
        self.speed = r.randint(1,10)
        xdir = r.gauss(0,1)
        ydir = r.gauss(0,1)
        magnitude = (xdir**2 + ydir**2)**0.5
        self.xdir = xdir/magnitude
        self.ydir = ydir/magnitude
    def Move(self):
        self.circle.x += self.xdir * self.speed
        self.circle.y += self.ydir * self.speed
        if self.circle.x < (0 + self.circle.radius):
            self.circle.x = 0 + self.circle.radius
            self.xdir *= -1
        if self.circle.x > (400 - self.circle.radius):
            self.circle.x = 400 - self.circle.radius
            self.xdir *= -1
        if self.circle.y < (0 + self.circle.radius): 
            self.circle.y = 0 + self.circle.radius
            self.ydir *= -1
        if self.circle.y > (400 - self.circle.radius):
            self.circle.y = 400 - self.circle.radius
            self.ydir *= -1
            
circles = [MyCircle() for i in range(30)]


def OnFrameUpdate():
    for c in circles:
        c.Move()
```
