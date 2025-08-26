# First Iteration - text based
- Build a game
  - The gameboard will 10 by 10 squares
  - the user starts at a random postion
  - the user can use w,a,s,d to move. They cannot move outside game board.
  - a random postion in the board is selected to be the goal
  - the user can't see the goal
  - When the user finds the goal they win.


```python
# Build a game
# The gameboard will 10 by 10 squares
# the user starts at a random postion
# the user can use w,a,s,d to move. They cannot move outside game board.
# a random postion in the board is selected to be the goal
# the user can't see the goal
# When the user finds the goal they win.

import random
# randomly initialize the player
px = random.randint(0,9)
py = random.randint(0,9)
# randomly initialize the goal
gx = random.randint(0,9)
gy = random.randint(0,9)
print(gx, gy)
# while their postions are different
# while not(px == gx and py == gy)
while px != gx or py != gy:
    # let the user move
    move = input('Please Move!:\n')
    if not(move in 'wasd'):
        print('invalid move')
        continue
    if move == 'w':
        if py < 9:
            py += 1
    elif move  == 'a':
        if px > 0:
            px -= 1
    elif move  == 's':
        if py > 0:
            py -= 1
    elif move  == 'd':
        if px < 9:
            px += 1
    print(f'Player is at {px},{py}')

# player wins
print("win")
```

    3 1
    Please Move!:
    w
    Player is at 3,3
    Please Move!:
    w
    Player is at 3,4
    Please Move!:
    s
    Player is at 3,3
    Please Move!:
    s
    Player is at 3,2
    Please Move!:
    s
    Player is at 3,1
    win


# Next Iteration - Turn the Player into a class
This isn't really a great use of classes because there is only 1 player
But it will help understand classes.



```python
# Same Game. make the player a class.

import random
class Player:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def Move(self,move):
        if not(move in 'wasd'):
            print('invalid move')
        if move == 'w':
            if self.y < 9:
                self.y += 1
        elif move  == 'a':
            if self.x > 0:
                self.x -= 1
        elif move  == 's':
            if self.y > 0:
                self.y -= 1
        elif move  == 'd':
            if self.x < 9:
                self.x += 1


# randomly initialize the player
player = Player(random.randint(0,9),random.randint(0,9))
# randomly initialize the goal
gx = random.randint(0,9)
gy = random.randint(0,9)
print(gx, gy)
# while their postions are different
# while not(px == gx and py == gy)
while player.x != gx or player.y != gy:
    # let the user move
    move = input('Please Move!:\n')
    player.Move(move)
    print(f'Player is at {player.x},{player.y}')
# player wins
print("win")
```

    2 5
    Please Move!:
    w
    Player is at 7,9
    Please Move!:
    a
    Player is at 6,9
    Please Move!:
    a
    Player is at 5,9
    Please Move!:
    a
    Player is at 4,9
    Please Move!:
    a
    Player is at 3,9
    Please Move!:
    a
    Player is at 2,9
    Please Move!:
    w
    Player is at 2,9
    Please Move!:
    w
    Player is at 2,9
    Please Move!:
    s
    Player is at 2,8
    Please Move!:
    s
    Player is at 2,7
    Please Move!:
    s
    Player is at 2,6
    Please Move!:
    s
    Player is at 2,5
    win


# Let's try make a graphical game and adapt our code
We will use z.shocode.com



```python
import random
### RECTANGLES ###
# Rect(x, y, width, height, rotation, fillColor, borderColor)
# x,y - center # rotation - degrees rotate clockwise. #optional - rotation, fillColor, borderColor

### Circles ###
# Circle(x, y, radius, rotation, fillColor, borderColor, degrees)
# x,y - center. # optional-fillColor, borderColor, degrees

database.state = 0 # 0 -  waiting to play. press s to start
          # 1 - game is playing


class Player:
    def __init__(self, x, y, color):
        self.object=Circle(x,y, 10,0, color, None,360)

    def Move(self,move):
        print('in Move', move)
        if not(move in 'wasdijkl'):
            print('invalid move')
        if move in 'wi':
            if self.object.y < 380:
                self.object.y += 40
        elif move  in 'aj':
            if self.object.x > 20:
                self.object.x -= 40
        elif move  in 'sk':
            if self.object.y > 20:
                self.object.y -= 40
        elif move  in 'dl':
            if self.object.x < 380:
                self.object.x += 40


# create the player
p1 = Player(20,20, 'green')
p2 = Player(380,20, 'blue')

# creat the goal
gx = 20 + random.randint(0,9)*40
gy = 20 + random.randint(0,9)*40
goal = Circle(gx,gy, 10,0, 'red', None,360)


# drawing grid lines
for i in range(9):
    Rect(40*(i+1),200, 1, 400,0,'black')
for i in range(9):
    Rect(200,40*(i+1), 1, 400, 90, 'blue')

def OnKey(key):
    print(key)
    if database.state == 0 and key == 's':
        p1.object.x = 20 + random.randint(0,9)*40
        p1.object.y = 20 + random.randint(0,9)*40
        p2.object.x = 20 + random.randint(0,9)*40
        p2.object.y = 20 + random.randint(0,9)*40
        goal.x = 20 + random.randint(0,9)*40
        goal.y = 20 + random.randint(0,9)*40
        database.state = 1
    if database.state == 1:
        if key in 'wasd':
            p1.Move(key)
        if key in 'ijkl':
            p2.Move(key)
        if p1.object.x == goal.x and p1.object.y == goal.y:
            print('player 1 wins')
            database.state = 0
        if p2.object.x == goal.x and p2.object.y == goal.y:
            print('player 2 wins')
            database.state = 0


```


```python

```
