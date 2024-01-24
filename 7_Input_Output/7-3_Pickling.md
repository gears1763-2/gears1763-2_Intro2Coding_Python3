# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 7.3. - Pickling

--------


## Pickling

Things like documents and spreadsheets are nice in the sense that they are human
readable. That said, they do suffer from a downside in the context of programming, and 
that is they can be rather heavy (and, at times, have some weird formatting gotchas).
So, for example, using such files to save the state of a Python session for later use is
not the best solution. This is also complicated by the fact that the `open()` and
`readlines()` approach we saw previously will only ever return strings (like `input()`),
so there's the added complexity of type casting appropriately.

Fortunately, Python does offer a *data persistence* solution in the form of the
*pickle* module (think pickling food for long term storage), and using it is (like most 
everything in Python) pretty easy. See <https://docs.python.org/3/library/pickle.html>.

For example, suppose we have a `dict` populated with data that came from
`veryExpensiveFunction()` (think a function that takes a *long* time to finish). We
might pickle the state of the `dict` as follows

    import pickle
    
    with open("data_dict.pkl", "wb") as pickle_io:
        pickle.dump(data_dict, pickle_io)

This will create a new file called `data_dict.pkl` which contains our "pickled" `dict`. 
Note that for this to work, you need to be `open()`-ing in *binary* write mode (that's 
the `"wb"`).

Now, in any future script, we can load the pickled `dict` and pick right back up where 
we left off (in particular, we don't need to run `veryExpensiveFunction()` again!). To 
do this, we can

    import pickle
    
    with open("data_dict.pkl", "rb") as pickle_io:
        data_dict = pickle.load(pickle_io)
    
    print(data_dict)

Notice we're `open()`-ing in *binary* read mode.


### Minimal Working Example

Let's try an MWE in which we write one script to initialize and pickle some data
structure, and then write another to load it. For example, try reading 
`Lorem_Ipsum.txt` into a `list` and pickling it (script 1), then load it and print it
line by line (script 2).

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can save and recover the state of the variables / data structures in a Python 
    session using the `pickle` module.
