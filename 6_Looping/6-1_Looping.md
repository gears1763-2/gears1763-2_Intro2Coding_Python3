# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 6.1. - Looping

--------


## Motivation

Despite the fact that branching statements allow us to now write scripts that aren't so 
linear, scaling remains a problem. Computers are most useful when tasked with doing the 
same thing, over and over, many times (and with great speed), but as it currently stands, 
the only way for us to do that now is to write a lot of very repetitive (and thus error 
prone!) code.  

Fortunately, constructs know as *looping* statements allow the programmer to express 
repetitive tasks, to be executed an arbitrary number of times, using a simple and
concise notation. Looping is the focus of this section of the course.


## The `for` Loop

Probably the most common loop in Python (and perhaps across most programming languages)
is the `for` loop. When paired with *iterable* data structures (i.e., structures with a 
sense of "next, next, next, ..."), `for` loops become very useful. For example, suppose 
we have

    data_list = [1, 2, 3, 4, 5, 6, ..., 1000]

and we wish to print out each individual element of `data_list` on its own line. We
could certainly write a script that looks like

    print(data_list[0])
    print(data_list[1])
    .
    .
    .
    print(data_list[999])

But ... that's disgusting. Instead, it's far more concise to use a `for` loop here. One 
possible solution is

    for element in data_list:
        print(element)

What's happening here is

  * A looping variable `element` is declared and initialized to `data_list[0]`.
  
  * `element` is printed.
  
  * `element` takes the value of the next element of `data_list`.
  
  * The loop repeats (said to be an *iteration* of the loop).

This continues until there is no "next element" of `data_list`.  

In a similar manner, you can loop over a `dict` as well. For example,

    P1234 = {
        "project number": 1234,
        "project codename": "Artemis",
        "language": "Python 3.12.1",
        "contributors": ["Tom", "Dick", "Harry"]
    }
    
    for key in P1234.keys():
        print("key =", key)
        print("value =", P1234[key])
        print()

Can you make sense of what's going on here?


## Generators and Comprehensions

A bit of an aside (and it was tempting to introduce this in the data structures section), 
but it is related to `for` loops and so does have a place here. It's also quite useful, 
and so is definitely worth introducing.  

### Generators

First, there is a concept in Python referred to as a *generator*, and the generator that 
is probably most commonly used is the `range()` function. How this works is best
demonstrated using an example. Suppose we wish to consider every integer between 1 and 
1000, and then print that integer if it is divisible by either 3 or 5. One solution is 

    for integer in range(1, 1001):
        if (integer % 3 == 0) or (integer % 5 == 0):
            print(integer)

What is happening here is that the `range()` function is returning each subsequent 
integer, *in the range of* 1 (inclusive) and 1001 (exclusive), on each iteration of the 
`for` loop. If that's a bit confusing, then another example that might help is

    import random
    
    lower = random.randint(1, 10)
    upper = 100 * lower
    
    for integer in range(lower, upper):
        print(integer)
    
    print()
    print("lower is", lower)
    print("upper is", upper)

What is happening here is essentially the same; the  `range()` function is returning
each subsequent integer, *in the range of* `lower` (inclusive) and `upper` (exclusive),
on each iteration of the `for` loop.  

Given the functionality of `range()`, it is now possible to also implement the first 
`for` loop example shown as follows

    for i in range(0, len(data_list)):
        print(data_list[i])

In the original example, we might say *we're looping over the elements (or values) of
`data_list`*, whereas in this alternate example we might say *we're looping over the
indicies of `data_list`*. The difference between these two ideas is a bit subtle, but it
is also rather important. For example, if we have two *parallel* lists (say, `list_1`
and `list_2`) that are both the same length, and we need to do a looping operation that 
does something with the corresponding elements from each list, then we would want to use 
a "looping over indices" rather than a "looping over values" approach; something like 

    for i in range(0, len(list_1)):
        [do something with list_1[i] and list_2[i]]


### Comprehensions

Now, a slick feature unique to Python (which kind of feels like magic) is what's called
a *comprehension*, and when you encounter this you will no doubt almost always encounter 
a `list` comprehension. Essentially, this is (often) using a generator (like `range()`)
to populate the elements of a `list`. For example, need a list of every integer from 1
to a million? No problem

    integer_list = [integer for integer in range(1, 1_000_001)]

The part that makes it feel like magic is that you can combine this with logic to
exclude elements of the range that aren't relevant to your particular needs. Want the 
same integer list, but don't want anything divisible by 7? Still easy

    integer_list = [integer for integer in range(1, 1_000_001) if (integer % 7 != 0)]

Remember the divisible by 3 or 5 example presented previously? How about

    solution_list = [integer for integer in range(1, 1001) if (integer % 3 == 0) or (integer % 5 == 0)]

Also, if you already have an iterable structure (like a `list`), then there's nothing
stopping you from using that in a comprehension instead of a generator. For example

    integer_list = [integer for integer in range(1, 101)]
    
    evens_list = [integer for integer in integer_list if (integer % 2 == 0)]
    
    odds_list = [integer for integer in integer_list if (integer not in evens_list)]


## Minimal Working Example

Let's try an MWE in which we play `FizzBuzz`. This is a game (admittedly contrived) in 
which we consider every integer in some range from 1 to N (just pick an upper bound, or 
set it randomly), and then do the following for each integer in the range

  * If the integer is divisible by 3, print `Fizz`.
  
  * If the integer is divisible by 5, print `Buzz`.
  
  * If the integer is divisible by both 3 and 5, print `FizzBuzz`.
  
  * If the integer is divisible by neither 3 nor 5, print the integer.

For example, for the integer range 1 to 15, the `FizzBuzz` solution is

    1
    2
    Fizz
    4
    Buzz
    Fizz
    7
    8
    Fizz
    Buzz
    11
    Fizz
    13
    14
    FizzBuzz

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use loops to concisely express repetitive operations (for any arbitrary 
    number of iterations).
  
  * You can either loop over the elements of a `list`, or you can loop over the indices 
    of a `list`.
  
  * You can use generators and comprehensions to quickly (and concisely) initialize a 
    `list`, even one with non-trivial membership criteria.
  
  * You can combine branching and looping statements together.
