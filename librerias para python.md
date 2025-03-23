# Numpy
Numpy es una librería aplicada para el manejo de vectores y matrices, que facilita una gran cantidad de operaciones matemáticas que pueden resolverse mediante el álgebra matricial ayudando a resolver aspectos como:
- Matrices multidimensionales (ndarray) eficientes.
- Operaciones matemáticas rápidas.
- Funciones de álgebra lineal, transformadas de Fourier, generación de números aleatorios, entre otras.

Para instalar NumPy:

```bash
pip install numpy
```

Para utilizar NumPy en Python:

```python
import numpy as np
```

---

## Creación y Manipulación de Arrays

### Crear Arrays

```python
import numpy as np

# Array unidimensional
a = np.array([1, 2, 3])
print(a)

# Array bidimensional (matriz)
b = np.array([[1, 2, 3], [4, 5, 6]])
print(b)

# Array de ceros
zeros = np.zeros((3, 3))
print(zeros)

# Array de unos
ones = np.ones((2, 2))
print(ones)

# Array con valores equidistantes
lin_space = np.linspace(0, 10, 5) # De 0 a 10 en 5 puntos
print(lin_space)
```

### Indexación y Segmentación

```python
arr = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])

# Acceder a un elemento específico
print(arr[1, 2]) # 60

# Extraer una fila
print(arr[1, :]) # [40, 50, 60]

# Extraer una columna
print(arr[:, 1]) # [20, 50, 80]
```

---

## Operaciones con Matrices

### Operaciones Básicas

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# Suma
print(A + B)

# Resta
print(A - B)

# Multiplicación elemento a elemento
print(A * B)

# Producto de matrices (matmul o @)
print(np.matmul(A, B))
print(A @ B)

# Transposición
print(A.T)
```

### Determinante e Inversa

```python
from numpy.linalg import det, inv

A = np.array([[4, 7], [2, 6]])

# Determinante
print(det(A))

# Matriz inversa
print(inv(A))
```

---

## Solución de Sistemas de Ecuaciones Lineales

Resolver el sistema:

\[ 2x + 3y = 5 \]
\[ 4x + y = 6 \]

```python
import numpy as np

# Matriz de coeficientes
A = np.array([[2, 3], [4, 1]])

# Vector de términos independientes
b = np.array([5, 6])

# Resolver el sistema
x = np.linalg.solve(A, b)
print("Solución:", x)
```

---

## Álgebra Vectorial

### Producto Punto

```python
u = np.array([1, 2, 3])
v = np.array([4, 5, 6])

print(np.dot(u, v)) # 1*4 + 2*5 + 3*6 = 32
```

### Producto Cruz

```python
u = np.array([1, 0, 0])
v = np.array([0, 1, 0])

print(np.cross(u, v)) # [0, 0, 1]
```

### Norma de un Vector

```python
v = np.array([3, 4])

print(np.linalg.norm(v)) # 5
```

---

# Matplotlib

Matplotlib es una biblioteca de Python utilizada para crear visualizaciones estáticas, animadas e interactivas. Es especialmente útil para representar gráficos en 2D y 3D.

Para instalar Matplotlib:

```bash
pip install matplotlib
```

Para importar la biblioteca:

```python
import matplotlib.pyplot as plt
```

### Gráfico de Líneas

```python
import matplotlib.pyplot as plt
import numpy as np

x = np.linspace(0, 10, 100)
y = np.sin(x)

plt.plot(x, y, label='Seno')
plt.title('Gráfico de una función seno')
plt.xlabel('x')
plt.ylabel('sin(x)')
plt.legend()
plt.show()
```

### Gráfico de Barras

```python
categorias = ['A', 'B', 'C', 'D']
valores = [10, 20, 15, 25]

plt.bar(categorias, valores)
plt.title('Gráfico de Barras')
plt.show()
```

### Gráfico de Dispersión

```python
x = np.random.rand(100)
y = np.random.rand(100)

plt.scatter(x, y)
plt.title('Gráfico de Dispersión')
plt.show()
```

### Gráfico en 3D

```python
from mpl_toolkits.mplot3d import Axes3D

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
x, y = np.meshgrid(x, y)
z = np.sin(np.sqrt(x**2 + y**2))

ax.plot_surface(x, y, z, cmap='viridis')
plt.title('Superficie 3D')
plt.show()
```
