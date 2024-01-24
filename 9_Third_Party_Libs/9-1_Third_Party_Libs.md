# Intro to Coding (getting started with Python 3)

    Anthony Truelove MASc, P.Eng.
    github: gears1763-2


## 9.1. - Third Party Libraries

--------


## Motivation

Python has been around for a while (it first appeared in 1991), and over the years it
has developed a large and dedicated following (especially in the domains of scientific
computing, data analysis, and AI / machine learning). In this section, the Python 
package installer `pip` is introduced, which is a command line tool that allows one to 
install any third party libraries (called *packages*) that are hosted in the official 
Python Package Index `PyPI` (see <https://pypi.org/>). A few notable examples are
presented here, namely `numpy`, `scipy`, `pandas`, `matplotlib`, and `keras`.


## The Python Package Installer: `pip`

See <https://pypi.org/project/pip/>  

When you installed your Python interpreter, it almost certainly included an
installation of `pip`. This command line tool makes installing third party libraries a 
breeze (provided they're hosted on `PyPI`). For example, to install `[package name]`, 
you simply

    pip install [package name]

in the command prompt. Once you do that, you should be able to 

    import [package name]

in any of your scripts.


## Numerical Python: `numpy`

See <https://numpy.org/>  

The Numerical Python (`numpy`) package is perhaps the most popular, and it provides the 
programmer with access to lower-level (and fast!) numeric data structures such as the 
`numpy` array. To install, you need only 

    pip install numpy

Once that's done, you can experiment with it. For example.

    import numpy as np
    
    float_array = np.linspace(1, 100_000, 100_001)
    print(float_array)
    
    print(np.min(float_array))
    print(np.mean(float_array))
    print(np.std(float_array))
    print(np.max(float_array))

`numpy` also allows one to *vectorize* numeric operations (think looping over a numeric 
`list` and performing the same operation on each element; using "vanilla" Python this 
is rather slow, but using `numpy` vectorization can speed things up dramatically).


## Scientific Python: `scipy`

See <https://scipy.org/>  

The Scientific Python (`scipy`) package is for you if you want to do things like
modelling (fitting curves to data, for example), simulation (generating realizations of 
a random system), and optimization (finding the best possible solution to a given
problem). To install, you need only

    pip install scipy

Once that's done, you can experiment with it. For example, how about some basic
interpolation?

    import random
    import scipy.interpolate as spi
    
    x_data = [x for x in range(1, 101)]
    y_data = [3 * x * x - 2 * x + 1 for x in x_data]
    
    yInterp1d = spi.interp1d(x_data, y_data)
    
    for i in range(1, 100):
        random_x = random.uniform(1, 100)
        print("x =", random_x)
        print("y(x) =", yInterp1d(random_x)


## Data Analysis: `pandas`, the Python "panel data" Package

See <https://pandas.pydata.org/>  

Need to analyze volumes of data in a variety of formats? Looking to do formal analytics
(like descriptive, predictive, or prescriptive)? `pandas` is for you. To install, you 
need only

    pip install pandas

`pandas` is huge, so we won't give an example here. The `pandas` community is pretty big, 
so there is no shortage of how-tos and examples online.


## Data Visualization: `matplotlib`, the MATLAB-like Plotting Library

See <https://matplotlib.org/>  

Need to generate graphics from data, for the sake of visualization? Introducing
`matploblib` (also, very, very popular). To install, you need only 

    pip install matplotlib

For example, not sure what the data in the `scipy` example looks like? Generate a quick 
plot like so

    import matplotlib.pyplot as plt
    
    x_data = [x for x in range(1, 101)]
    y_data = [3 * x * x - 2 * x + 1 for x in x_data]
    
    plt.figure()
    plt.grid()
    plt.plot(x_data, y_data)
    plt.xlabel("x")
    plt.ylabel("y")
    plt.show()


## Artificial Intelligence and Machine Learning: `keras`

See: <https://keras.io/>  

Want to get up to your elbows in AI and machine learning? `keras`. To install, you need 
only

    pip install keras

Want an example? How about diving right in to image recognition of hand written digits 
using an artificial neural network? See
<https://nextjournal.com/gkoehler/digit-recognition-with-keras>.

### Minimal Working Example

There are too many options here. Just pick one or two of the third party libraries
listed above (based on your interests), `pip install` them, and start playing around. 
Remember, good docs are your friend; give them a read.

--------


## Consolidation 

From this quick lesson, you should have picked up the following bits of knowledge:  

  * You can use `pip` to install third party libraries for use in your scripts. This 
    massively expands the capabilities of Python, particularily for niche applications.
  
  * There are many, many third party libraries available for Python. The entire Python 
    ecosystem is vast, and it continues to grow and evolve.
