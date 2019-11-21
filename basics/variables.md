# Variabili

In Python le variabili **puntano ai valori**.

```python
>>> a = 1   # assegnazione a 1
>>> b = 2   # altra variabile
>>> a       # ottieni il valore puntato da a
1
>>> b
2
>>>
```

Ovviamente possiamo cambiare il valore delle variabili:
```python
>>> a = 2    # make a point to 2 instead of 1
>>> a
2
>>>
```

Manipolazioni di variabili:

```python
>>> a = 1
>>> b = a  # questo rende b uguale a 1, non a
>>> a = 5
>>> b      # b non cambia anche se a e' cambiato
1
>>>
```

Alcune note:

- Le variabili puntano a valori, **non puntano ad altre variabili**.
- Una variabile ha valore univoco.
- I valori ai quali le variabili puntano posso puntare anche ad altri valori. Lo vedremo con le
  [liste](lists-and-tuples.md).

Le variabili sono case-sensitive

```python
>>> thing = 1
>>> THING = 2
>>> thIng = 3
>>> thing
1
>>> THING
2
>>> thIng
3
>>>
```

Ci sono dei nomi di variabile che non posso essere utilizzate perche' sono **keywords** speciali.

Per avere una lista completa basta lanciare `help('keywords')`.

```python
>>> if = 123456
  File "<stdin>", line 1
    if = 123456
       ^
SyntaxError: invalid syntax
>>>
```

Riassegnazione della variabile:

```python
>>> a = 1
>>> a = a + 1
>>> a
2
>>>
```

Per accorciare operazioni sulla stessa variabile si possono usare i simboli `+=`, `-=`, `*=` e `/=` instead invece di `+`, `-`, `*` e
`/`.

```python
>>> a += 2          # a = a + 2
>>> a -= 2          # a = a - 2
>>> a *= 2          # a = a * 2
>>> a /= 2          # a = a / 2
>>>
```

Vale anche per le stringhe.

```python
>>> a = 'hello'
>>> a *= 3
>>> a += 'world'
>>> a
'hellohellohelloworld'
>>>
```

## Booleans
Ci sono due valori Booleani True e False. `=` riguarda l'assegnazione e `==` e' la comparazione.
`a = 1` setta a ad 1, e `a == 1` controllo se a e' uguale a 1.

```python
>>> a = 1
>>> a == 1
True
>>> a = 2
>>> a == 1
False
>>>
```

## None

None e' un tipo speciale che significa "nulla". E' spesso usato come default ed e' molto utile per capire quando una variabile e' stata cambiata e molto altro.

Esempio:

```python
>>> a = None
>>> abs
>>>
```

Il prompt non torna nulla.

Se vuoi visualizzare espicitamente il valore usa:

```python
>>> print(a)
None
>>>
```

## Operatori di confronto

| Usage     | Description                       | True examples         |
|-----------|-----------------------------------|-----------------------|
| `a == b`  | a is equal to b                   | `1 == 1`              |
| `a != b`  | a is not equal to b               | `1 != 2`              |
| `a > b`   | a is greater than b               | `2 > 1`               |
| `a >= b`  | a is greater than or equal to b   | `2 >= 1`, `1 >= 1`    |
| `a < b`   | a is less than b                  | `1 < 2`               |
| `a <= b`  | a is less than or equal to b      | `1 <= 2`, `1 <= 1`    |

Comparazioni multiple:

| Usage     | Description                               | True example                      |
|-----------|-------------------------------------------|-----------------------------------|
| `a and b` | a is True and b is True                   | `1 == 1 and 2 == 2`               |
| `a or b`  | a is True, b is True or they're both True | `False or 1 == 1`, `True or True` |

`not` e' usato per la negazione. Se `value` e' True, `not value` e' False, e se `value` e' False, `not value` e' True.

Esiste anche `is`, ma attenzione a non usarlo come sostituto a `==`. Lo vedremo meglio dopo.

[Previous](the-way-of-the-program.md) | [Next](using-functions.md) |
[List of contents](../README.md#basics)
