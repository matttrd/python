# Files con Python

Python e' in grado di leggere e scrivere file.


## Scrivere in un file

Creare in modalita di scrittura 'w':
```python
>>> with open('hello.txt', 'w') as f:
...     print("Hello World!", file=f)
...
>>>
```
 `open` apre il file e l'oggetto che lo gestisce e' assegnato alla variabile `f`.

```python
>>> f
<_io.TextIOWrapper name='hello.txt' mode='w' encoding='UTF-8'>
>>>
```

Il primo argomento e' il nome (path completo o relativo) del file ('hello.txt') mentre il secondo argomento indica l'operazione di scrittura, lettura, append.


| Mode  | Short for | Meaning                                                               |
|-------|-----------|-----------------------------------------------------------------------|
| `r`   | read      | Read from an existing file.                                           |
| `w`   | write     | Write to a file. **If the file exists, its old content is removed.**  |
| `a`   | append    | Write to the end of a file, and keep the old content.                 |

`with` assicura che quando l'operazione e' finita il file venga chiuso.


## Leggere da file

Bsat usare `r`:

```python
>>> lines = []
>>> with open('hello.txt', 'r') as f:
...     for line in f:
...         lines.append(line)
...
>>> lines
['Hello World!\n']
>>>
```
E' anche possibile leggere una linea alla volta con `readline` (https://docs.python.org/3/library/io.html#io.TextIOBase.readline)

```python
>>> with open('hello.txt', 'r') as f:
...     first_line = f.readline()
...     second_line = f.readline()
...
>>> first_line
'Hello one!\n'
>>> second_line
'Hello two!\n'
```

Gli oggetti file ricordano la posizione:

```python
>>> first = []
>>> second = []
>>> with open('hello.txt', 'r') as f:
...     for line in f:
...         first.append(line)
...
>>> with open('hello.txt', 'r') as f:
...     for line in f:
...         second.append(line)
...
>>> first
['Hello one!\n', 'Hello two!\n', 'Hello three!\n']
>>> second
['Hello one!\n', 'Hello two!\n', 'Hello three!\n']
>>>
```

Leggere tutto il contenuto:

```python
>>> with open('hello.txt', 'r') as f:
...     full_content = f.read()
...
>>> full_content
'Hello one!\nHello two!\nHello three!\n'
>>>
```

[Previous](real_script.md) | [Next](modules.md) |
[List of contents](../README.md#basics)
