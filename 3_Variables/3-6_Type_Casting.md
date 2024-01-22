# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.6 - Type Casting

--------


## Type Casting

Now that you have a basic understanding of variable type, it's useful to point out that 
you can change the type of a variable without changing its value (a process called 
*type casting*). For example

    x = 2
    x = float(x)
    print("x = ", x)

Initializes `x` to `2` (integer), but then casts `x` to a float (decimal number). The 
resulting print is then

    x = 2.0

`x` has changed typed (from `int` to `float`) without changing value. You can also 
cast from `float` to `int`, but this may have some unintended consequences (can you 
anticipate what that might be?).  

An often useful casting is from `str` to `int` or `float` and *vice versa*. For example 

    birth_year = 1999
    first_name = "Shmee"
    last_name = "McLovin"
    
    username = first_name + last_name + "_" + str(birth_year)
    
    print(username)

The resulting print is then

    ShmeeMcLovin_1999

While this might seem a bit contrived at this point, when you begin to work with
input/output (IO) operations (either reading from or writing to the disk, or gathering 
keyboard input from the user), you will likely need to implement type casting from `str`
to some numeric (or other) types in order for your script to execute as intended.


### Minimal Working Example

Let's try an MWE in which we declare and intialize a bunch of variables of differing 
value and type (stick to `int`, `float` and `str` for now), and then play with type
casting between them, performing some basic arithmetic operations, and printing the 
results.

--------

## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can change the type of a variable without changing its value (so-called type 
    casting).

