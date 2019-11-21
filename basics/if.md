# If, else e elif

## Usare if

Adesso sappiamo usare True e False.

```python
>>> 1 == 1
True
>>> 1 == 2
False
>>>
>>> sta_piovendo = True
>>> sta_piovendo
True
>>>
```

Molte volte vogliamo eseguire un'azione condizionatamente ad un certo evento: "Se piove, allora vado in macchina".

```python
>>> sta_piovendo = True
>>> if sta_piovendo:
...     print("Sta piovendo, andiamo in macchina!")
...
Sta piovendo, andiamo in macchina!
>>> sta_piovendo = False
>>> if sta_piovendo:
...     print("Sta piovendo, andiamo in macchina!")        # non accade nulla
...
>>>
```
**Nota importante**. Il codice in Python deve essere **identato**. Basta premere il tasto tab key, o lo spazio 4 volte. Dove serve identazione?
- if, else, ecc.
- Funzioni
- for

## Using else

`else` e' semplicemente il nostro altrimenti:

```python
sta_piovendo = True

if sta_piovendo:
    print("Sta piovendo!")
else:
    print("Non sta piovendo.")
```

Attenzione che il codice viene controllato solo una volta. Il seguente codice non esegue il print:

```python
>>> sta_piovendo = True
>>> if sta_piovendo:
...     sta_piovendo = False
... else:
...     print("Non sta piovendo.")
...
>>>
```

## Evitare tanti livelli di identazione con elig

Quando abbiamo molte condizioni da controllare:

```python
print("Hello!")
word = input("Enter something: ")

if word == "hi":
    print("Hi to you too!")
else:
    if word == "hello":
        print("Hello hello!")
    else:
        if word == "howdy":
            print("Howdyyyy!")
        else:
            if word == "hey":
                print("Hey hey hey!")
            else:
                if word == "gday m8":
                    print("Gday 4 u 2!")
                else:
                    print("I don't know what", word, "means.")
```

Invece di usare  `else`, possiamo usare `elif`, che e' la shortcut per `else if`:

```python
print("Hello!")
word = input("Enter something: ")

if word == "hi":
    print("Hi to you too!")
elif word == "hello":
    print("Hello hello!")
elif word == "howdy":
    print("Howdyyyy!")
elif word == "hey":
    print("Hey hey hey!")
elif word == "gday m8":
    print("Gday 4 u 2!")
else:
    print("I don't know what", word, "means.")
```

Da notare che l'interprete va in ordine e cade nella prima condizione soddisfatta:


```python
if 1 == 1:
    print("hello")
elif 1 == 2:
    print("this is weird")
else:
    print("world")
```

Cosa printa?

[Previous](using-functions.md) | [Next](handy-stuff-strings.md) |
[List of contents](../README.md#basics)
