# Intro to Python - Session 1

Goals for this workshop:
* Learn basics of what is computer programming
* Use the `Turtle` software package to learn some basics of the Python programming language

### Setup
1. Ensure you are using a modern web brower such as Google Chrome or Mozilla Firefox
1. Have your parent setup an account on https://repl.it/

### Intro
See slide deck up to the Repl.it slide

Turtle demo code:

Repl - https://repl.it/repls/IllustriousLatestCallback

```
import turtle
import random
larry = turtle.Turtle()

larry.shape('turtle')
larry.color('green')
larry.speed(0)

colors = ['green', 'blue', 'red', 'yellow']

for i in range(100):
  larry.circle(i*3)
  larry.left(10)
  larry.color(random.choice(colors))
```

### Python Basics
* `print`, `type`, `input` commands
* string, integers
* Variables
* Basic math

#### `print()` command

The `print()` command is probably one of the most fundamental Python commands because it prints or outputs anything passed into it. 

> In the Repl console, type: 
`print('Hello world')`

You will see the output:
```
Hello world
```
Let us dissect the output a little bit:

* `print()` is a Python **command** 

* All Python commands end with a `()` to tell Python that this is a command

* With some commands, like this one, you can put stuff between the `()`. The stuff, called arguments or parameters, are said to be 'passed to the command'

* We passed some text, `'Hello world'` to the `print()` command. This is why it was displayed in the console. **Anything that is between quotes in Python is called a `string`.** 

Now, in addition to strings, we have integers in Python, which are whole numbers with no decimal places or fractions.

> Print an integer like `10` in the console.
`print(10)`

Notice - here we did not put quotes around the `10` to print it. But we could. 
```
> print('10') 
10
```
In the output display, `print(10)` and `print('10')` look to be the same. What is different?

> Try both the following:
`print(10+2)`
`print('10' + 2)`

* What happens in the second case and why?
* What about `print('10' + '2')` ?

The next command will help us shed some light on what type of data we are using.

#### `type()` command

Let us look at the next Python command, `type()`

> In the console, run:
`type('Hello world')`

You will see an output like:
`<class 'str'>`

This means the `'Hello world'` object is of a class `'str'` which stands for `string`. A class is just a category or blueprint for a type of object in Python.

> In the console, run:
`type(10)`

You will see an output like:
`<class 'int'>`

This means the `10` object is of a class `'int'` which stands for `integer`.

> Q) What is the class of `'10'`?

So earlier, we were trying to run `print('10' + 2)` which was adding a string with an integer. This is a no-no in Python. We can only add integers together and strings together. 

#### Variables

A variable is just a label for a container holding some value. It can be empty or contain a string, integer or some other Python data. 

For example:
```
some_variable = 'This is a variable string because this text is surrounded by quotes'

other_variable = 6
```

* Note the variable name - it is NOT in quotes. 

* Also the convention in Python is to use all lowercase when creating your variable names. 

> In your code editor this time, create a variable called `age` with a value equal to your age.

> Then, write a `print()` command which will print your `age` variable.

> Press the **run** button to run both commands together.

Notice in our Repl Code Editor that Python colour codes things as follows:
* Comments are shown in grey
* Variables are shown in black
* Built-in Python commands are shown in blue
* Strings are shown in brown

Again, we are using the Code Editor instead of typing directly into the console because we want to run multiple lines of our code together quickly. In the console, we would have to run each line one by one.

#### `input()` command

What if we want to get some user input to work with? Python has an `input()` command we can use to ask or prompt the user at the console for some information. 

> Back in your Code Editor, use the following input command to your existing code:
```
# Python Basics

age = input('What is your age? ')
print(age)
print(type(age))
```
Here, we **assign** the input received to the variable `age`. 

Note the type of object that `age` is, even though what we entered looks like an integer.

We can convert the value of `age` from a string to an integer by using Python's built-in `int()` command:
```
age = int(age)
print(age)
print(type(age))
```


> Ask the user what their name is and assign that value to a new variable `name`. Then print the value of `name`.

#### Basic Math in Python

Here are the basic math operators in Python:
* `a+b` is a + b
* `a-b` is a - b
* `a*b` is a x b
* `a/b` is a / b

> In the Console, go through each of the above math operators using:
* `a` as your age
* `b` as your grade. 

##### Exercise

Write a program which does the following:

1. Asks the user to input their weight in pounds
2. Assigns the value to a variable called `weight_pounds`
3. Create a new variable called `weight_kilos` which is related to `weight_pounds` as follows:
```
weight_kilos = weight_pounds / 2.2
```
4. Print the `weight_kilos` to the console

