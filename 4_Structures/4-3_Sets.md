# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 4.3. - Python Data Structures: `set`

--------


## The `set`

Another data structure available in Python is the `set` (see 
<https://docs.python.org/3/tutorial/datastructures.html#sets>). The `set` is mutable 
like a `list` (in that it has insertion and deletion methods), but it is not indexed. 
Trying to use the same indexing and slicing interface that you can for a `list` or a 
`tuple` will not work with a `set` (a `set` is said to be *unordered*).  

However, the `set` does have one unique (and very useful!) property; repeated values
are not allowed, and will be filtered out at initialization.  

For example, suppose I have

    data_list = ["yes", "no", "no", "yes", 0, 1, 1, 0, 1, 1, -1]

If I have a problem in which I need to know how many *distinct* values are contained in 
`data_list`, then I can use a `set` type casting to get that. For instance

    data_set = set(data_list)
    print(data_set)
    print(len(data_set))

would yield

    {0, 1, 'no', -1, 'yes'}
    5

Note that sets use the curly braces ('{ }') syntax, so you can also initialize a `set` 
like this

    data_set = {1, 2, 3}


### Minimal Working Example

Let's try an MWE in which we declare and initialize a few sets (call them whatever you 
want and fill them with whatever you wish), and then experiment with them. Try both 
literal initialization and initialization by way of type casting.

--------

## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use a `set` to store an arbitrary number of data elements (even elements of 
    mixed type).
  
  * The `set` does not support indexing and slicing, but is nonetheless mutable (using 
    various `set` methods).
  
  * Repeated values are not allowed in a `set`, and are filtered out at initialization. 
    This makes the `set` useful for enumerating all the distinct values contained in a 
    `list` or `tuple`.

