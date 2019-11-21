# Numpy
Numpy è la libreria principale per il calcolo scientifico in Python. Fornisce un oggetto array multidimensionale e strumenti per lavorare con questi array. Per chi ha gia' familiarità con MATLAB, potresti trovare utile questo [tutorial](https://docs.scipy.org/doc/numpy/user/numpy-for-matlab-users.html) per iniziare a utilizzare Numpy.

## Array
Una matrice numpy è una griglia di valori, tutti dello stesso tipo, ed è indicizzata da una tupla di numeri interi non negativi. Il numero di dimensioni è il rango dell'array; la forma di un array è una tupla di numeri interi che fornisce le dimensioni dell'array lungo ciascuna dimensione. Possiamo inizializzarlo in maniera simile alle liste:

```python
import numpy as np

a = np.array([1, 2, 3])   
print(type(a))            # Prints "<class 'numpy.ndarray'>"
print(a.shape)            # Prints "(3,)"
print(a[0], a[1], a[2])   # Prints "1 2 3"
a[0] = 5                  # Cambia un elemento dell'array
print(a)                  # Prints "[5, 2, 3]"

b = np.array([[1,2,3],[4,5,6]])    # Crea una matrice
print(b.shape)                     # Prints "(2, 3)"
print(b[0, 0], b[0, 1], b[1, 0])   # Prints "1 2 4"
```

Altri esempi predefiniti:
```python
import numpy as np

a = np.zeros((2,2))   # Create an array of all zeros
print(a)              # Prints "[[ 0.  0.]
                      #          [ 0.  0.]]"

b = np.ones((1,2))    # Create an array of all ones
print(b)              # Prints "[[ 1.  1.]]"

c = np.full((2,2), 7)  # Create a constant array
print(c)               # Prints "[[ 7.  7.]
                       #          [ 7.  7.]]"

d = np.eye(2)         # Create a 2x2 identity matrix
print(d)              # Prints "[[ 1.  0.]
                      #          [ 0.  1.]]"

e = np.random.random((2,2))  # Create an array filled with random values
print(e)                     # Might print "[[ 0.91940167  0.08143941]
                             #               [ 0.68744134  0.87236687]]"
```

## Indexing degli Array

```python
import numpy as np

# Create la matrice con shape (3, 4)
# [[ 1  2  3  4]
#  [ 5  6  7  8]
#  [ 9 10 11 12]]
a = np.array([[1,2,3,4], [5,6,7,8], [9,10,11,12]])

# Seleziona la sotto-matrice:
# [[2 3]
#  [6 7]]
b = a[:2, 1:3]

# A slice of an array is a view into the same data, so modifying it
# will modify the original array.
print(a[0, 1])   # Prints "2"
b[0, 0] = 77     # b[0, 0] is the same piece of data as a[0, 1]
print(a[0, 1])   # Prints "77"
```

E' anche possibile selezionare gli indici in ordine mutato o ripetuto:

```python
import numpy as np
a = np.array([1,2,3,4,5,6])
print(a[[5,1,2,4,3,0]])  # [6 2 3 5 4 1]
```

### Boolean indexing
```python
import numpy as np

a = np.array([[1,2], [3, 4], [5, 6]])

bool_idx = (a > 2)   # Trova gli elementi maggiori di 2;
                     # ritorna un array numpy di Booleani con la stessa shape di a, dove ogni elemento indica se l'elemento corrispondente di a e' maggiore di 2

print(bool_idx)      # Prints "[[False False]
                     #          [ True  True]
                     #          [ True  True]]"

print(a[bool_idx])  # Prints "[3 4 5 6]"

# Seleziona gli elementi di a maggiori di 2
print(a[a > 2])     # Prints "[3 4 5 6]"
```


### Tipi

Se non scecificato, Numpy sceglie un datatype standard conforme all'input.
```python
import numpy as np

x = np.array([1, 2])  
print(x.dtype)         # Prints "int64"

x = np.array([1.0, 2.0])
print(x.dtype)             # Prints "float64"

x = np.array([1, 2], dtype=np.int64)   # Forza un datatype
print(x.dtype)                         # Prints "int64"
```

### Matematica


