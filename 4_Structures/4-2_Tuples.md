# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 4.2. - Python Data Structures: `tuple`

--------


## The `tuple`

Another data structure that is available in Python is the `tuple` (see 
<https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences>). In many 
ways it is similar to a `list` in that the indexing and slicing interface looks the same.
For example,

    data_tuple = (1, 2, 3)
    
    print(data_tuple[0])
    print(data_tuple[1])
    print(data_tuple[2])

would yield

    1
    2
    3

as expected. We can also get the tuple's length

    print(len(data_tuple))

Note that the only difference so far between a `tuple` and a `list` is the 
initialization syntax; lists use square brackets (`[ ]`) whereas tuples use parentheses 
(`( )`). However, whereas a `list` is *mutable* (i.e., it can change after
initialization), a `tuple` is *immutable* (i.e., it cannot change after initialization).
For example, if we take the previously defined `data_tuple` and try some `list`-like 
operations such as

    data_tuple[0] = -1
    data_tuple.append("LOL")

Python will raise an `Exception`. The elements of a `tuple` are protected once
initialized, and this can be useful in programming (for example, protecting data from 
being inadvertently overwritten at some point during execution).  

Note that you can also use an alternative initialization syntax; namely

    data_tuple = 1, 2, 3

You can check this by way of

    print(type(data_tuple))

which indicates that the resulting variable `data_tuple` is indeed of type `tuple`.


### Minimal Working Example

Let's try an MWE in which we declare and initialize a few tuples (call them whatever you 
want and fill them with whatever you wish), and then experiment with indexing, slicing, 
and trying to change them.  

Can you find a way to "trick" Python into changing the state of a tuple after
initialization? Do you think the tuple is actually changing, or are you really just 
initializing a new tuple that just *happens* to have the same variable name as the old 
tuple?

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use a `tuple` to store an arbitrary number of data elements (even elements of 
    mixed type).
  
  * In Python, there are mutable data structures and immutable data structures. The 
    `list` is mutable, whereas the `tuple` is immutable.

