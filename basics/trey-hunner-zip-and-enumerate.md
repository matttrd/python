# enumerate e zip
## zip
Il comando `zip` ha la funzionalita' di accoppiare due iterabili:
```python
>>> list_1 = ['a', 'b', 'c']
>>> list_2 = [1,2,3]
>>> a = zip(list_1,list_2)
>>> zip(list_1,list_2)
<zip object at 0x103c57408>
>>> list(zip(list_1,list_2))
[('a', 1), ('b', 2), ('c', 3)]
```

Possiamo iterare su piu' valori:

```python
>>> items = [('a', 1), ('b', 2), ('c', 3)]
>>> for pair in items:
...     a, b = pair
...     print(a, b)
...
a 1
b 2
c 3
>>>
```
## enumerate
Enumera gli elementi della lista. E' molto comodo quando dobbiamo tener traccia dell'indice.
```python
>>> for i,v in enumerate(list_1):
...     print(i, v)
...
0 a
1 b
2 c
>>>
```


[Previous](loops.md) | [Next](dicts.md) |
[List of contents](../README.md#basics)
