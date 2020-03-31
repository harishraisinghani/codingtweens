# Intro to Python - Session 2

Goals for this workshop:
* Review basics from last session including `for` loops
* Learn about Python lists
* Intro to `random()` software package
* Use the `Turtle` software package to incorporate above learned functions

### Setup
1. Open up the `Python Basics` repl from last class

### Python Basics Review
Our code from last time looks something like:
```
name = input('What is your name? ')
print('Hello ', name)
```

Questions:
* Q) `input()` and `print()` are examples of what type of objects in Python?
* Q) `name` is a container for some value. What do we call containers in Python?
* Q) The text in grey represents what? How do we create comments?

> Change the input to ask for a user's school grade and then print the grade.

Q) Last session we introduced the concept of loops. What are loops?

A) A loop in a program basically tells the computer to run through all the commands in the loop over and over if some condition is met and then until some other condition is met.

Q) What type of loop did we cover in the last session to move our turtle, `larry`, a certain number of times?

In Python, we have many different types of loops. A popular one is called the `for` loop which has a syntax that looks like this:
```
for <each item> in <some group of items>:
    <do something>
```

We used this together with the `range()` command as follows:

> Type the following `for` loop:
```
for i in range(4):
    print(i)
    print('Hello')
```

Q) So what does `range(4)` do? 

Q) What is `i` and how does its value change each time the loop is run? Have a look at the output in the console. Refer to slide.

A question was raised last time about the `range()` command and if it has to start from 0. 

> What if you do the following:
```
for i in range(1,4):
    print(i)
    print('Hello')
```
Q) What are the values of `i` now and why?

> What if you do the following:
```
for i in range(1,4,2):
    print(i)
    print('Hello')
```
Q) What are the values of `i` now and why?

* Remember the indenting on the `for` commend, which tells Python that the following indented commands after the `:` belong to the loop. Otherwise, Python would not know when the loop finishes and the next command starts. 

The `range()` command actually represents a **list** of items, in this case a list of integers. Lists are another type of data object in Python and very useful for containing a collection of Python objects together. **Think of lists as library book shelves containing items**. 

### Lists

Lists are defined by `[ ]` which each item inside the list separated by commas. Lists can contain integers, strings or even other lists!

> In the console, create a list variable called `my_list` and have 4 items (integers or strings) inside of it

Lists are 0 indexed (just like we saw with the `range()` command) so we say the first item in a list has an index 0, or a pointer reference of 0. **This is how we find stuff in a list!**

To get the first item in a list, use `my_list[0]`

> Get the 3rd item in `my_list`

Python has a built-in command to get the length of a list, called `len()`. Simply pass in the name of the list inside the `len()` command to get the total number of items because the number of items can be very large. 

To get the very last item in a list, you can do one of two things:
1. Use the length of the list:
```
length = len(my_list)
last_item = my_list[length-1]
```
2. Simply use the index `-1`:
```
my_list[-1]
```

Exercise:
> You have a list of 4 numbers as follows: `[10,8,7,9]`. Add just the second and third numbers of this list.

> Then add the first and last numbers of the same list.

To add a single item to a list, simply use the `append()` command:
```
<name of list>.append(<item to add>)

my_list.append(12)
```

And similarly, you can remove items from the list with the `remove()` command:
```
my_list.remove(12)
```
Exercise:
> You have a list of 4 numbers as follows: `[10,8,7,9]`. Add the second and third numbers of this list and then add the result, 15, to the end of the list.

> Then remove the `10` from the list.

### Lists and `for` Loops
Recall that we ran this `for` loop before:
```
for i in range(4):
    print(i)
    print('Hello')
```

Well, `range(4)` is just a list equal to `[0,1,2,3]`. In fact, replace it and do the following:
```
for i in [0,1,2,3]:
    print(i)
    print('Hello')
```

So we see that `i` is a variable container for each item in our list `[0,1,2,3]` as we loop through it. But `i` is a variable name we came up with and is completely up to us. For example, if we wanted to use the variable name `item` instead of `i`, then we get:

```
for item in [0,1,2,3]:
    print(item)
    print('Hello')
```

See, `item` is just a variable name and I can call anything I want, and I can refer to that variable name later in my `for` loop.  

> Suppose you have a list of words such as `['Hello', 'my', 'name', 'is', 'Aaliyah']`. Use a `for` loop to go through each word in this list and print it out to the screen. 


### `random`

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

Now we can combine `for` loops with the `random` software package to loop through and have the computer randomly select things for us. 

Exercise:
> Create a `for` loop which runs 4 times using the `range(4)` command, and prints a random number each time it goes through the loop.

> What if I want to add up each of the 4 random numbers together and print the sum after the loop is done. How can I write a simple program to do that?

Now let us go back to our Turtles program from last time and use the power of `for` loops and the `random` software package to create some fun visualizations.

### Turtles

Ensure you have opened the `Intro to Turtle` repl. Note that this repl looks a bit different. There's no File Explorer - just the Code Editor and both a 'result' and 'console' output page. The 'result' tab is where we will see graphical outputs from our Turtle exercise.

Our starting code is:
```
import turtle

larry = turtle.Turtle()

larry.shape('turtle')

larry.color('green')
larry.speed(0)

for i in range(4):
    print(i)
    larry.forward(100)
    larry.left(90)
```
> Any questions with this starting code to create a square?

Now let us use the `random` software package to randomly select the color of larry each time he goes through the loop. 

> Import `random` after the `turtle` import

To start, larry will be 'green'.

> Next, create a `colors` variable with the following colors: `['green', 'blue', 'red', 'yellow']`

> Then, in the `for` loop, after larry has moved forward and left, create a variable called `random_color` which is going to take the value of a random choice from the `colors` list.

> Then apply this `random_color` to `larry`

```
import turtle
import random

larry = turtle.Turtle()

larry.shape('turtle')

larry.color('green')
larry.speed(0)

colors = ['green', 'blue', 'red', 'yellow']

for i in range(4):
    larry.forward(100)
    larry.left(90)

    random_color = random.choice(colors)
    larry.color(random_color)
```

> Now, let us move larry forward a variable distance based on the value of `10*i` (like we did last class) and change the range from 4 to 32.

> What about something like this using circles:
```
for i in range(100):
  larry.circle(i*3)
  larry.left(10)

  random_color = random.choice(colors)
  larry.color(random_color)
```

> What does the argument inside the `circle` command represent again? The radius of a circle or the diameter?

> Use the `random.randint(a,b)` command to randomly select a circle radius between 10 and 100 and apply that to the `for` loop above. 

```
for i in range(100):
  radius = random.randint(10,100)
  larry.circle(radius)
  larry.left(10)

  random_color = random.choice(colors)
  larry.color(random_color)
```