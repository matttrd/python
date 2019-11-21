# Funzioni

Adesso sappiamo come mostrare testo.

```python
>>> 'Hello!'
'Hello!'
>>>
```

Se vogliamo vedere il testo senza `''` possiamo usare `print`:

```python
>>> print('Hello!')
Hello!
>>>
```

## Cosa sono le funzioni?

Partiamo da `print`:

```python
>>> print
<built-in function print>
>>>
```

Come vediamo print is a function built-in. Quest'ultimo termine significa che e' una funzione di base.

In generale le funzioni accettato degli argomenti all'interno delle parentesi e possibilmente restituiscono un risultato oppure modificano delle variabili:

`function()` chiama una funzione senza argomenti mentre
    `function(1, 2, 3)` chiama una fun con tre argomenti.


## Altri dettagli su print

Possiamo printare anche una riga vuota.

```python
>>> print()

>>>
```

In Python, `\n` e' il carattere 'a capo' (newline):

```python
>>> print('hello\nworld')
hello
world
>>>
```

Possiamo anche fornire piu' di un argomento, separando con la virgola:

```python
>>> print("Hello", "World!")
Hello World!
>>>
```

## Nomi di variabili and built-in

[Abbiamo visto](variables.md) che if non e' un nome di variabile valido:

```python
>>> if = 123
  File "<stdin>", line 1
    if = 123
       ^
SyntaxError: invalid syntax
>>>
```

Ma `print` e `input` non sono keywords: possiamo usarlo come nomi di variabile?

```python
>>> print = "hello"
>>> print
'hello'
>>>
```

Possiamo ma poi non riusciamo ad usare la funzione print:

```python
>>> print("Hello World!")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object is not callable
>>>
```

La maggiorparte degli editor mostra i built-in con un colore speciale.


[Previous](variables.md) | [Next](if.md) |
[List of contents](../README.md#basics)
