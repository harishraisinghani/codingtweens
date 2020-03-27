# Intro to Python with Turtles

Goals for this workshop:
* Learn what is computer programming
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

### Intro to Variables

Ensure you have opened the `Intro to Turtle` repl. Note that this repl has the Code Editor and both a 'result' and 'console' output page. The 'result' tab is where we will see graphical outputs from our Turtle exercise.

Let us start by understanding the concept of variables and how they are setup in Python.

A variable is just a label for a container holding some value. It can be empty or contain some string of letters and numbers (uses quotes), or an integer or some other Python data. 

For example:
```
some_variable = 'This is a variable string because this text is surrounded by quotes'

other_variable = 6
```

* Note the variable name - it is NOT in quotes. 

* Also the convention in Python is to use all lowercase when creating your variable names. 

> In your code editor, after all the starter code, create a variable called `age` with a value equal to your age.

> Then, write a `print()` command which will print your `age` variable to the Console. 

> Press the **run** button to run the commands.

Notice in our Repl Code Editor that Python colour codes things as follows:
* Comments are shown in grey
* Variables are shown in black
* Built-in Python commands are shown in blue
* Strings are shown in brown

Variables are used everywhere in Python and are very important so remember some of the key basics. 

### Intro to Turtles

Let us look at our starting code:
```
import turtle

larry = turtle.Turtle()

larry.shape('turtle')
```

* `import turtle` - this is how we bring in a software package from somewhere else into our program. `turtle` is holding the blueprint for how all turtles should look and behave. Whenever we reference the `turtle` variable now, we are using the blueprint.

* `larry = turtle.Turtle()` - this part is a little tricky but essentially we are taking the `turtle` variable, which is a blueprint, and saying "use the blueprint to create a new version or instance of a turtle called `larry` by using the `Turtle()` command. In Python, commands end with the `()` and sometimes there is stuff or arguments in between the `()` and sometimes not. See slide for details.

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

We can also create a circle with `larry.circle(100)`. 

> Q) What does the 100 mean here? Radius What about `-100`? 

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

We will use this together with something called the `range()` command which you will see in action in just a second.

> Replace your code to create a square with the following:
```
for i in range(4):
    print(i)
    larry.forward(100)
    larry.left(90)
```

> Q) So what does `range(4)` do? A) It provides us with a group of 4 items or numbers
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

So what if we now use our `for` loop with circles such as:
```
for i in range(50):
  larry.circle(i*3)
  larry.left(10)
```
> Now what if you make the range 100?

* Go ahead and experiment with loops - try different shapes and repetitions!

> Here is the code for a cool spiral:
```
# Cool spiral
for i in range(100):
    larry.forward(i*2)
    larry.circle(i*2, 90)
    larry.right(20)
```