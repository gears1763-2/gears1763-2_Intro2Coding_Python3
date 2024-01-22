# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 5.1. - Branching

--------

## Motivation

With a basic understanding of variables and data structures, we already have a good deal 
of flexibility in terms of what we can do with Python. However, we're still limited in 
two key ways; namely

  * Our scripts are still very linear (it's always the same sequence of operations); and,
  
  * Our scripts don't scale very well (doing lots of operations on lots of data can only 
    be done by writing lots of code).

The first limitation can be addressed by introducing what are called *branching*
statements (so called because they allow a script to branch off in multiple different 
directions), and this is the focus of this section of the course.  

The second limitation will be addressed in the next section of course, in which 
*looping* statements are introduced.


## The `if-elif-else` Block

The branching statement that is most commonly used in Python is almost certainly the 
`if-elif-else` block, and this is due largely to how straightforward it is (in fact, 
essentially any programming language will have some version of this construct). See 
<https://docs.python.org/3/tutorial/controlflow.html>  

Branching in this manner unfolds as follows

  * If statement A is `True`, do [bunch of stuff]. (This is an `if` block)
  
  * Otherwise, if statement B is `True`, do [bunch of stuff]. (This is an `elif` block)
  
  * Otherwise, if ...
  
  * Otherwise, if statement Z is `True`, do [bunch of stuff]. (This is an `elif` block)
  
  * If all else fails, [do bunch of stuff]. (This is an `else` block)

Note that the structure of an `if-elif-else` block is always the same

  * An initial `if` block; then,
  
  * Any number (even zero) of `elif` blocks; then,
  
  * An optional `else` block.

In the specific syntax of Python, a simple example that uses everything might be

    import random
    
    random_integer = random.randint(-5, 5)
    
    print("random_integer =", random_integer)

    if (random_integer > 0):
        print("random_integer is > 0")
    
    elif (random_integer < 0):
        print("random_integer is < 0")
    
    else:
        print("random_integer is 0")

You can probably already read and make sense of this script. Of course, it initializes 
`random_integer` to some random integer value between -5 and 5, and then prints
information on `random_integer` depending on its sign.  

Are you starting to see why the `3.7 - Variables and Logic` module was a bit ... extra? 
Hopefully the usefulness of branching statements is obvious, and you can already
anticipate using them *a lot*. But then, how your script branches depends on the
truthfulness of whatever logic you pair with each `if` and `elif` block. If you don't
understand variables and logic, then branching statements will remain largely
unaccessible!


## Significant Whitespace

You may notice in the example provided above, that the [bunch of stuff] associated with 
each `if`, `elif`, and `else` statement is defined by its indentation. This is a feature 
unique to Python, in that *scope is defined by indentation* (and so Python is said to 
have *significant whitespace*; how we space and indent things matters to the
interpreter!). This is important to keep in mind, because things like inconsistent
spacing, or mixing tabs and spaces, can cause the Python interpreter to raise an
`Exception`. This can be particularily annoying because, to you, the script may look 
fine! Fortunately, this can be largely mitigated by doing two things

  * Be consistent: If you want to use spaces, then use spaces. If you want to use tabs, 
    then use tabs. Pick one and stick with it.
  
  * Make whitespace visible: Use an editor that displays whitespace information (e.g.,
    denotes spaces differently from tabs). Both Notepad++ and Geany provide this.
  

## Minimal Working Example

Let's try an MWE in which we declare and initialize some number of numeric variables 
(using random initialization), and then have execution branch depending on the state 
(i.e., values) of the variables. Be sure to use at least one `elif` block and one `else` 
block.  

Try an MWE that uses multiple `elif` blocks (and hopefully you'll see that they 
have an order of priority; first-come, first-(and-only)-served).

Can you think of an MWE that demonstrates branching based on data structure logic? 
There's nothing stopping you from doing this too (and it is often useful!). For example, 
if a `list` is empty, do this, otherwise, do that.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can cause your script to behave differently depending on the state of the
    variables and/or data structures in play during any given execution *instance*.
  
  * The `if-elif-else` block is a (very) common means of implementing branching based 
    on the truthfulness of various logical statements.
