# Liste e tuple

## Perche' usare liste?

```python
name1 = 'Matteo'
name2 = 'Luca'
name3 = 'Davide'
name4 = 'Marco'
name5 = 'Giovanni'

name = input("Inserire il nome: ")
if name == name1 or name == name2 or name == name3 or name == name4 or name == name5:
    print("Ti conosco")
else:
    print("Scusa, non ti conosco")
```

Ma non possiamo fare cosi' tante volte, diventa scomodo.

## Definizione della lista

```python
nomi = ['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni']
```
La variabili nomi punta ad una lista di valori. Le liste possono contenere anche tipi diversi.

## Oerazioni su list

```python
>>> nomi = ['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni']
>>> nomi
['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni']
>>>
```
Molto simile a quello che abbiamo vist oper le strighe:

```python
>>> len(nomi)   # lunghezza della lista
5
>>> nomi + ['Alessandro']   # create a new list with me in it
['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni','Alessandro']
>>> ['Matteo', 'Luca'] * 2    # repeating
['Matteo', 'Luca', 'Matteo', 'Luca']
>>>
```

Slicing e indexing:
```python
>>> nomi[:2]    # first two nomi
['Matteo', 'Luca']
>>> nomi[0]     # the first name
'Matteo'
>>>
```

Controllare se un item compare nella lista usando `in`.

```python
>>> 'Alice' in nomi
False
>>> 'Davide' in nomi
True
>>>
```

We can't use this for checking if a list of nomi is a part of
our name list.

Qui trovate i [metodi fondamentali](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists) per le liste.
Le piu' comuni sono append, extend and remove.
`append` aggiunge un item alla lista, `extend` aggiungi item multipli da un'altra lista e `remove` rimuove un item.

```python
>>> nomi
['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni']
>>> nomi.remove('Luca')
>>> nomi.remove('Matteo')
>>> nomi
['Davide', 'Marco', 'Giovanni']
>>> nomi.append('Alice')  
>>> nomi
['Davide', 'Marco', 'Giovanni', 'Alice']
>>> nomi.extend(['Riccardo', 'Beatrice'])
>>> nomi
['Davide', 'Marco', 'Giovanni', 'Alice','Riccardo', 'Beatrice']
>>>
```

Da notare che remove rimuove solo il primo match che trova.
Se dobbiamo rimuovere tutti i match dobbiamo usare un for loop (lo vedremo nel [prossimo capitolo](loops.md)).

```python
>>> nomi = ['Marco', 'Marco', 'Luca']
>>> while 'Marco' in nomi:
...     nomi.remove('Marco')
...
>>> nomi
['Luca']
>>>
```

Possiamo anche assegnare sfruttando indexing e slicing.

```python
>>> nomi = ['Matteo', 'Luca', 'Davide', 'Marco', 'Giovanni']
>>> nomi[1] = 'Alice'   # sostituisce Luca with Alice
>>> nomi
['Matteo', 'Alice', 'Davide', 'Marco', 'Giovanni']
>>>
```

Le liste **possono cambiare in-place**.


## Confronti

```python
>>> a = [1, 2, 3]
>>> b = a
>>> b.append(4)
>>> a    # this changed also!
[1, 2, 3, 4]
>>>
```

Qui cambia anche a. Perche? a e b Puntano allo stesso oggetto a causa di `b = a`.

`is` puo' essere usato per controllare che siano la **stessa** cosa.

```python
>>> a is b
True
>>>
```

Infatti abbiamo:

```python
>>> [] is []
False
>>> [1, 2, 3] is [1, 2, 3]
False
>>>
```

Per assegnare ad una nuova lista (duplicata) dobbiamo usare `.copy()`

```python
>>> a = [1, 2, 3]
>>> b = a.copy()
>>> b is a
False
>>> b.append(4)
>>> b
[1, 2, 3, 4]
>>> a
[1, 2, 3]
>>>
```

## Tuple

Le tuple sono come lista ma sono immutabili e si usano le parentesi tonde:

```python
>>> thing = (1, 2, 3)
>>> thing
(1, 2, 3)
>>> thing = ()
>>> thing
()
>>>
```

Per creare una tupla che contiene un solo elemento dobbiamo usare  `(item,)` invece di `(item)`:

```python
>>> (3)
3
>>> (3,)
(3,)
>>> (1 + 2) * 3
9
>>> (1 + 2,) * 3
(3, 3, 3)
>>>
```

Append non puo' essere usato perche' le tuple sono immutabili:

```python
>>> my_tuple = (1, 2, 3)
>>> my_tuple.append(4)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'tuple' object has no attribute 'append'
>>>
```

[Previous](strings.md) | [Next](loops.md) |
[List of contents](../README.md#basics)
