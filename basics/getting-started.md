# Primi passi con Python

[Lancia Python](installing-python.md).

Il simbolo `>>>` significa che il comando e' andato a buon fine e siamo dentro all'ambiente python. Da cui possiamo lanciare i comandi desiderati.

```python
>>> hello
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'hello' is not defined
>>>
```
Perche'? `hello` e' vista come una variabile e non come una stringa. Ci ritorneremo in un attimo.

```python
>>> 123
123
>>> -123
-123
>>> 3.14
3.14
>>> -12.3
-12.3
>>>
```

Attendi ai punto decimali. Vengono definiti dal punto '.'.
```python
>>> 3,14
(3, 14)
>>>
```
Come vedremo la virgola serve per le tuple e le liste per separare gli oggetti.

## Commenti

**I commenti sono semplice testo utile a descrivere il codice**. Possono essere creati con il simbolo
`#` and poi il testo.

```python
>>> 1 + 2     # somma
3
>>>
```

## Stringhe

```python
>>> 'hello'
'hello'
>>> "questa e' una prova"
"questa e' una prova"
>>>
```
Le stringhe posso ussere definite sia dalla single quote che dalla double quote. Le doppie sono utili quando si usano le singole all'interno della stringa.

Le stringhe possono essere concatenate usando `+` o ripetute usando `*`:

```python
>>> "hello" + "world"
'helloworld'
>>> "hello" * 3
'hellohellohello'
>>>
```

## Calcolatrice


```python
>>> 17 + 3
20
>>> 17 - 3
14
>>> 17 * 3
51
>>> 17 / 3
5.666666666666667
>>>
```

**Nota importante**: qui python ritorna il risultato. Nei programmi veri all'interno dei file `.py` e' necessario usare `print`.

Altri esempi:

```python
>>> 1 + 2 * 3        # 2 * 3 ha la priorita'
7
>>> (1 + 2) * 3      # 1 + 2 ha la priorita'
9
>>>
```

[Previous](installing-python.md) | [Next](variables.md) |
[List of contents](../README.md#basics)
