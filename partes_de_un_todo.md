
# Visualización de Partes de un Todo en Python

En esta sección, se describen gráficos utilizados para representar **jerarquías** y **proporciones** dentro de un conjunto de datos.

## Gráficos Implementados

### 1. Treemap

El **Treemap** representa jerarquías mediante rectángulos anidados que muestran proporciones.

**Parámetros:**
- `labels`: Etiquetas para cada categoría.
- `sizes`: Tamaño relativo de cada categoría.
- `colors`: (Opcional) Colores para cada rectángulo.

**Ejemplo:**
```python
import matplotlib.pyplot as plt
import squarify

# Datos de ejemplo
sizes = [500, 300, 100, 80, 50]
labels = ['Categoría A', 'Categoría B', 'Categoría C', 'Categoría D', 'Categoría E']

# Crear el gráfico treemap
squarify.plot(sizes=sizes, label=labels, alpha=0.8)
plt.axis('off')
plt.title('Treemap')
plt.show()
```

### 2. Venn Diagram (Diagrama de Venn)

El diagrama de Venn visualiza las intersecciones entre diferentes conjuntos de datos.

**Parámetros:**
- `set1`, `set2`: Conjuntos de datos para comparar.
- `set_labels`: Etiquetas de los conjuntos.

**Ejemplo:**
```python
from matplotlib_venn import venn2

# Datos de ejemplo
set1 = set([1, 2, 3, 4])
set2 = set([3, 4, 5, 6])

# Crear el diagrama de Venn
venn2([set1, set2], set_labels=('Set A', 'Set B'))
plt.title('Diagrama de Venn')
plt.show()
```

### 3. Doughnut (Gráfico de dona)

El gráfico de dona es similar a un gráfico de pastel, pero con un agujero en el centro.

**Parámetros:**
- `sizes`: Tamaño de cada porción.
- `labels`: Etiquetas para cada porción.
- `colors`: (Opcional) Colores para cada segmento.

**Ejemplo:**
```python
# Datos de ejemplo
sizes = [40, 30, 20, 10]
labels = ['A', 'B', 'C', 'D']

# Crear el gráfico de dona
plt.pie(sizes, labels=labels, wedgeprops=dict(width=0.4))
plt.title('Gráfico de Dona')
plt.show()
```

### 4. Sunburst

El gráfico **Sunburst** visualiza datos jerárquicos como segmentos radiales.

**Parámetros:**
- `labels`: Etiquetas de cada nodo.
- `sizes`: Tamaño de cada nodo.
- `parent`: Nodo padre de cada elemento.

**Ejemplo:**
```python
import plotly.graph_objects as go

# Datos de ejemplo
labels = ["A", "B", "C", "D", "E", "F", "G"]
parents = ["", "A", "A", "B", "B", "C", "C"]
sizes = [100, 40, 30, 20, 10, 10, 5]

# Crear el gráfico sunburst
fig = go.Figure(go.Sunburst(labels=labels, parents=parents, values=sizes))
fig.update_layout(title="Gráfico Sunburst")
fig.show()
```

### 5. Dendrogram

El **Dendrograma** muestra jerarquías mediante ramificaciones que representan agrupamientos.

**Parámetros:**
- `data`: Datos para realizar el agrupamiento.
- `method`: Método de enlace (por ejemplo, `single`, `complete`, etc.).

**Ejemplo:**
```python
from scipy.cluster.hierarchy import dendrogram, linkage
import numpy as np

# Datos de ejemplo
data = np.random.rand(10, 4)
linked = linkage(data, 'single')

# Crear el dendrograma
dendrogram(linked)
plt.title('Dendrograma')
plt.show()
```

## Formato y Personalización

- Los colores y estilos se pueden personalizar usando parámetros como `colors`, `alpha`, o `cmap`.
- Para los gráficos de tipo jerárquico como **Sunburst** y **Dendrogram**, puedes ajustar los métodos de visualización y el estilo de las ramas o nodos.

## Referencias
- [Documentación de matplotlib](https://matplotlib.org/stable/contents.html)
- [Documentación de plotly](https://plotly.com/python/)
- [Documentación de matplotlib-venn](https://pypi.org/project/matplotlib-venn/)
