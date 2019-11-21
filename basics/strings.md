# Alcune operazioni con le stringhe


The stringhe Python sono [immutabili](https://docs.python.org/3/glossary.html#term-immutable).
Questo significa che non possono essere cambiate in-place.

```python
our_string = 'Hello World'
```

## Slicing
Lo slicing funziona per diversi tipi: stringhe, liste, array (lo vedremo).
Possiamo selezionare una parte della stringa:

```python
>>> our_string[2:5]
'llo'
>>>
```

La sintassi e' `some_string[start:end]`.

Solitamente in Python end rappresenta l'elemento successivo all'ultimo compreso.

Cosa succede con valori negativi?
```python
>>> our_string[-5:-2]
'orl'
>>>
```

Parte a contare dalla fine (parte dal quint'ultimo e va fino al penultimo).

Se non specifichiamo l'inizio, il default e' 0, e non specifichiamo end viene settato al valore pari alla lunghezza della stringa:

```python
>>> our_string[1:]
'ello World!'
>>> our_string[:-1]
'Hello World'
>>>
```

## Indexing
Selezionare un elemento della stringa:

```python
>>> our_string[1]
'e'
>>>
```
**Con Python tutto parte dall'indice 0**. Il primo carattere e' `our_string[0]`, il secondo `our_string[1]`, e cosi' via.

```python
>>> our_string[0]
'H'
>>> our_string[1]
'e'
>>> our_string[2]
'l'
>>> our_string[3]
'l'
>>> our_string[4]
'o'
>>>
```

E con valori negativi?

```python
>>> our_string[-1]
'!'
>>>
```

Otteniamo l'ultimo. Attenzione: `our_string[-1]` e' l'ultimo ma `our_string[1]` non e' il primo.

Questo perche' -0 e 0 sono uguali.

## String methods

Ci sono molti metodi per manipolare stringhe (https://docs.python.org/3/library/stdtypes.html#string-methods)

Alcuni esempi:
```python
>>> our_string.upper()
'HELLO WORLD!'
>>> our_string.lower()
'hello world!'
>>> our_string.startswith('Hello')
True
>>> our_string.endswith('World!')
True
>>> our_string.endswith('world!')  # Python is case-sensitive
False
>>> our_string.replace('World', 'there')
'Hello there!'
>>> our_string.replace('o', '@', 1)   # only replace one o
'Hell@ World!'
>>> '  hello 123  '.lstrip()    # left strip
'hello 123  '
>>> '  hello 123  '.rstrip()    # right strip
'  hello 123'
>>> '  hello 123  '.strip()     # strip from both sides
'hello 123'
>>> '  hello abc'.rstrip('cb')  # strip c's and b's from right
'  hello a'
>>> our_string.ljust(30, '-')
'Hello World!------------------'
>>> our_string.rjust(30, '-')
'------------------Hello World!'
>>> our_string.center(30, '-')
'---------Hello World!---------'
>>> our_string.count('o')   # it contains two o's
2
>>> our_string.index('o')   # the first o is our_string[4]
4
>>> our_string.rindex('o')  # the last o is our_string[7]
7
>>> '-'.join(['hello', 'world', 'test'])
'hello-world-test'
>>> 'hello-world-test'.split('-')
['hello', 'world', 'test']
>>> our_string.upper()[3:].startswith('LO WOR')  # combining multiple things
True
>>>
```

## Formattazione di stringhe



```python
name = 'Matteo'
country = 'Italia'
>>> "Hello {}.".format(name)
'Hello Matteo.'
>>> "Il mio nome e' {} e vivo in {}.".format(name, country)
"Il mio nome e' Matteo e vivo in Italia"
>>>
```


## Altre cose

Possiamo usare `in` e `not in` per controllare se una stringa contiene una stringa.

```python
>>> our_string = "Hello World!"
>>> "Hello" in our_string
True
>>> "Python" in our_string
False
>>> "Python" not in our_string
True
>>>
```

Possiamo ottenere la lunghezza di una stringa con `len`:

```python
>>> len(our_string)
12
>>> len('')    
0
>>> len('\n')   
1
>>>
```

Possiamo convertire strighe, interi e float l'un l'altro usando `str`, `int` and `float`. Non sono proprio funzioni ma qui le usiamo come funzioni.

```python
>>> str(3.14)
'3.14'
>>> float('3.14')
3.14
>>> str(123)
'123'
>>> int('123')
123
>>>
```

[Previous](if.md) | [Next](lists-and-tuples.md) |
[List of contents](../README.md#basics)
