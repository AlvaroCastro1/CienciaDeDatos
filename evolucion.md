# Visualización de Evolución en Python

En esta sección se detallan los tipos de gráficos utilizados para mostrar la evolución de una o varias categorías a lo largo del tiempo.

## Requisitos
Instala las siguientes bibliotecas de Python:

```bash
pip install matplotlib seaborn pandas
```

## Gráficos Implementados

### 1. Line Plot (Gráfico de Líneas)

El gráfico de líneas visualiza la evolución de una variable a lo largo del tiempo con líneas.

**Parámetros:**
- `x`: Eje X, normalmente usado para representar el tiempo o secuencia.
- `y`: Eje Y, que representa los valores a lo largo del tiempo.

**Ejemplo:**
```python
import matplotlib.pyplot as plt

# Datos de ejemplo
x = [1, 2, 3, 4, 5]
y = [10, 20, 15, 25, 30]

# Crear gráfico de líneas
plt.plot(x, y)
plt.title('Line Plot')
plt.xlabel('Tiempo')
plt.ylabel('Valor')
plt.show()
```

### 2. Area Plot (Gráfico de Área)

El gráfico de área es similar al gráfico de líneas, pero rellena el área bajo la curva.

**Parámetros:**
- `x`: Eje X.
- `y`: Eje Y.
- `color`: (Opcional) Color del área.

**Ejemplo:**
```python
# Crear gráfico de área
plt.fill_between(x, y, color="skyblue", alpha=0.4)
plt.plot(x, y, color="Slateblue", alpha=0.6)
plt.title('Area Plot')
plt.xlabel('Tiempo')
plt.ylabel('Valor')
plt.show()
```

### 3. Stacked Area (Área Apilada)

El gráfico de área apilada muestra la evolución de múltiples categorías apiladas en áreas.

**Parámetros:**
- `x`: Eje X.
- `ys`: Conjunto de datos apilados en el eje Y.
- `labels`: Etiquetas de cada área apilada.

**Ejemplo:**
```python
import numpy as np

# Datos de ejemplo
x = np.arange(1, 6)
y1 = np.array([10, 20, 15, 25, 30])
y2 = np.array([5, 10, 7, 12, 18])
y3 = np.array([2, 5, 3, 5, 7])

# Crear gráfico de áreas apiladas
plt.stackplot(x, y1, y2, y3, labels=['Categoría 1', 'Categoría 2', 'Categoría 3'], alpha=0.5)
plt.legend(loc='upper left')
plt.title('Stacked Area Plot')
plt.xlabel('Tiempo')
plt.ylabel('Valor')
plt.show()
```

### 4. Streamchart (Gráfico de Corrientes)

El gráfico de corrientes (streamchart) muestra la evolución de múltiples categorías con curvas suavizadas que fluyen.

**Parámetros:**
- `x`: Eje X.
- `ys`: Conjunto de datos apilados.
- `labels`: Etiquetas de cada área.

**Ejemplo:**
Para crear un gráfico de corriente, puedes usar bibliotecas especializadas como `streamz`, pero un gráfico de áreas apiladas puede ser un punto de partida. En Python, la implementación exacta puede necesitar bibliotecas adicionales como `plotly` o `bokeh`.

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos de ejemplo para el streamchart
x = np.arange(0, 100, 1)
y1 = np.sin(x / 10) + np.random.rand(len(x)) * 0.5
y2 = np.cos(x / 10) + np.random.rand(len(x)) * 0.5
y3 = np.sin(x / 15) + np.random.rand(len(x)) * 0.5

# Crear gráfico de corriente
plt.fill_between(x, y1, alpha=0.6, label='Categoría 1')
plt.fill_between(x, y1 + y2, y1, alpha=0.6, label='Categoría 2')
plt.fill_between(x, y1 + y2 + y3, y1 + y2, alpha=0.6, label='Categoría 3')
plt.legend(loc='upper right')
plt.title('Streamchart')
plt.show()
```

## Formato y Personalización

- Los colores y el relleno de los gráficos pueden personalizarse con el parámetro `color` o `alpha` para modificar la transparencia.
- Las etiquetas, leyendas y títulos se ajustan con las funciones `plt.title()`, `plt.xlabel()`, `plt.ylabel()`, y `plt.legend()`.

## Referencias
- [Documentación de matplotlib](https://matplotlib.org/)