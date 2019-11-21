# Dizionari

I dizionari sono appunto dei dizionari. Ad ogni chiave corrisponde un valore. Tutti i database moderni sono basati su questo concetto.

```python
nomi_e_luoghi = [
    ('Marco', 'Padova'),
    ('Luca', 'Milano'),
    ('Alice', 'Roma'),
]
```

Usare le liste non e' troppo comodo quando abbiamo bisogno di coppie chiave-valore.


```python
nomi_e_luoghi = {
    'Marco': 'Padova',
    'Luca': 'Milano',
    'Alice': 'Roma',
}
```

A sinistra abbiamo le **chiavi** ('Marco',ecc.) e destra i valori.
I dizionari non sono ordinati (esiste anche OrderedDict ma non lo vedremo).

## Operazioni con i dizionari

Lunghezza:

```python
>>> len(nomi_e_luoghi)  
3
>>> len(nomi_e_luoghi)  
3
>>>
```

Possiamo ottenere un valore di una chiave con `the_dict[key]`:

```python
>>> nomi_e_luoghi['Marco']
'Padova'
>>> nomi_e_luoghi['Alice']
'Roma'
>>>
```

Se si cerca di accedere a una chiave non presente nel dizionario, verra' lanciato un errore.

L'assegnazione e' semplicemente `the_dict[key] = value`.
Se la chiave 'key' non esiste viene automaticamente aggiunta altrimenti iene aggiornata.

```python
>>> nomi_e_luoghi['Massimo'] = 'Torino'
>>> nomi_e_luoghi['Massimo']
'Torino'
>>> nomi_e_luoghi['Massimo'] = 'Mantova'
>>> nomi_e_luoghi['Massimo']
'Mantova'
```

Possiamo anche iterare su un dizionario oppure controllare se esiste una chiave:

```python
>>> 'Massimo' in nomi_e_luoghi
True
>>> 'Giovanna' in nomi_e_luoghi
False
>>> for name in nomi_e_luoghi:
...     print(name)
...
Massimo
Luca
Alice
Marco
```
**Attenzione**: il codice precedente tiene conto solo delle chiavi. Per avere i valori si usa la funzione `values()`:

```python
>>> nomi_e_luoghi.values()
dict_values(['Mantova', 'Milano', 'Roma', 'Padova'])
>>>
```
Se vogliamo una lista di valori possiamo usare il comando  `list(nomi_e_luoghi.values())`. Esiste anche un metodo `.keys()` per avere le chiavi.

Se vogliamo iterare invece sulle coppie dobbiamo usare `items()`:

```python
>>> nomi_e_luoghi.items()
dict_items([('Massimo', 'Mantova'), ('Luca', 'Milano'), ('Alice', 'Roma'), ('Marco', 'Padova')])
>>> for nome, luogo in nomi_e_luoghi.items():
...     print(nome, luogo)
...
Massimo Mantova
Luca Milano
Alice Roma
Marco Padova
```

Si puo' verificare se esiste una coppia  `key: value`.

```python
>>> ('Massimo', 'Mantova') in nomi_e_luoghi.items()
True
>>> ('Luca', 'Verona') in nomi_e_luoghi.items()
False
>>>
```

E' possibile usare tuple come chiavi (non vale per le liste):

```python
>>> stuff = {('a', 'b'): 'c', ('d', 'e'): 'f'}
>>> stuff
{('a', 'b'): 'c', ('d', 'e'): 'f'}
>>>
```
I valori possono esser qualsiasi cosa:
```python
>>> stuff = {'a': [1, 2, 3], 'b': [4, 5, 6]}
>>> stuff
{'a': [1, 2, 3], 'b': [4, 5, 6]}
>>>
```


[Previous](zip-and-enumerate.md) | [Next](functions.md) |
[List of contents](../README.md#basics)
