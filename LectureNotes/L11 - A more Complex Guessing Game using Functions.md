Review from last Lecture.



```python
import random
def ListMax(lst):
  # take the first value
  # set it equal to max
  result = lst[0]
  # iterate through the rest of values (or all)
  for i in range(1, len(lst)):
    # if the new value is greater than the max
    if result < lst[i]:
      # set the new max
      result = lst[i]
    #otherwise
      # check the next value
  return result

if __name__ == '__main__':
  print(max([1,2,3]))
  print(ListMax([1,2,3]))
  correct = 0
  for i in range(100):
    rand_list = []
    rand_length = random.randint(1,100)
    for i in range(rand_length):
      rand_list.append(random.randint(1, 10000))
    if max(rand_list) == ListMax(rand_list):
      correct += 1
      print(f'{correct}/100', end='\r')
```

    3
    3
    1/1002/1003/1004/1005/1006/1007/1008/1009/10010/10011/10012/10013/10014/10015/10016/10017/10018/10019/10020/10021/10022/10023/10024/10025/10026/10027/10028/10029/10030/10031/10032/10033/10034/10035/10036/10037/10038/10039/10040/10041/10042/10043/10044/10045/10046/10047/10048/10049/10050/10051/10052/10053/10054/10055/10056/10057/10058/10059/10060/10061/10062/10063/10064/10065/10066/10067/10068/10069/10070/10071/10072/10073/10074/10075/10076/10077/10078/10079/10080/10081/10082/10083/10084/10085/10086/10087/10088/10089/10090/10091/10092/10093/10094/10095/10096/10097/10098/10099/100100/100

# A review of our Generic Guessing game.

Build a Guessing game. When the program starts the user will be given 3 chances to guess the random number generated between 1 and 100. If the user guesses wrong, print the hint 'too high' or 'too low'.




```python
import random
# generate a random number between 1 and 100 - answer
answer = random.randint(1,100)
#print('debug:', answer)
# assume the user has lost
didWin = False
# iterate the following 3 times
for i in range(3):
  # get a guess from the user
  guess = int(input('Enter your Guess: '))
  # if the guess is wrong
    # display a hint (too high, or too low)
  if guess > answer:
    print('too high.')
  elif guess < answer:
    print('too low')
  # otherwise user wins
  else:
    #display winner
    print('winner!')
    didWin = True
    break;
# display 'you lose!
if not didWin:
  print('you lose!')

```

# A more complex Guessing game with use of functions



```python
# Example NotImplementedError

import random
def GetRandomIntBetween(start,stop):
  #pass
  raise NotImplementedError
def TestGuess(answer):
  # given the answer
  # take the guess as an input
  # return a string to print to the screen.
  # return too high!, too low!, or winner!
  raise NotImplementedError
def RunGame(guesses):
  # this handles a single game loop
  # given the number of guesses runs the game
  # returns True if the user wins. Otherwise returns False
  raise NotImplementedError
def Continue():
  # prompts the user to enter "yes" or "no".
  # if the input is not "yes" or "no", then keep asking until the user enters
  # either "yes" or "no"
  # Returns True if the user enters "yes" and False if the user enters "no"
  raise NotImplementedError

if __name__ == '__main__':
  result = RunGame(3)
  willCon = Continue()
  # while the user wants to continue:
  while willCon:
    # play the game
    result = RunGame(3)
    # does the user want to continue
    willCon = Continue()

```


```python
import random
def GetRandomIntBetween(start,stop):
  # returns a random number between start and stop
  return random.randint(start, stop)
def TestGuess(answer):
  # given the answer
  # take the guess as an input
  # return a string to print to the screen.
  guess = int(input('Enter a Guess between 1 and 100'))
  if guess > answer:
    return 'too high!'
  elif guess < answer:
    return 'too low!'
  else:
    return 'Winner!'
def RunGame(guesses):
  # given the number of attempts (guesses)
  # this handles the main game loop
  # returns True if the user wins. Otherwise returns flase

  #generate a random number between 1 and 100
  answer = GetRandomIntBetween(1,100)
  # loop the number of guesses
  for i in range(guesses):
    #check a users guess
    result = TestGuess(answer)
    print('debug: answer =', answer)
    # if they win
    if result == 'Winner!':
      print(result)
      return True
    # if they guess wrong
    else:
      # print a hint
      print(result)
  return False
def Continue():
  # if the the user enters yes return True. False for no.
  # continue asking for a "yes" or "no" if neither is inputted
  yn = input('Do you want to Play again."yes" or "no"')
  while yn !='yes' and yn !='no':
    yn = input("Please Enter yes/no")
  if yn =='yes':
    return True
  return False
if __name__ == '__main__':
  result = RunGame(3)
  willCon = Continue()
  # while the user wants to continue:
  while willCon:
    # play the game
    result = RunGame(3)
    # does the user want to continue
    willCon = Continue()





```

    Enter a Guess between 1 and 1000
    debug: answer = 62
    too low!
    Enter a Guess between 1 and 100100
    debug: answer = 62
    too high!
    Enter a Guess between 1 and 10062
    debug: answer = 62
    Winner!
    Do you want to Play again."yes" or "no"no


# Preparing For Midterm 1:
If there is extra time this lecture, I will move on to Lecture 12. Both Lecture 12 and Lecture 13 contain practice problems taken from online sources like leetcode and codewars.

- Midterm 1 covers Chapter 2 through Chapter 6.
- There are additional Practice Problems in the Textbook
- Lectures 12 and 13 contain additional Practice Problems
- We wil do a Mini Mock Exam so students can be familiar with which problems are assigned to you. This will likely take place sometime during the next two lectures





