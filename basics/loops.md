# Loop

Ci sono 2 tipi di loop:

- [While loops](#while-loops) ripete qualcosa fino a quando la condizione non e' piu' soddisfatta.
- [For loops](#for-loops) ripete qualcosa per ogni elementi di un iterabile

## While loops

```python
sta_piovendo = True
if sta_piovendo:
    print("Sta piovendo!")
```

```python
sta_piovendo = True
while sta_piovendo:
    print("Sta piovendo!")

print("Non sta piovendo piu'.")
```

Questo codice va all'infinito perche' la condizione `sta_piovendo` era la **condizione**.

```python
sta_piovendo = True
while sta_piovendo:
  print("Sta piovendo!")
    answer = input("Ancora? (y=yes, n=no) ")
    if answer == 'y':
        print("Oh well...")
    elif answer == 'n':
        sta_piovendo = False     # end the while loop
print("Non sta piovendo piu'.")
```

Possiamo interrompere i loop con `break`.

```python
while True:
    answer = input("Sta piovendo? (y=yes, n=no) ")
    if answer == 'y':
        print("Sta piovendo!")
    elif answer == 'n':
        print("Non sta piovendo piu'!")
        break   # end the loop
    else:
        print("Enter y or n.")
```

Altro esempio:
```python
>>> while True:
...     break
...     print("This is never printed.")
...
>>>
```

## For loops

Assumiamo di avere una lista e di voler stampare i valori al suo interno:

```python
stuff = ['hello', 'hi', 'how are you doing', 'im fine', 'how about you']

print(stuff[0])
print(stuff[1])
print(stuff[2])
print(stuff[3])
print(stuff[4])
```

L'output e' qualcosa come:

    hello
    hi
    how are you doing
    im fine
    how about you

Diventa scomodo farlo quando la lunghezza della lista cambia oppure e' troppo lunga. Possiamo usare il ciclo `for`.

```python
>>> for thing in stuff:
...     # this is repeated for each element of stuff, that is, first
...     # for stuff[0], then for stuff[1], etc.
...     print(thing)
...
hello
hi
how are you doing
im fine
how about you
>>>
```

Without the comments, that's only two simple lines, and one variable.
Much better than anything else we tried before.

```python
>>> for thing in stuff:
...     print(thing)
...
hello
hi
how are you doing
im fine
how about you
>>>
```

I loop possono essere utilizzati con tutto i tipi **iterabili** come stringhe, tuple, array.

```python
>>> for short_string in 'abc':
...     print(short_string)
...
a
b
c
>>> for item in (1, 2, 3):
...     print(item)
...
1
2
3
>>>
```

E' sempre buona norma non modificare il contenuto della lista che si sta iterando:

```python
>>> stuff = ['hello', 'hi', 'how are you doing', 'im fine', 'how about you']
>>> for thing in stuff:
...     stuff.remove(thing)
...
>>> stuff
['hi', 'im fine']
>>>
```

Basta usare una copia:

```python
>>> stuff = ['hello', 'hi', 'how are you doing', 'im fine', 'how about you']
>>> for thing in stuff.copy():
...     stuff.remove(thing)
...
>>> stuff
[]
>>>
```

[Previous](lists-and-tuples.md) | [Next](trey-hunner-zip-and-enumerate.md) |
[List of contents](../README.md#basics)
