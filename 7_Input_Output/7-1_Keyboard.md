# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 7.1. - Keyboard Input

--------


## Motivation

Once you get a handle on writing Python scripts, it is time to start venturing into 
interacting with things other than the script itself. For example, suppose you run a 
small business and you would like to better automate your record keeping. You could 
certainly do that using Python, but not without getting comfortable with input/output 
(IO) functionality first. This functionality will be the focus of this section of the 
course.


## Keyboard Input

In Python, it is quite easy to gather input from the keyboard using the `input()` 
function. The way this function works is

  * When called, the input function records the keystrokes entered by the user.
  
  * As soon as [Enter] is pressed, the keystrokes are then returned as a `str`.

So, for example

    name = input("Enter name: ")
    print("Hello,", name)

does what you might expect. Note that passing an argument to `input()` is optional, but 
it usually makes sense to do so (the argument defines the prompt that the user sees).  

You can also use `input()` to cause your script to pause; something like

    input("Press Enter to continue ...")

which can be useful now and then.

Finally, an important thing to keep in mind here is that *`input()` returns a `str`*. So, 
if the intent is to gather numeric input, then you will need to type cast the return 
from `input()` accordingly.


### Minimal Working Example

Let's try an MWE like so:

  1. Initialize a blank user account. Try using a `dict` with any number of keys for
     this (but be sure to include at least `username` and `password`). Leave the values
     "blank" for now (so initialize to 0 for numeric, and "" for text).
  
  2. To populate `username`, prompt the user using `input()`.
  
  3. To populate `password`, you can also prompt the user using `input()`. However, you 
     should NEVER, NEVER store sensitive information like a password in plain text. So, 
     rather than just a simple `input()`, do the following instead
     
        user_account["password"] = hashlib.sha256(bytes(input("Enter password: "), "utf-8")).hexdigest()
    
     This is jumping ahead a bit in terms of complexity, but it's also a matter of data 
     security, and data security is important. What's going on here is that a *hash* of 
     the password, rather than the password itself, is being stored. Essentially a hash 
     is a one way function: given only the password, you can always generate the hash, 
     but given only the hash, it's practically impossible to recover the password that 
     generated it.
    
     Of course, you will need to `import hashlib` for this to work!  
     See <https://docs.python.org/3/library/hashlib.html>.
    
  4. `print()` the user account to see the end result.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can gather user input from the keyboard using the `input()` function.
  
  * The `input()` function always returns a `str`, so be sure the type cast as 
    necessary.