5. Add some extra text to the `print()` command using commas as follows:
```
print('Your weight in kilos is', weight_kilos)
```

Next we are going to look at Python in action using the Turtles software package. 

> 1. Click on the Settings icon (3 layers) to open the left-hand menu drawer. 
> 2. Right-click on `My Repls` and open the link in a new tab. 
> 3. Then select the `Intro to Turtle` repl. 

### Intro to Turtles

Ensure you have opened the `Intro to Turtle` repl. Note that this repl looks a bit different. There's no File Explorer - just the Code Editor and both a 'result' and 'console' output page. The 'result' tab is where we will see graphical outputs from our Turtle exercise.

Let us look at our starting code and go through each line:
```
import turtle

larry = turtle.Turtle()

larry.shape('turtle')
```

* `import turtle` - this is how we bring in a software package from somewhere else into our program. Note it is displayed in black which is a variable or a container holding some value. In this case, it is holding the blueprint for how all turtles should look and behave. Whenever we reference the `turtle` variable now, we are using the blueprint.

* `larry = turtle.Turtle()` - this part is a little tricky but essentially we are taking the `turtle` variable, which is a blueprint, and saying "use the blueprint to create a new version or instance of a turtle called `larry` by using the `Turtle()` command. Remember - commands end with the `()` and sometimes there is stuff or arguments in between the `()` and sometimes not. See slide for details.

* `larry.shape('turtle')` - Now we are doing stuff on our newly created turtle called larry. There is a command to set the shape of larry to actually be a turtle versus a dot or a triangle or some default icon.

How do we know what commands are available for larry and any Turtle in general? Well, we can look at the Turtle Book, which in general is called 'documentation'. Here is a website which goes through the Turtle documentation and what commands are available: https://docs.python.org/3.3/library/turtle.html?highlight=turtle#turtle-methods 

> Press *run* to see larry now. Q) How do we change the color of larry to green?

Now let us move larry around.

> Q) How do we move larry forward 50 units?

> Q) How do we then move larry back 100 units?

Larry can also be moved left or right by passing a number into the command `left()` or `right()`

> Try the following:
```
larry.left(90)
larry.forward(100)
larry.left(90)
larry.forward(100)
```

> Go ahead and complete the square. 

To reset larry, use the `.reset()` command. 

Notice how code is repeated for us to complete the square. We are basically using the same two commands over and over:
```
larry.left(90)
larry.forward(100)
```

> Q) What sort of tools would you expect Python to have to simplify our code? **Ans: Loops!**

A loop in a program basically tells the computer to run through all the commands in the loop over and over if some condition is met and then until some other condition is met.

For example, a program to make a robot walk might say:
```
while battery power above 10%:
    move robot left foot
    move robot right foot
```

In Python, we have many different types of loops. A popular one is called the `for` loop which has a syntax that looks like this:
```
for <each item> in <some group of items>:
    <do something>
```

We will use this together with the `range()` command which you will see in action in just a second.

> Replace your code to create a square with the following:
```
for i in range(4):
    print(i)
    larry.forward(100)
    larry.left(90)
```

> Q) So what does `range(4)` do? 
> Q) What is `i` and how does its value change each time the loop is run? Have a look at the output in the console. Refer to slide.

* Note the indenting on the `for` commend, which tells Python that the following indented commands after the `:` belong to the loop. Otherwise, Python would not know when the loop finishes and the next command starts. 

Now with the power of loops, we can make some really interesting patterns using very little code.

> Try the following code:
```
for i in range(8):
    larry.forward(100)
    larry.left(225)
```

* We can also use the fact that `i` increments every time the loop is run to add variable increments in our pattern.
```
# Make a maze
for i in range(16):
    larry.forward(10*i)
    larry.left(90)
```

**Note: If you don't want to wait for the entire trace, set `larry.speed(0)` before you start moving your turtle.** 

We can also create a circle with `larry.circle(100)`. 

> Q) What does the 100 mean here? Radius What about `-100`? 

So what if we now use our `for` loop with circles such as:
```
for i in range(50):
  larry.circle(i*3)
  larry.left(10)
```
> Now what if you make the range 100?

* Note - in our `circle()` command, we are not restricted to drawing whole circles. What number do you think we can pass into our circle command as the second argument to make only a half circle?

> Try the following which uses half circles:
```
for i in range(20):
    larry.circle(i*3, 180)
    larry.right(45)
```

> Change the color to red

* Go ahead and experiment with loops - try different shapes and repetitions!

> Here's the code for a cool spiral:
```
# Cool spiral
for i in range(100):
    larry.forward(i*2)
    larry.circle(i*2, 90)
    larry.right(20)
```