# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.3 - Operations with/on Numeric Variables (continued)

--------


## Extended Arithmetic

As your scripts evolve over time and become progressively more sophisticated, you will 
likely run into the need for non-basic arithmetic operations (referred to here as 
extended arithmetic). Fortunately, much like the `random` module provides one with 
random number generation, the `math` module provides one with more advanced operations 
for numeric variables (by *extending* the basic arithmetic of Python). To name a few
(and these *should* be familiar from highschool math =P):

  * `math.pow(x,y)` returns `x` raised to the power of `y`.
  
  * `math.sqrt(x)` returns the square root of `x`.
  
  * `math.exp(x)` returns `e` (Euler's number) raised to the power of `x`.
  
  * `math.log(x)` returns the natural logarithm of `x`.
  
  * `math.sin(x)` returns the sine of `x` (`x` in radians!)
  
  * `math.cos(x)` returns the cosine of `x` (`x` in radians!)

And so on and so on (the `math` module has a lot in it!). For more details, see 
<https://docs.python.org/3/library/math.html> (Seeing a trend here? As a programmer, 
good documentation is your friend!).


### Minimal Working Example

Let's try an MWE in which we declare two variables `x` and `y`, initialize each with
some random *decimal number* between 0 and 10, perform a bunch of extended arithmetic 
with them, and then print the corresponding results. For the "getting a random decimal 
number" part, refer to the documentation for the `random` module (see
<https://docs.python.org/3/library/random.html>; is friend, yes? =P) and select a
suitable function. This is an important exercise because real programmers spend a good
chunk of their time doing just this; reading the docs to find ways of solving their
problems.

--------

## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can perform non-basic arithmetic operations with numeric variables.

  * Good documentation is your friend!
  
  * You can import as many modules as you need.

