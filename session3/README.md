# Intro to Python - Session 3

Goals for this workshop:
* Review last session including: 
  * `print()`, `input()`, `random`
  * Python lists
  * `for` loops

* `if/elif/else` flow control
* Rock-paper-scissors app

### Setup
* Ensure you have linked the 2 new project repls:
  * `YourNameLengthCalc`
  * `RockPaperScissors`
* Open up the `Python Basics` repl from last class. 

### Review

In the `Python Basics` repl, there are 6 mini exercises to complete which cover what we went through last session.

Questions:
* Q) `input()` and `print()` are examples of what type of objects in Python? How do we know these are examples of commands?

* Q) words displayed in black are containers for some value. What do we call containers in Python?

* Q) The text in grey represents what? How do we create comments?

* Q) What type of brackets do we use to define lists in Python?

* Q) What index to list's start with. So for example, what index would you use to get the first item in a list?

> Answer the 7 questions by doing the following:
* Replace `<code>` with your code
* Uncomment (i.e. remove the `#` symbol) in front of the code which you want to run

### `if/else` flow control

We used `for` loops as a way to do something over and over again multiple times quickly without having to repeat code. Loops are an example of flow control because they help us control how the program runs by making some decisions (such as run over and over).

Another type of flow control is with `if/else` statements which sounds something like this:
```
if <some condition>:
    //do this
elif <some condition>:
    //do that
else:
    //do something if all else fails
```
Few things to note:
* Each of `if`, `elif`, `else` ends with a colon which tells Python the code on the next line is under this header
* Indentations after each of line of code
* `elif` is shorthand for `else-if`
* `else` does NOT have a condition because it is a catch all for everything else

Example:
```
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

You can also check if an item is in a list with:
```
if 'Mom' in my_friends:
    print('Mom is in my friends list')
else:
    print('Mom is not in my friends list')
```

##### Exercise - Name Length Calculator

> Open up the `YourNameLengthCalc` repl and follow the instructions to build this app.


### Rock-Paper-Scissors App

> Open up the `RockPaperScissors` repl and follow the instructions to build this app.

Additional exercises with `Rock-Paper-Scissors` App:

1. How can I check if the player's move is an approved move?
1. What additional `if/elif` check can I add if I want to allow the player to quit the game by pressing the letter `q`?

1. How can I run the game continuously so that it keeps running and only breaks if the player presses the letter `q`?

Sample code:
```
import random

player_score = 0
computer_score = 0
ties_score = 0
allowed_moves = ['r', 'p', 's']
winning_moves = ['pr', 'sp', 'rs']

while True:
    player_move = input("What is your move?")
    computer_move = random.choice(allowed_moves)
    print('Your move', player_move)
    print('Computer move', computer_move)

    if player_move == 'q':
        break
    elif player_move == computer_move:
        print("Tie")
        ties_score += 1
    elif player_move + computer_move in winning_moves:
        print("You Win!")
        player_score += 1
    else:
        print("You Lose!")
        computer_score += 1
    print('Current Score: Player - ', player_score, 'Computer:', computer_score, 'Ties:', ties_score)
```