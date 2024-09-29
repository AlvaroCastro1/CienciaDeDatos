# Graficos 

# Visualización de Correlaciones

### 1. Scatter Plot (Gráfico de Dispersión)

El gráfico de dispersión muestra la relación entre dos variables utilizando puntos dispersos.

**Parámetros:**
- `x`: Datos para el eje X.
- `y`: Datos para el eje Y.
- `color`: (Opcional) Color de los puntos.

**Ejemplo:**
```python
import matplotlib.pyplot as plt

# Datos de ejemplo
x = [1, 2, 3, 4, 5]
y = [2, 4, 1, 3, 7]

# Crear el gráfico
plt.scatter(x, y, color='blue')
plt.title('Scatter Plot')
plt.xlabel('Variable X')
plt.ylabel('Variable Y')
plt.show()
```

### 2. Heatmap (Mapa de Calor)

El heatmap representa una matriz de correlaciones en colores, donde el color refleja la intensidad de la correlación.

**Parámetros:**
- `data`: Matriz de correlaciones.
- `cmap`: (Opcional) Colormap para los colores.

**Ejemplo:**
```python
import seaborn as sns
import numpy as np

# Datos de ejemplo
data = np.random.rand(10, 12)

# Crear el heatmap
sns.heatmap(data, cmap='coolwarm')
plt.title('Heatmap')
plt.show()
```

### 3. Correlogram (Correlograma)

Visualiza múltiples correlaciones entre variables en un conjunto de datos.

**Parámetros:**
- `data`: Un DataFrame con los datos a correlacionar.
- `cmap`: (Opcional) Colormap para los colores.

**Ejemplo:**
```python
import seaborn as sns
import pandas as pd

# Datos de ejemplo
data = pd.DataFrame(np.random.rand(10, 4), columns=["A", "B", "C", "D"])

# Crear el correlograma
sns.pairplot(data)
plt.title('Correlogram')
plt.show()
```

### 4. Bubble Plot (Gráfico de Burbujas)

Similar a un gráfico de dispersión, pero las burbujas tienen tamaños que representan una tercera variable.

**Parámetros:**
- `x`: Datos para el eje X.
- `y`: Datos para el eje Y.
- `size`: Datos que representan el tamaño de las burbujas.
- `color`: (Opcional) Color de las burbujas.

**Ejemplo:**
```python
import matplotlib.pyplot as plt

# Datos de ejemplo
x = [1, 2, 3, 4, 5]
y = [10, 20, 25, 30, 35]
size = [40, 80, 200, 300, 400]

# Crear el gráfico de burbujas
plt.scatter(x, y, s=size, alpha=0.5)
plt.title('Bubble Plot')
plt.xlabel('Variable X')
plt.ylabel('Variable Y')
plt.show()
```

### 5. Connected Scatter (Gráfico de Dispersión Conectado)

Este gráfico muestra relaciones secuenciales entre datos conectados por líneas.

**Parámetros:**
- `x`: Datos para el eje X.
- `y`: Datos para el eje Y.
- `linestyle`: (Opcional) Estilo de las líneas que conectan los puntos.

**Ejemplo:**
```python
# Datos de ejemplo
x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

# Crear el gráfico de dispersión conectado
plt.plot(x, y, marker='o', linestyle='-', color='green')
plt.title('Connected Scatter Plot')
plt.xlabel('Variable X')
plt.ylabel('Variable Y')
plt.show()
```

### 6. Density 2D (Densidad 2D)

Este gráfico muestra la densidad de los datos en un espacio bidimensional.

**Parámetros:**
- `x`: Datos para el eje X.
- `y`: Datos para el eje Y.
- `cmap`: (Opcional) Colormap para la densidad.

**Ejemplo:**
```python
import seaborn as sns

# Datos de ejemplo
x = np.random.randn(1000)
y = np.random.randn(1000)

# Crear el gráfico de densidad 2D
sns.kdeplot(x=x, y=y, cmap='Blues', fill=True)
plt.title('Density 2D Plot')
plt.show()
```

## Formato y Personalización

- Para cambiar el color de los gráficos, puedes utilizar el parámetro `color` o `cmap` dependiendo del gráfico.
- Los títulos, etiquetas y estilos se pueden personalizar usando las funciones `plt.title()`, `plt.xlabel()`, `plt.ylabel()` y `plt.grid()`.
- Para guardar los gráficos en un archivo, puedes usar `plt.savefig('nombre_del_archivo.png')`.

- [Documentación de matplotlib](https://matplotlib.org/stable/contents.html)
- [Documentación de seaborn](https://seaborn.pydata.org/)