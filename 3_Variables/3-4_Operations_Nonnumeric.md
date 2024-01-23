# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 3.4 - Operations with/on Non-numeric Variables

--------


## Operator Overloading

Consider the snippet

    x = 1
    y = 2
    z = 3
    
    S = x + y + z
    
    print("S =", S)

At this point, you can probably anticipate what will be printed to the command prompt. 
However, what about

    x = "READ "
    y = "THE "
    z = "DOCS!"
    
    S = x + y + z
    
    print("S =", S)

What do you think will happen in this case? Well, as you've probably guessed, what 
you'll see printed to the command prompt is

    S = READ THE DOCS!

This illustrates an important concept, namely *operator overloading*. Essentially, 
operator overloading is a simple example of *polymorphism* (which is just a fancy way of
saying "how something changes its meaning based on context"). For this particular 
example, consider the `+` operator together with two variables `x` and `y`. The operator 
overloading in play here is as follows

  * If `x` and `y` are both numeric, then do the usual mathematical addition.
  
  * Otherwise, if `x` and `y` are both strings (i.e., text), then do string
    concatenation.

where "string concatenation" is the process of stitching a sequence of strings together 
end-to-end (e.g., "READ " + "THE " + "DOCS!" = "READ THE DOCS!", "L" + "O" + "L" = "LOL",
etc.).  

We've also already seen another example of polymorphism. Can you think of what it is? 
(**Hint**: how have we used the `print()` function so far?)


### Minimal Working Example

Let's try an MWE in which we declare some number of variables (call them whatever you
want), initialize some of the variables as strings (text in double quotes "..."), 
initialize the other variables as random decimal numbers, and then play with the basic
arithmetic operations to get a sense of operator overloading.  

Try mixing numeric and non-numeric variables together and see how that blows up. `1 + 1` 
make sense, and `"PAY" + "DAY"` should now also make sense, but what about `1 + "DAY"`?
What about `"PAY" + 1`? ... it's total nonsense, isn't it?

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * An initial, simple understanding of operator overloading (and the more general idea 
    of polymorphism). Don't worry if this is still a but unclear; polymorphism is a more 
    intermediate concept, but very, very important (hence why we're daring to introduce 
    it so early!).
  
  * Mixing variables of different *type* rarely (if ever) makes any sense!

