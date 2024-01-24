# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 7.2. - Reading/Writing Files

--------


## Reading Files

If you work in any kind of admin job, then that probably involves an endless parade of 
documents, spreadsheets, etc.; office stuff. If this is the case, then one of the most 
useful things that Python can do for you is automate the more monotonous and repetitive 
aspects of office work.  

Starting simply, you can read a plain text file (line by line) into Python and then 
print it out like so

    with open("Lorem_Ipsum.txt", "r") as file_io:
        line_list = file_io.readlines()
    
    for line in line_list:
        print(line)

`Lorem_Ipsum.txt` has been provided, so give it a try! Can you see the loops and data 
structures in play here?  

Notice that the `open()` function (which is largely self-explanatory) takes two
arguments

  * The name of the file to be opened (in general, the *path* to the file).
  
  * Some other string ...?

The "some other string" piece is the *mode*, and some of the more common options are 

  * `r`: open for reading.
  
  * `w`: open for writing (will create the file if it does not exist, will overwrite if 
         if does).
  
  * `a`: open for appending (will write to the end of an existing file).

See <https://docs.python.org/3/library/functions.html#open>.

Finally, there is a new keyword in this example that warrants explanation: `with`.
Essentially, what this block does (for the case of this example) is incorporate 

  * Error handling if the file cannot be opened; and,
  
  * Closing the file once we're done with it.


## Aliasing

There is actually another new key word in the example above: `as`. This peratins to an 
often useful idea in Python called *aliasing*. In the example, we are aliasing the 
return from `open()` as `file_io`, so that we can refer to it later on. However, another 
common use of `as` is import aliasing. For example, suppose we have something like 

    import ReallyReallyReallyLongModuleName
    
    ReallyReallyReallyLongModuleName.functionOne()
    variable = ReallyReallyReallyLongModuleName.someOtherFunction()
    .
    .
    .

That can get tedious fast. But by import aliasing, one can do this

    import ReallyReallyReallyLongModuleName as RLM
    
    RLM.functionOne()
    variable = RLM.someOtherFunction()


## Writing Files

Starting simply, you can write to a plain text (line by line) like so

    line_list = [
        "I will read the docs.\n",
        "Exceptions are my friend.\n",
        "And a partridge in a pear tree.\n"
    ]

    with open("my_first_file.txt", "w") as file_io:
        for line in line_list:
            file_io.write(line)

See how you can split a `list` initialization by moving the square brackets? This can be 
helpful in keeping your scripts readable. Mind you, if you're trying to populate a
`list` with a large number of elements, its better to either use some kind of 
comprehension, or read it from a spreadsheet or something.  

Finally, notice the `\n` characters in `line_list`? Those are end of line characters, 
and the tell `write()` to start a new line. Try removing them and see how that changes 
things. Another such character that is often useful is the tab character `\t`. You can 
also use these to format the results of `print()`.

### Minimal Working Example

Let's try an MWE in which we first write a plain text file using the following structure

    [key]
    [value]
    [key]
    [value]
    .
    .
    .

Having saved the text file, next try reading it into a Python script and then use the 
contents to populate a `dict`. Be sure to print out the resulting `dict` to ensure that 
everything is behaving as intended.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can both read from and write to files using the `open()`, `readlines()`, 
    `write()` functions.
  
  * `with` is useful for keepin read/write code fairly concise.
  
  * Aliasing is a thing, and it can help to make scripts more concise.
