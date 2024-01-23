# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 6.2. - Looping (continued)

--------


## The `while` Loop

In addition to the `for` loop, another quite common loop is the `while` loop. This
differs from a `for` loop in one key way. That is, while a `for` loop *loops over some 
iterable*, a `while` loop *loops for as long as some condition is `True`*. For example,

    integer = 0
    
    while (integer < 100):
        print(integer)
        integer = integer + 1

What's happening here is that `integer` is intialized to 0, and then *so long as*
`integer` is less than 100, it is printed and then *incremented* by one (i.e., `integer` 
increases its value by one on each iteration of the loop). Note than an alternative 
shorthand for the last line of this example is

    integer += 1

It is interesting and insightful to observe that

    for i in range(lower, upper):
        print(i)

is equivalent (in its outcome) to

    i = lower
    
    while (i < upper):
        print(i)
        i += 1

So you can always translate a `for` loop into a `while` loop, and *vice versa*.  

## Beware the Infinite Loop

Of course, the construct of a `while` loop also introduces a problematic possibility; 
namely, the infinite loop. Remember, a `while` loop continues to iterate for as long as 
its test statement remains `True`. So then, if the test statement is always `True`, a
`while` loop will loop forever. For example, if we forget the last line of the `while` 
example presented above

    integer = 0
    
    while (integer < 100):
        print(integer)

the result will be

    0
    0
    0
    0
    .
    .
    .

for all eternity (well, until the computer breaks down, or loses power, or ...). The 
problem, of course, is that we fail to increment `integer` on each iteration, and so its
value never changes, therefore the statement `integer < 100` is always `True`, therefore
the loop just grinds on and on.  

When using `while` loops, remember to remain on guard against the infinite loop.


## The `break` Statement

Suppose you have an application in which you need to loop something, but you may be able 
to "quit early"; it's not always necessary to loop over the full possible range. For 
example, suppose that we're looking for people in a class whose names start with "A",
"B", or "C", but we only need, at most, 10 such people. One way to implement "quitting
early" is the `break` statement (which can be used to "break out of" any looping
statement). So then, a solution to the example is

    solution_list = [ ]

    for name in class_list:
        if name[0] in ["A", "B", "C"]:
            solution_list.append(name)
        
        if len(solution_list) >= 10:
            break
    
    print(solution_list)

What this will give us is a list of *at most* 10 people in the class whose names start 
with "A", "B", or "C" (regardless of how long or short `class_list` is).  

Note that you could also use the `break` statement to implement an infinite loop guard.
For example

    iteration_count = 0
    iteration_limit = 1_000_000
    
    while ([some complicated logic that is hard to predict]):
        [do stuff]
        
        iteration_count += 1
        
        if (iteration_count >= iteration_limit):
            break


## The `continue` Statement

Suppose you have an application in which you need to loop over something, but you may 
be able to skip individual iterations; it's not always necessary to fully process every 
single iteration. For example, suppose that we need to correct for a bug that has
randomly appended "ZORS" to the end of student names in a class list, such as

    class_list = ["Tom", "DickZORS", "Harry", "LorenzZORS", "PeppaZORS", ...]

One way to implement skipping is the `continue` statement (which can be used to
immediately continue to the next iteration of a loop). So then, a solution to the 
example is 

    for i in range(0, len(class_list)):
        name = class_list[i]

        if ("ZORS" not in name):
            continue
        
        name = name[0 : len(name) - 4]
        
        class_list[i] = name

To clarify, whenever the `continue` statement is encountered within a loop iteration, 
the remainder of the loop body is skipped and execution immediately continues with the 
next iteration.


## Not-So-Minimal Working Example

Here's a not-so-minimal working example (bit of a challenge for you): write a script
that considers a list of integers from 2 to N, and then prints the sublist that
contains all primes in the list.  

If you can't quite remember, a prime is an integer that is divisible only by itself
and one.

This is definitely a little more complex, so one possible approach might start like 
this

    import random

    N = random.randint(20, 100)

    integer_list = [integer for integer in range(2, N + 1)]
    primes_list = [ ]

    for integer in integer_list:
        if integer not in primes_list:
            [do stuff ... maybe another loop here too ...]

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * There are both `for` loops and `while` loops in Python.
  
  * Beware the infinite loop.
  
  * You can use the `break` statement to break out of a loop.
  
  * You can use the `continue` statement to skip a loop iteration and immediately
    continue to the next.
