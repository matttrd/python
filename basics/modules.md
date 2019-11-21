# Moduli

I moduli sono programmi o funzioni gia' scritte in altri file che vogliamo utilizzare. Per esempio se vogliamo generare un numero interno random:

```python
>>> import random
>>> random.randint(1, 3)
3
>>> random.randint(1, 3)
1
>>> random.randint(1, 3)
3
>>> random.randint(1, 3)
2
>>> random.randint(1, 3)
2
>>>
```


## Come importare

Possiamo importare nostri moduli oppure moduli gia' installati. Per creare un module e' sufficiente creare un file 'my_module.py' che contiene le funzioni necessarie.


Ci sono vari modi di importare:
```python
>>> import random
```
importa tutto il modulo random. Se vogliamo importare solo la funzione `randint` possiamo fare:
```python
>>> from random import randint
>>> randint(1, 3)
3
```

Se vogliamo importare tutte le funzioni del modulo invece:
```python
>>> from random import *
>>> randint(1, 3)
3
```


## Moduli standard


### Random numbers

La documentazione ufficiale e'
[qui](https://docs.python.org/3/library/random.html).

```python
>>> import random
>>> random.randint(1, 3)      # 1, 2 or 3
3
>>> colors = ['red', 'blue', 'yellow']
>>> random.choice(colors)     # choose one color
'red'
>>> random.sample(colors, 2)  # choose two different colors
['yellow', 'red']
>>> random.shuffle(colors)    # mix the color list in-place
>>> colors
['yellow', 'red', 'blue']
>>>
```


### Matematica

La libreria ufficiale e' [qui](https://docs.python.org/3/library/math.html).

```python
>>> import math
>>> math
<module 'math' (built-in)>
>>> math.pi                  # approximate value of π
3.141592653589793
>>> math.sqrt(2)             # square root of 2
1.4142135623730951
>>> math.radians(180)        # convert degrees to radians
3.141592653589793
>>> math.degrees(math.pi/2)  # convert radians to degrees
90.0
>>> math.sin(math.pi/2)      # sin of 90 degrees or 1/2 π radians
1.0
>>>
```

### Tempo

La libreria ufficiale e' [qui](https://docs.python.org/3/library/time.html).

```python
>>> import time
>>> time.sleep(1)   # wait one second
>>> time.time()     # return time in seconds since beginning of the year 1970
1474896325.2394648
>>> time.strftime('%d.%m.%Y %H:%M:%S')  # format current time nicely
'07.04.2017 19:08:33'
>>>
```

### Sistema operativo

Il modulo "os" contiene funzioni per interagire con il sistema operativo.

La libreria ufficiale e' [qui](https://docs.python.org/3/library/os.html).

```python
>>> import os
>>> os.getcwd()        # short for "get current working directory"
'/home/akuli'
>>> os.mkdir('stuff')  # create a folder, short for "make directory"
>>>
>>> os.path.isfile('hello.txt')  # check if it's a file
True
>>> os.path.isfile('stuff')
False
>>> os.path.isdir('hello.txt')   # check if it's a directory
False
>>> os.path.isdir('stuff')
True
>>> os.path.exists('hello.txt')  # check if it's anything
True
>>> os.path.exists('stuff')
True
>>>
>>> # this joins with '\\' on windows and '/' on most other systems
>>> path = os.path.join('stuff', 'hello-world.txt')
>>> path
'stuff/hello-world.txt'
>>> with open(path, 'w') as f:
...     # now this goes to the stuff folder we created
...     print("Hello World!", file=f)
...
>>> os.listdir('stuff')  # create a list of everything in stuff
['hello-world.txt']
>>>
```

[Previous](files.md) | [Next](numpy.md) |
[List of contents](../README.md#basics)
