# Defining custom functions

Quando si devo fare operazioni ripetute tante volte ma con argomenti diversi e' utile usare delle funzioni


Esempio di una funzione che non fa nulla:

```python
>>> def do_nothing():
...     pass
...
>>> do_nothing
<function do_nothing at 0x103a14048>
>>>
```

Altro esempio:
```python
>>> def print_ciao():
...     print("ciao!")
...
>>> print_ciao()
ciao!
>>>
```

Le variabili definite all'interno della funzione sono riconosciute sono all'interno di quello scope:

```python
>>> def get_username():
...     username = input("Username: ")
...
>>> get_username()
Username: me
>>> username
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'username' is not defined
>>>
```

Sintassi:

```python
def add_numbers(x,y):
   sum = x + y
   return sum
```

E se volessimo passare un numero variabile di argomenti?
Usiamo `*args` e `**kwargs`. `*args` rappresenta Non-Keyword Arguments mentre `**kwargs` Keyword Arguments. `*args` e' una tupla mentre `**kwargs` un dizionario.

```python
def adder(*num):
    sum = 0

    for n in num:
        sum = sum + n
    print("Sum:",sum)
adder(3,5)
adder(4,5,6,7)
adder(1,2,3,5,6)

def intro(**data):
    print("\nData type of argument:",type(data))
    for key, value in data.items():
        print("{} is {}".format(key,value))
intro(Firstname="Sita", Lastname="Sharma", Age=22, Phone=1234567890)
intro(Firstname="John", Lastname="Wood", Email="johnwood@nomail.com", Country="Wakanda", Age=25, Phone=9876543210)
```

[Previous](dicts.md) | [Next](larger-program.md) |
[List of contents](../README.md#basics)
