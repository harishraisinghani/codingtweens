# Intro to Python - Session 4

### Setup
* Open up the `RockPaperScissors` repl from last class.
* We will also have a few assignments for this class

### Rock-Paper-Scissors app improvements

> Run the app from last time to check were we left off.

> Now carry out exercises 5-7 to add a few more features to the app. 

### While Loops

https://www.w3schools.com/python/python_while_loops.asp

### 'Longest Name Calculator' exercise
See Repl

### 'Roll the Dice' game
See Repl


# Python Coding Series Recap

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

#### Variables

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


