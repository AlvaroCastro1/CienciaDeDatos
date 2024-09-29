# Visualización de Mapas en Python

En esta sección, se detallan los tipos de gráficos utilizados para mostrar datos geográficos en forma de mapas, junto con ejemplos de cómo implementarlos en Python.

## Gráficos Implementados

### 1. Map (Mapa Geográfico)

Este gráfico representa datos geográficos sobre un mapa.

**Parámetros:**
- `shapefile`: Archivo de forma geográfica (shapefile) o datos de geometría.
- `data`: Datos geográficos a representar.

**Ejemplo:**
```python
import geopandas as gpd
import matplotlib.pyplot as plt

# Cargar un shapefile de ejemplo
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

# Crear un mapa básico
world.plot()
plt.title('Mapa Geográfico')
plt.show()
```

### 2. Choropleth (Mapa Coroplético)

El **Choropleth** muestra datos categóricos o numéricos utilizando colores en un mapa geográfico.

**Parámetros:**
- `shapefile`: Archivo de forma geográfica.
- `data`: Datos para colorear las regiones.
- `cmap`: Colormap para representar los valores.

**Ejemplo:**
```python
import geopandas as gpd
import matplotlib.pyplot as plt

# Cargar shapefile del mundo
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

# Crear un mapa coroplético basado en la población
world.plot(column='pop_est', cmap='coolwarm', legend=True)
plt.title('Choropleth: Población Estimada')
plt.show()
```

### 3. Hexbin Map

El **Hexbin Map** utiliza hexágonos para representar la densidad de datos en un mapa.

**Parámetros:**
- `x`, `y`: Coordenadas geográficas.
- `gridsize`: Tamaño de los hexágonos.
- `cmap`: Colormap para los hexágonos.

**Ejemplo:**
```python
import numpy as np
import matplotlib.pyplot as plt

# Datos de ejemplo
x = np.random.randn(1000)
y = np.random.randn(1000)

# Crear un mapa hexbin
plt.hexbin(x, y, gridsize=30, cmap='Blues')
plt.colorbar(label='Densidad')
plt.title('Hexbin Map')
plt.show()
```

### 4. Cartogram

El **Cartogram** modifica la forma de los territorios para reflejar una variable específica (como población, economía, etc.).

**Parámetros:**
- `shapefile`: Archivo de forma geográfica.
- `data`: Datos que influyen en la deformación de los territorios.

**Ejemplo:**
Para un cartograma, se pueden usar bibliotecas específicas como `geopandas`, aunque son más avanzadas, y podrías necesitar bibliotecas adicionales como `cartopy`.

```python
# Ejemplo básico para visualizar mapas geográficos
import geopandas as gpd
import matplotlib.pyplot as plt

# Cargar shapefile del mundo
world = gpd.read_file(gpd.datasets.get_path('naturalearth_lowres'))

# Crear un cartograma sencillo (requiere más bibliotecas especializadas para distorsionar)
world.plot()
plt.title('Cartogram')
plt.show()
```

### 5. Bubble Map (Mapa de Burbujas)

El **Bubble Map** superpone burbujas sobre un mapa para representar una tercera variable (como el tamaño).

**Parámetros:**
- `lat`, `lon`: Coordenadas geográficas.
- `size`: Tamaño de las burbujas.
- `color`: (Opcional) Colores de las burbujas.

**Ejemplo:**
```python
import plotly.express as px

# Datos de ejemplo
data = px.data.gapminder().query("year == 2007")
fig = px.scatter_geo(data, locations="iso_alpha", size="pop", hover_name="country", color="continent",
                     projection="natural earth", title="Bubble Map")

fig.show()
```

## Formato y Personalización

- Los colores, tamaños de burbujas, y mapas base se pueden personalizar según las necesidades del gráfico.
- Para los mapas avanzados como **Cartogram** se pueden usar herramientas como `Cartopy` o `TopoJSON` para deformaciones y análisis geoespacial más complejo.

## Referencias
- [Documentación de geopandas](https://geopandas.org/)
- [Documentación de matplotlib](https://matplotlib.org/)
- [Documentación de plotly](https://plotly.com/python/)
```

Con esta actualización, ahora el README incluye guías para crear gráficos que muestran **mapas** y **datos geográficos**. Si tienes preguntas o necesitas personalizar más alguno de estos gráficos, no dudes en pedírmelo.