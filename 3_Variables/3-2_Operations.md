# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.2 - Operations with/on Numeric Variables

--------


## Basic Arithmetic

Of course, it is possible to perform operations with/on variables (and this is when they 
really start to become useful!). For example, if we have two *numeric* variables called 
`x` and `y`, then we can perform the basic arithmetic operations with them. For instance 

  * `x + y` adds the values of `x` and `y` together and returns the result.
  
  * `x - y` subtracts the value of `y` from the value of `x` and returns the result.
  
  * `x * y` multiplies the values of `x` and `y` and returns the result.
  
  * `x / y` divides the value of `x` by the value of `y` and returns the result.

There is also one other arithmetic operation that is basic but rarely used outside of 
mathematics and programming, and that is the modulus operator.

  * `x % y` performs the integer division of `x` by `y` and returns the remainder 
    (remember long division from ye olde elementary school days?). This may seem silly 
    and of little use, but it is in fact often quite useful in programming! For example, 
    if `x % y` returns 0, then `x` is divisible by `y`.

### Minimal Working Example

Let's try an MWE in which we declare two variables `x` and `y`, initialize each to some
random integer between 0 and 9, perform each of the basic arithmetic operations listed
above, and then print out the results. Try building this script on your own, but be sure
to include the following elements somewhere in the script:

  * Have a line that just contains an operation (like just `x + y` and nothing else,
    for example).
  
  * Have two lines which initialize a new variable `z` with the return from some
    operation on `x` and `y` (like `z = x * y`, for example), and then print the 
    resulting value of `z`.
  
  * Print the return from some operation on `x` and `y` directly (that is, don't create 
    any new variable to contain the return).

Think about what it means for an operation to *return* a value (that term has been used 
a few times now). What happens if "there's nobody around to catch the return"?

Also, you may run into some errors (called `Exception`s in Python) when you try to 
execute your script (see <https://docs.python.org/3/library/exceptions.html>). If this 
does happen, exception handling in Python is usually very good, and the error messages 
are usually quite descriptive. If this happens, just try reading the message to see if 
you can make sense of the cause(s). Don't worry if it doesn't make much sense at this 
point!

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can perform basic arithmetic operations with numeric variables.
  
  * You can use the return from an operation to intialize a new variable (or directly
    as a function parameter).

