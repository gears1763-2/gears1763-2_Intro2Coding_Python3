# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.5 - Variable Type

--------


## Variable Type

The previous lesson introduced (albeit implicitly) the idea of variable *type* (think 
numeric vs non-numeric, for the time being). For example, the operator overloading of 
`+` was determined by the type of its parameters (`x` and `y`, in our examples). This 
idea of type is an important one in programming, so much so that it does warrant its own 
lesson.  

Now, Python in particular is actually not the best programming language for teaching 
types. This is because Python is very forgiving in its handling of types; namely

  * Variable type is inferred at assignment (so-called "duck typing"; if it looks like
    a duck and it quacks like a duck, then it must be a duck); and,
  
  * Variable type can change at runtime (Python is said to be "dynamically typed").

For example, in Python one can do the following

    x = 2
    print(x)
    
    x = "Sasquatch"
    print(x)
    
    x = 3.14
    print(x)

and this will execute as one might expect

    2
    Sasquatch
    3.14

However, in most other programming languages (like C++ or FORTRAN), variables cannot
change type once they've been declared (the language is said to be "statically typed"), 
and Python-like "duck typing" is considered to be heresy; you simply cannot do it. This 
has pros and cons. One pro is that a dynamic and duck-typed language like Python is
arguably a lot more flexible (and closer to natural language as a result). However, 
the corresponding con is that this actually makes Python a lot more error prone. Think 
about our previous experience in attempting to mix types when performing arithmetic 
operations. If you tried to do this in C++, the compiler would immediately notice and 
yell at you. The Python interpreter, however, may or may not fuss about it (and even if 
it does, it won't until it tries to execute your script). This can make Python much 
harder to debug. 

Fortunately, with the adoption of a few good programming practices, the potential
drawbacks of Python's forgiving-ness can be largely mitigated. For instance

  * Use descriptive variable names that make the intended type clear. For example,
    `person_first_name`, `person_last_name`, `person_age_years`, and `person_weight_kg`
    rather than just `fn`, `ln`, `a`, and `w`. From the descriptive variable names, one
    should be able to infer the intent: the first two variables are strings, and the
    last two are numeric (either integers or decimal numbers; could be either). By 
    contrast, the concise and non-descriptive variable names could mean anything.
  
  * Get into the habit of test-driven development. Initially and informally, this is the 
    habit of testing your script (simply try and execute it) every time you make a change 
    to it, and restricting the scope of changes to incremental ones (i.e., make larger 
    sequences of smaller changes, rather than smaller sequences of larger changes).
    Catch errors early and often, and address them as they arise.

### Minimal Working Example

Let's try an MWE in which we declare and initialize a bunch of variables and then make 
use of Python's `type()` function to print information on their types. For this MWE,
try the following first

    x = 2
    print("x =", x, " (x is a", type(x), ")")
    
    x = "Sasquatch"
    print("x =", x, " (x is a", type(x), ")")
    
    x = 3.14
    print("x =", x, " (x is a", type(x), ")")

What do you see printed to the command prompt? Does `x = 2` have the same type as 
`x = 3.14`?  

Once you've done that, experiment however you wish.  

Are you starting to see the difference between the *value* of a variable and the *type* 
of a variable?

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * The difference between the *value* of a variable and the *type* of a variable.
  
  * Python is dynamic and duck-typed, and this has pros and cons.
  
  * How to get information on the type of a variable (using the `type()` function).

