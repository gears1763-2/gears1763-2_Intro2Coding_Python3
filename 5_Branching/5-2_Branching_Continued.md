# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 5.2. - Branching (continued)

--------

## The `try-except-else-finally` Block

Another branching statement that is somewhat common is the `try-except-else-finally` 
block. See <https://docs.python.org/3/tutorial/errors.html>  

The way this block works is

  * Try to [do bunch of stuff]. (This is the `try` block)
  
  * If this causes an `Exception` to be raised, then [do bunch of stuff]. (This is the 
    `except` block)
  
  * Otherwise, if no `Exception` was raised, then [do bunch of stuff]. (This is the 
    `else` block)
  
  * Finally, [do bunch of stuff] in any case. (This is the `finally` block)

In the specific syntax of Python, a simple example that uses everything might be

    import random
    
    random_integer = random.randint(1, 10)
    random_float = random.uniform(-1, 1)
    
    try:
        random_division = random_integer / random_float
    
    except:
        print("You know, you really shouldn't divide by zero ...")
    
    else:
        print("random_division =", random_division)
    
    finally:
        print()
        print("and this came from")
        print()
        print("random_integer =", random_integer)
        print("random_float =", random_float)

You can probably already read and make sense of this script. =)


## A Word of Caution

This particular branching statement, while it has many good use cases, is also dangerous 
when used irresponsibly. Notice that the `try-except` part can cause `Exception`s to 
become unhandled (which, in turn, can lead to undefined behaviour that is usually 
horrifically difficult to debug!). For example, doing something flippant like

    try:
        [do bunch of sketchy stuff]
    
    except:
        # dont be such a whiny baby
        pass

causes any `Exception`s raised in the `try` block to be ignored (since the `except` 
block contains only a tongue-in-cheek comment, followed by a `pass` statement [which is 
the Python "do nothing"]). If you're doing something like this to "make the `Exception`s 
go away", then you're absolutely doing it wrong.  

This points out an important mindset in programming: embrace failure. Do it early, do it 
often, and learn from it. Python `Exception`s (like good documentation) are your friend,
and without them it would be borderline impossible to write reliable software of
anything more than trivial complexity. `Exception`s are not an annoyance to be avoided;
they're there to help you. So, when they happen (and they will!), don't feel bad about
it; even the most seasoned programmers mess up on a regular basis. 


### Minimal Working Example

Let's try an MWE in which we declare and initialize some number of numeric variables 
(using random initialization), and then have execution branch depending on the state 
(i.e., values) of the variables. Be sure to use at least one `except`, one `else`, and 
one `finally` block.  

If you'd like to include data structures in the MWE, then by all means! It won't be long 
now before you find yourself using as many (if not more) structures than simple scalars 
anyways.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * The `try-except-else-finally` block is a (somewhat) common means of implementing 
    branching based on whether or not an `Exception` is raised.
  
  * PLEASE USE RESPONSIBLY.
