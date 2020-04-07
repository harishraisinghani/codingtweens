# Python Coding Series Recap

It is recommended you go through this code using a cloud based code editor. For example, simply go to https://repl.it and create a new **Python** Repl. 

### Commands and instructions
Let us look at our sample starting code:
```
print('Hello world')
print(2020)
```

* On the first line, `print()` is the **command** and `'Hello world'` is the `instruction` given to the `print()` command.

* On the second line, `print()` is the command and `2020` is the instruction.

* Anything inside of the *single or double quotes* is called a **string**. The `'Hello world'` instruction is an example of a string.

* Whole numbers in Python, like `123456789` are simply called **integers**.

* Commands in Python ends with the round brackets or parentheses  - `()` 
* Commands do NOT have to have instructions passed inside the round brackets. 
* The `print()` command is one of the most popular commands in Python because it allows you to see the output of your code. 

* Anything after a hashtag (`#`) is greyed out because it is called a **comment**.  

* Comments are not run by Python, and are used to share information with other humans. You can add or remove the hashtag from the line to activate or deactivate any following code.

Some useful, built-in Python commands we covered in this series:

* `print('Hello')`
* `input('What is your name?')`
* `type(45)`

### Variables

A variable is just a label for a container holding some value. It can be empty or contain a string, integer or some other Python data. 

For example:
```
some_variable = 'This is a variable string because this text is surrounded by quotes'

other_variable = 6
```

* Note the variable name - it is NOT in quotes
* The variable name goes on the **left side** of the equals (`=`) sign and the value assigned to that variable name goes on the **right side** of the equals (`=`) sign. 

* The convention in Python is to use all lowercase when creating your variable names. 

### Flow control

Flow control means allowing Python to decide which code to run and which code to skip depending on conditions. 

We looked at the following flow control elements in Python:
1. Basic loops: `for` and `while` loops
2. `If/elif/else` statements

#### `for` loops

`for` loops have the structure:

```
for <each item> in <some group of items>:
    <do something>
```

For example:
```
for i in range(4):
    print(i)

Output: >>>
0
1
2
3
```
```
my_friends = ['Alpha', 'Bravo', 'Charlie']

for friend in my_friends:
    print(friend)

Output: >>>
'Alpha'
'Bravo'
'Charlie'
```

#### `while` loops
`while` loops have the structure:

```
while <some condition is True>:
    <do something>
```
For example:
```
i = 1
while i < 6:
  print(i)
  i = i + 1

Output: >>>
1
2
3
4
5
```

#### `if/elif/else`

Another type of flow control is with `if/elif/else` statements which look something like this:
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
* `elif` is shorthand for `else if`
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


### The `random` software package

In Python, there is a built-in software package called `random` which allows Python to randomly select things for us. To use this software package, just like with the `turtle` blueprint, we need to first `import` it:

```
import random
```

Now we have a variable called `random` we can use. A popular command that `random` has to offer is called `choice()` which takes in a list as the argument:
```
random.choice(<some list>)

words_list = ['Hello', 'my', 'name', 'is', 'Aaliyah']
word = random.choice(words_list)
print(word)
```
> Run this a few times to confirm you are getting randomly selected words.

We can also have the computer randomly select an integer between a range we provide using the `randint()` command which takes 2 arguments - the start and end of the selection range:

```
num = random.randint(10,100)
print(num)
```

### Lists

Lists are defined by `[ ]` which each item inside the list separated by commas. Lists can contain integers, strings or even other lists!

Lists are 0 indexed so we say the first item in a list has an index 0, or a pointer reference of 0. **This is how we find stuff in a list!**

To get the first item in a list, use `my_list[0]`

Python has a built-in command to get the length of a list, called `len()`. Simply pass in the name of the list inside the `len()` command to get the total number of items because the number of items can be very large. 

To get the very last item in a list, you can do one of two things:

1. Use the length of the list:
```
length = len(my_list)
last_item = my_list[length-1]
```
or 

2. Simply use the index `-1`:
```
my_list[-1]
```

To add a single item to a list, simply use the `append()` command:
```
<name of list>.append(<item to add>)

my_list.append(12)
```

And similarly, you can remove items from the list with the `remove()` command:
```
my_list.remove(12)
```
For more info on **list related commands**, see https://docs.python.org/3.8/tutorial/datastructures.html

### Rock-Paper-Scissors App
Sample working code:
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

### Links to coding resources

* Our **repl.it classroom** with all the exercises: https://repl.it/student/classrooms/180990

* **Turtles documentation**: https://docs.python.org/3.3/library/turtle.html?highlight=turtle#turtle-methods

* **Codeacademy**: - https://www.codecademy.com/courses/learn-python/lessons/python-syntax

* **Beginner Python games**: - https://www.pythonforbeginners.com/games/