```python
import numpy as np

x = np.array([[1,2],[3,4]], dtype=np.float64)
y = np.array([[5,6],[7,8]], dtype=np.float64)

# Elementwise sum; both produce the array
# [[ 6.0  8.0]
#  [10.0 12.0]]
print(x + y)
print(np.add(x, y))

# Elementwise difference; both produce the array
# [[-4.0 -4.0]
#  [-4.0 -4.0]]
print(x - y)
print(np.subtract(x, y))

# Elementwise product; both produce the array
# [[ 5.0 12.0]
#  [21.0 32.0]]
print(x * y)
print(np.multiply(x, y))

# Elementwise division; both produce the array
# [[ 0.2         0.33333333]
#  [ 0.42857143  0.5       ]]
print(x / y)
print(np.divide(x, y))

# Elementwise square root; produces the array
# [[ 1.          1.41421356]
#  [ 1.73205081  2.        ]]
print(np.sqrt(x))
```

`*` rappresenta la moltiplicazione pointwise e non la moltiplicazione matriciale. Possiamo usare `dot` per moltiplicare matrici.

```python
import numpy as np

x = np.array([[1,2],[3,4]])
y = np.array([[5,6],[7,8]])

v = np.array([9,10])
w = np.array([11, 12])

# Inner product of vectors; both produce 219
print(v.dot(w))
print(np.dot(v, w))

# Matrix / vector product; both produce the rank 1 array [29 67]
print(x.dot(v))
print(np.dot(x, v))

# Matrix / matrix product; both produce the rank 2 array
# [[19 22]
#  [43 50]]
print(x.dot(y))
print(np.dot(x, y))
```

Numpy fornisce molte operazioni che possono essere specificate lungo assi specificati:

```python
import numpy as np

x = np.array([[1,2],[3,4]])

print(np.sum(x))  # Compute sum of all elements; prints "10"
print(np.sum(x, axis=0))  # Compute sum of each column; prints "[4 6]"
print(np.sum(x, axis=1))  # Compute sum of each row; prints "[3 7]"
```

Puoi trovare l'elenco completo delle funzioni matematiche fornite da numpy nella [documentazione](https://docs.scipy.org/doc/numpy/reference/routines.math.html).


Per trasporre un vettore/matrice:

```python
import numpy as np

x = np.array([[1,2], [3,4]])
print(x)    # Prints "[[1 2]
            #          [3 4]]"
print(x.T)  # Prints "[[1 3]
            #          [2 4]]"

v = np.array([1,2,3])
print(v)    # Prints "[1 2 3]"
print(v.T)  # Prints "[1 2 3]"
```

### Broadcast

Il broadcast consente al numpy di lavorare con matrici di forme diverse quando si eseguono operazioni aritmetiche. Spesso abbiamo un array più piccolo e un array più grande e vogliamo utilizzare l'array più piccolo più volte per eseguire alcune operazioni sull'array più grande.

Ad esempio, supponiamo di voler aggiungere un vettore costante a ciascuna riga di una matrice. Potremmo farlo in questo modo:

```python
import numpy as np

# Aggiungeremo il vettore v ad ogni riga della matrice x,
# memorizzando il risultato nella matrice y

x = np.array([[1,2,3], [4,5,6], [7,8,9], [10, 11, 12]])
v = np.array([1, 0, 1])
y = np.empty_like(x)   # crea una matrice vuota con la shape di x

# Aggiunge il vettore v ad ogni riga della matrice con un loop
for i in range(4):
    y[i, :] = x[i, :] + v

# [[ 2  2  4]
#  [ 5  5  7]
#  [ 8  8 10]
#  [11 11 13]]
print(y)
```

Ci sono molti modi piu' efficienti per farlo!

### Reshape

Un altro comando utile e' `reshape`.

```python
import numpy as np
a = np.array([[1,2,3],[4,5,6]]) # shape (2, 3)
print(a.reshape(-1)) # array([1, 2, 3, 4, 5, 6])
print(a.reshape(3,2)) # [[1 2]
                      # [3 4]
                      # [5 6]]
print(a.reshape(3,-1)) # funziona ugualmente
```

Quando -1 e' utilizzato singolarmente rende piatto l'array. Puo' anche essere utilizzato assieme alla specificazione degli altri assi.
