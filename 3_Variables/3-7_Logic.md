# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.7 - Variables and Logic

--------


## Logical Operations

There is another variable type that should be introduced early (as it is used
essentially everywhere in programming), and that is the Boolean (`bool`) type. This is
a logical type; that is, it takes only two values: `True` or `False`. This is also the
return type of the various logical (or comparator) operations for variable value, 
such as 

  * `x == y` returns `True` if `x` is equal (in value) to `y`, `False` otherwise. Notice 
    the difference between assignment (`x = 0`) and comparison (`x == 0`); this is 
    important!
  
  * `x != y` returns `True` if `x` is not equal (in value) to `y`, `False` otherwise.
  
  * `x < y` returns `True` if `x` is less (in value) than `y`, `False` otherwise.
  
  * `x <= y` returns `True` if `x` is less than, or equal to, ...
  
And so on. The `==` and `!=` operations can also be overloaded for type logic. For
example

  * `type(x) == int` returns `True` if `x` is an `int`, `False` otherwise.
  
  * `type(x) != type(y)` returns `True` if `x` and `y` are of different type, `False` 
    otherwise.

And so on.

## Key Words and Truth Tables

There are a few other logical key words in Python which are useful to know, namely `and`,
`or`, and `not`. This allows for implementing more complex logic in terms of simple
logic. For example, if we have a script in which we need the variable `x` to *both* (a)
be an integer *and* (b) be greater than 10, then we can express this as

    (type(x) == int) and (x > 10)

which can only be `True` if `type(x) == int` is `True` and `x > 10` is `True`.
However, if it suffices for `x` to *either* (a) be an integer *or* (b) be greater than
10, then we can express this as

    (type(x) == int) or (x > 10)

which is `True` if either `type(x) == int` is `True` or `x > 10` is `True`. 
Suppose instead that we need `x` to *both* (a) *not* be an integer *and* (b) be greater 
than 10. This can be expressed as 

    (not (type(x) == int)) and (x > 10)

Using `and`, `or`, and `not`, you can compose complex logical statements from any
number of simple logical statements (using parentheses `()` to keep the grouping 
unambiguous).  

However, in composing such complex logic it is important to understand the logical 
conventions for `and`, `or`, and `not`, and this can be illustrated by way of truth
tables for each key word.

The simplest is the truth table for `not`. This key word simply "flips the Boolean value".
So, if `P` is some simple logical statement, then the truth table for `not` is just

| `P`     | `not P` |
|---------|---------|
| `True`  | `False` |
| `False` | `True`  |

that is, whenever `P` is `True`, `not P` is `False` and *vice versa*.

The truth tables for `and` and `or` involve comparing two logical statements (call them 
`P` and `Q`). For `or`, the truth table looks like this

| `P`     | `Q`     | `P or Q` |
|---------|---------|----------|
| `True`  | `True`  | `True`   |
| `True`  | `False` | `True`   |
| `False` | `True`  | `True`   |
| `False` | `False` | `False`  |

That is, `P or Q` is `True` whenever one (or both) of `P` and `Q` are `True`. For `and`,
the truth table looks like this

| `P`     | `Q`     | `P and Q` |
|---------|---------|-----------|
| `True`  | `True`  | `True`    |
| `True`  | `False` | `False`   |
| `False` | `True`  | `False`   |
| `False` | `False` | `False`   |

That is, `P and Q` is `True` only when both `P` and `Q` are `True`.

## Assertion

One other utility worth mentioning here is the `assert()` function. This function can 
be useful for things like catching type and value errors before they can potentially do 
any damage. It is particularily useful for writing automated tests for your scripts (a 
more advanced concept not covered in this course). For example, consider

    x = 0
    assert(abs(x) > 0)

This example initializes `x` to zero, but then asserts that the absolute value of `x` is 
greater than zero (so it asserts that `x` is non-zero). This will result in an
`AssertionError`, the script will immediately stop executing, and an appropriate error 
message will be printed out.  

In general, assertions work like this

  * If the statement passed to `assert()` is `True`, then it will do nothing and
    execution of the script continues.
  
  * Otherwise, if the statement passed to `assert()` is `False`, then it will halt 
    execution of the script and raise an `AssertionError`.


## Minimal Working Example

Let's try an MWE in which we declare and intialize a bunch of variables of differing 
value and type (stick to `int`, `float` and `str` for now), and then play with a variety 
of logical operations both simple and complex (printing out the results). For complex 
logic, you will need to play with the logical key words `and`, `or`, and `not`. For
complex logic, try to use the provided truth tables to anticipate the outcome (i.e., 
`True` or `False`) of some complex logical statement(s).

--------


## Consolidation 

From this not-so-quick lesson (sorry, but it's really important!), you should have
picked up the following bits of knowledge:  

  * The Boolean (`bool`) type exists in Python, and it is always either `True` or `False`.
  
  * You can implement both value logic and type logic using logical (or comparator) 
    operations.
  
  * You can compose complex logical statements from simple ones using the key words `and`,
    `or`, and `not`. The logical behaviour of this follows the conventions laid out in 
    the truth tables.

