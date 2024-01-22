# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 4.4. - Python Data Structures: `dict`

--------


## The `dict`

Another data structure available in Python (and perhaps the most useful of all!) is the 
dictionary, or `dict` (see 
<https://docs.python.org/3/tutorial/datastructures.html#dictionaries>). The `dict` is 
what is referred to as an *associative container* in that it defines a collection of 
*key:value* pairs. For example, suppose that we wish to maintain a file of information
on a particular project; using a `dict`, this can be structured as follows

    P1234 = {
        "project number": 1234,
        "project codename": "Artemis",
        "language": "Python 3.12.1",
        "contributors": ["Tom", "Dick", "Harry"]
    }

What results is the variable `P1234` of type `dict` which has the named attributes 
`"project number"`, `"project codename"`, `"language"`, and `"contributors"` (i.e., the 
*keys*). Each attribute then has an associated *value* (which can itself be of any type,
even another data structure!).  

To access the elements of a `dict`, one uses *keying*. For example

    print(P1234["project codename"])

yields

    Artemis

The `dict` is also mutable, so for example one could

    P1234["project codename"] = "Apollo"
    print(P1234["project codename"])

and see

    Apollo

You can also insert new key:value pairs by simply

    P1234["new key"] = "new value"

provided the given key does not already exist in the `dict`. To get a list of the keys 
in a `dict`, you can use the `keys()` method. together with a `list` type cast. For
example

    print(list(P1234.keys()))

The only real limitations are

  * Key must be either (a) numeric, or (b) immutable (Python strings are immutable).
  
  * Keys must be unique. That is, each key is associated with one, and only one, value 
    (a dictionary is said to be a *bijection*). In fact, the `dict` wouldn't make much 
    sense otherwise!


### Minimal Working Example

Let's try an MWE in which we declare and initialize a few dictionaries (call them
whatever you want and fill them with whatever you wish), and then experiment with them.

--------

## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use a `dict` to store an arbitrary number of key:value pairs (even values 
    of mixed type!).
  
  * Each `dict` key must be unique and immutable.
  
  * You can construct complex data structures by composing simpler ones (`list` of
    `dict`, `dict` of `dict`, `tuple` of `dict`, etc.).

