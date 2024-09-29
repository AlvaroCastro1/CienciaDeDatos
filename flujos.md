# Visualización de Flujos en Python

Esta sección describe gráficos que se utilizan para mostrar relaciones y flujos entre diferentes categorías o nodos en un sistema.

## Gráficos Implementados

### 1. Chord Diagram (Diagrama de Cuerdas)

El **Chord Diagram** muestra relaciones y flujos entre diferentes categorías utilizando arcos y cuerdas.

**Parámetros:**
- `matrix`: Matriz de conexiones entre categorías.
- `labels`: Etiquetas para las categorías.

**Ejemplo:**
```python
import matplotlib.pyplot as plt
from chord import Chord

# Datos de ejemplo
matrix = [[0, 2, 3], [2, 0, 4], [3, 4, 0]]
labels = ['Categoría A', 'Categoría B', 'Categoría C']

# Crear el diagrama de cuerdas
Chord(matrix, labels).show()
```

**Nota:** Para este tipo de gráfico, necesitarás la librería `chord` que puedes instalar con `pip install chord`.

### 2. Network (Red de Conexiones)

El gráfico de **Network** visualiza una red de conexiones entre nodos.

**Parámetros:**
- `edges`: Lista de tuplas representando las conexiones entre nodos.
- `positions`: Posiciones de los nodos en el gráfico.

**Ejemplo:**
```python
import networkx as nx
import matplotlib.pyplot as plt

# Crear una red de conexiones
G = nx.Graph()
G.add_edges_from([(1, 2), (1, 3), (3, 4), (2, 4)])

# Posiciones de los nodos
pos = nx.spring_layout(G)

# Dibujar la red
nx.draw(G, pos, with_labels=True)
plt.title('Network Diagram')
plt.show()
```

### 3. Sankey (Diagrama Sankey)

El diagrama **Sankey** representa flujos de cantidades entre categorías mediante líneas de diferentes grosores.

**Parámetros:**
- `flows`: Flujos de cantidades entre las categorías.
- `labels`: Etiquetas para los flujos.
- `orientations`: Orientación de los flujos (1 o -1).

**Ejemplo:**
```python
from matplotlib.sankey import Sankey

# Crear un diagrama Sankey
Sankey(flows=[15, -10, -5], labels=['Entrada', 'Salida 1', 'Salida 2'], orientations=[0, 1, -1]).finish()
plt.title('Diagrama Sankey')
plt.show()
```

### 4. Arc Diagram (Diagrama de Arcos)

El **Arc Diagram** muestra relaciones utilizando arcos entre nodos dispuestos linealmente.

**Parámetros:**
- `edges`: Lista de tuplas que representan las conexiones entre nodos.
- `positions`: Posiciones de los nodos.

**Ejemplo:**
```python
import matplotlib.pyplot as plt

# Datos de ejemplo
nodes = range(5)
edges = [(0, 1), (1, 2), (2, 3), (3, 4), (0, 4)]

# Crear el diagrama de arcos
for edge in edges:
    plt.plot(edge, [0, 0], marker='o', color='b')

plt.title('Arc Diagram')
plt.gca().axes.yaxis.set_visible(False)  # Ocultar eje Y
plt.show()
```

### 5. Edge Bundling

El **Edge Bundling** agrupa y organiza las conexiones en redes complejas para reducir el desorden visual.

**Parámetros:**
- `nodes`: Lista de nodos.
- `edges`: Conexiones entre nodos.
- `bundles`: Agrupaciones de las conexiones.

**Ejemplo:**
```python
import matplotlib.pyplot as plt
import networkx as nx

# Crear un grafo con agrupamiento de conexiones
G = nx.cycle_graph(6)
pos = nx.circular_layout(G)

# Dibujar la red con "bundling"
nx.draw(G, pos, with_labels=True, edge_color='gray')
plt.title('Edge Bundling')
plt.show()
```

## Formato y Personalización

- Los colores, grosores de las líneas, y disposición de los nodos se pueden personalizar usando parámetros adicionales como `color`, `width`, y `pos`.
- Los gráficos como **Sankey** y **Chord Diagram** se pueden ajustar según la cantidad de flujos o relaciones que se quieran representar.

## Referencias
- [Documentación de matplotlib](https://matplotlib.org/stable/contents.html)
- [Documentación de NetworkX](https://networkx.github.io/)
- [Documentación de chord](https://pypi.org/project/chord/)