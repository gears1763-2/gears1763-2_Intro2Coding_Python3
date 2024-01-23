# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 4.1. - Python Data Structures: `list`

--------

## Motivation

If you were to undertake a formal program in computer science, you would no doubt be 
required to complete one or more courses in the area of data structures and algorithms. 
This highlights just how important these topics are in programming, as difficult 
problems are often made easier simply by choosing an appropriate data structure. As
such, it is no surprise that Python offers a number of basic data structures that are 
useful in solving more complex programming problems.


## The `list`

Let's say you have a programming problem in which you need to store more than a few 
elements of data. So far, we've been declaring variables that just hold a single element 
(referred to as *scalars*), so in order to store more than few elements of data, we 
would need to do something like  

    data_element_0 = 0
    data_element_1 = 1
    data_element_2 = 2
    .
    .
    .
    data_element_n = n

and so on. Of course, this is soul-crushingly tedious and very error prone. There must 
be a better way.  

Enter data structures, programming objects that group logically related data together in 
a manner that allows the programmer to interact with them as a single entity. To begin, 
we consider perhaps the most basic (and one of the most useful!) data structures in
Python; the `list` (see <https://docs.python.org/3/tutorial/datastructures.html>).  

Implementing the example given above using a `list` would look more like

    data_list = [0, 1, 2, ..., n]

That is, we declare a variable called `data_list` and initialize it with a listing of 
the data elements that we want it to contain. Note the square brackets (`[ ]`) on the 
right-hand side of the assignment; this indicates to Python that the type intent is a
`list`, and thus `data_list` is duck-typed accordingly. At this point, we can simply

    print(data_list)

to see the list contents printed out.  

Note that you can also initialize an empty list (suppose you don't know exactly what it
will contain!) by way of

    data_list = [ ]

This is fine, because a `list` can contain an arbitrary number of elements (even
elements of mixed type!), and it can change throughout the course of a script (it is 
said to be a *mutable* data structure).

## Indexing and Slicing

To access elements within a structure like a `list` (which is an *indexed structure*, 
also referred to as an *array* or a *vector*), one uses an *indexing scheme*. In Python, 
the indexing scheme is zero indexing using the `[i]` notation (and this is often the 
case in other programming languages too). This means

  * The first element of a `list` (say, `data_list`) is accessed by way of 
    `data_list[0]`.
  
  * The nth element of a `list` (say, `data_list`) is accessed by way of 
    `data_list[n - 1]`

So, for example, if

    data_list = [-1, 3.14, "potato", 8]

then

    print(data_list[0])
    print(data_list[1])
    print(data_list[2])
    print(data_list[3])

would yield

    -1
    3.14
    potato
    8

You can also slice a list, which is passing a range of indices when indexing. The return 
is then a sublist of the list. For example, using the `data_list` defined above,

    print(data_list[0 : 2])

would yield

    [-1, 3.14]

That is, the sublist of `data_list` which is comprised of the elements ranging from 
index 0 up to (but not including!) index 2.  

Note that you can get the number of elements in a list by using the length function
`len()`. For example

    print(len(data_list))

would yield

    4

So then, the first element of `data_list` is `data_list[0]`, and the last element of 
`data_list` is `data_list[len(data_list) - 1]` (and in Python, you can also use the 
indexing shorthand `data_list[-1]` to access the last element).


## Inserting and Deleting

As was mentioned before, the `list` is a *mutable* data structure (meaning it can change 
after it has been initialized). There are three main `list` *methods* for inserting 
elements into, and deleting elements from, a `list`; namely

  * `list.append(x)` adds an element with value `x` to the end of the list (this causes 
    the length of the list to increase by one).
  
  * `list.insert(i, x)` inserts an element with value `x` at index `i` (this causes the 
    sublist `[i : len(list)]` to "shift right" by one to make room for the insert, and as 
    a result the length of the list increases by one).
  
  * `list.pop(i)` removes the element at index `i` and returns its value (this 
    causes the sublist `[i + 1 : len(list)]` to "shift left" by one to "fill in the hole", 
    and as a result the length of the list decreases by one).


## Minimal Working Example

Let's try an MWE in which we declare and initialize a few lists (call them whatever you 
want and fill them with whatever you wish), and then experiment with indexing, slicing, 
and the insert and delete methods shown above.

In particular, try stuff like

  * Changing the value of an existing list element (for example, `my_list[0] = 9`), and 
    then printing the result.
  
  * Try some simple logic (for example, `print(my_list[-1] > 0)`, or 
    `print(len(my_list) < 100)`.
  
  * Try indexing outside the bounds of a list and see what happens (for example, 
    `my_list = [1, 2, 3]` and then `print(my_list[100])`).

Finally, an important experiment is something like the following

    x = [1, 2, 3]
    y = x
    
    y.append("LOL")
    y[0] = -1
    print(x)
    
    x.pop(1)
    print(y)

What do you expect would be printed out? ... what actually gets printed out? Why do you 
think this is?

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use a `list` to store an arbitrary number of data elements (even elements of 
    mixed type).
  
  * Python uses zero indexing and the `[i]` notation.
  
  * Shorthand for the last element of a list is `[-1]`.
  
  * You can get the number of elements in a list using the `len()` function.
  
  * You can extract sublists from a list by way of slicing.
  
  * You can insert and delete elements from a list using various list methods.
  
  * Initializing a list using a reference to another list can lead to unexpected 
    behaviour!

