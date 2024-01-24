# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 8.1. - Functions

--------


## Motivation

Python can do a lot (like, *a lot*) out of the box. You can even add mature and well 
tested third-party packages and modules to it, to further extend its capabilities 
(more on that next section). But even with all that, what you end up with may not be
quite right for your particular needs. When that happens, there's only one thing to do:
it's time to strike out on our own. 

We've already used a number of functions in this course (`print()`, `input()`, `open()`, 
etc.), so the idea of a *function* should be starting to form for you. The focus of this 
section is introducing how to write your own custom functions, as the first step in 
striking out on your own.  

(This section barely scratches the surface!)


## Functions

Let's just begin with a very simple function definition. How about

    def add(x, y):
        return x + y

Here's what is going on

  * Define (`def`) a function called `add()`.
  
  * `add()` takes two arguments: a first called `x`, and a second called `y`.
  
  * When *called*, the function *returns* `x + y`.

Of course, `add()` is just a function which takes in `x` and `y` and returns their sum. 
That said, how would you expect the following to behave?

    print(add(1, 1))
    print(add(2, 3))
    print(add(-1, 1))
    print(add("OH ", "BOY!")

You can, of course, make more complex functions too; for example

    def playFizzBuzz(N):
        integer_list = [integer for integer in range(1, N + 1)]
        
        for integer in integer_list:
            [FizzBuzz game logic here]
        
        return

Yes, that's right, you don't actually have to return anything. In this case, `return` 
essentially is the function saying "OK, I'm done".  

You can also have functions calling other functions, like

    def isEven(x):
        if (x % 2 == 0):
            return True
        else:
            return False
    
    
    def getNextCollatzNumber(x):
        if isEven(x):
            x = x / 2
        else:
            x = 3 * x + 1
        
        return x

In this case, we say `isEven()` is a *helper function* for (or of)
`getNextCollatzNumber()`. If you're writing a function and it's becoming unwieldy, 
you should consider breaking it down into smaller functions.


## A Word on Keeping Things DRY

In programming, one should always aim to keep their code DRY, which simply stands for 
Don't Repeat Yourself. For example, if you have something like 

    for element in list_1:
        if (element % 2 == 0):
            print("even")
        else:
            print("odd")
    
    for element in list_2:
        if (element % 2 == 0):
            print("even")
        else:
            print("odd")
    
    for element in list_3:
        if (element % 2 == 0):
            print("even")
        else:
            print("odd")
    
    .
    .
    .

where you find yourself copy-pasting the same block of code over and over again with 
only minor changes, then that is almost always an indication that that block is better 
implemented as a function. Compare the above to

    def printEvenOdd(input_list):
        for element in input_list:
            if (element % 2 == 0):
                print("even")
            else:
                print("odd")
        
        return
    
    
    printEvenOdd(list_1)
    printEvenOdd(list_2)
    printEvenOdd(list_3)
    .
    .
    .

Rather more concise? Of course, it would be even better to implement the sequence of 
`printEvenOdd()` function calls in some kind of loop ...


### Minimal Working Example

Remember the not-so-minimal working example of `6.2 - Looping (continued)`? Extracting 
the sublist of primes from a list of integers? Well, try *refactoring* your solution 
using your own function definitions.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can define your own custom functions in Python.
  
  * You can have functions working together (i.e., calling eachother) to achieve complex 
    behaviour.
