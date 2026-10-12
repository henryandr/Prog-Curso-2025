# Gráficos simples con Matplotlib

Ahora, exploraremos cómo utilizar la biblioteca `matplotlib` en Python para crear gráficos simples. Nos enfocaremos en el uso de `matplotlib` con archivos CSV, sin utilizar ninguna otra biblioteca de manejo de datos como Pandas o NumPy.

---

## Índice

1. [Instalación](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
2. [Gráfica de línea](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
3. [Gráfica de dispersión](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
4. [Gráfica de barras](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
5. [Histograma](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
6. [Gráfica de pastel](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
7. [Diagrama de caja](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
8. [Mapa de calor](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
9. [Gráficas en 3D](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
10. [Subplots (Gráficas múltiples)](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
11. [Personalización de gráficas](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)
12. [Conclusión](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 1. Instalación

## Entorno virtual

Un entorno virtual en Python se utiliza para crear un espacio aislado donde se pueden instalar paquetes y dependencias específicas para un proyecto, sin que estas afecten la configuración global del sistema o de otros proyectos. Esto facilita la gestión de versiones y evita conflictos entre librerías, asegurando que cada proyecto funcione con las versiones requeridas por sus desarrolladores. Para crear un entorno virtual, se utiliza el comando:

```bash
 python -m venv .venv
```

Donde `“nombre_entorno”` es el nombre que deseas darle al entorno.

Una vez creado, puedes activarlo (en sistemas operativos tipo Unix, como Linux o macOS, con:

```bash
//Con GitBash
source ./.venv/bin/activate 
```

y en Windows con:

```bash
 nombre_entorno\\Scripts\\activate)
```

Para listar los módulos instalados en ese entorno, se emplea el comando `pip list`, el cual mostrará todas las librerías disponibles y sus respectivas versiones.

## Matplotlib

Ahora, antes de comenzar, asegúrate de tener Matplotlib instalado. Si no lo tienes, puedes instalarlo usando pip:

```bash
pip install matplotlib
```

También es útil instalar NumPy para manejar arreglos numéricos:

```bash
pip install numpy
```

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 2. Gráfica de línea

Las gráficas de línea son ideales para mostrar tendencias a lo largo del tiempo o un rango continuo.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Crear la gráfica
plt.plot(x, y)

# Agregar título y etiquetas
plt.title('Gráfica de Seno')
plt.xlabel('X')
plt.ylabel('sin(X)')

# Mostrar la gráfica
plt.show()
```

**Cómo modificarlo:**

- **Función a graficar:** Cambia `y = np.sin(x)` por cualquier otra función, como `y = np.cos(x)` o `y = np.exp(x)`.
- **Rango de x:** Ajusta `np.linspace(0, 10, 100)` para cambiar el intervalo y la densidad de puntos.
- **Estilo de línea:** Añade parámetros a `plt.plot`, por ejemplo, `plt.plot(x, y, linestyle='--', color='red')`.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 3. Gráfica de dispersión

Las gráficas de dispersión son útiles para mostrar la relación entre dos variables.

**Ejemplo:**

```python
import matplotlib.pyplot as plt

# Datos
x = [1, 2, 3, 4, 5]
y = [10, 12, 25, 30, 45]

# Crear la gráfica de dispersión
plt.scatter(x, y)

# Agregar título y etiquetas
plt.title('Gráfica de Dispersión')
plt.xlabel('Variable X')
plt.ylabel('Variable Y')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Datos personalizados:** Reemplaza las listas `x` e `y` con tus propios datos.
- **Personalización de puntos:** Usa `plt.scatter(x, y, s=100, c='green', marker='^')` para cambiar el tamaño, color y forma de los puntos.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 4. Gráfica de barras

Las gráficas de barras son ideales para comparar cantidades entre diferentes categorías.

**Ejemplo:**

```python
import matplotlib.pyplot as plt

# Datos
categorias = ['A', 'B', 'C', 'D']
valores = [10, 15, 7, 12]

# Crear la gráfica de barras
plt.bar(categorias, valores)

# Agregar título y etiquetas
plt.title('Gráfica de Barras')
plt.xlabel('Categorías')
plt.ylabel('Valores')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Colores personalizados:** Usa `plt.bar(categorias, valores, color=['red', 'blue', 'green', 'orange'])`.
- **Orientación horizontal:** Usa `plt.barh(categorias, valores)` para una gráfica de barras horizontal.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 5. Histograma

Los histogramas muestran la distribución de un conjunto de datos.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos
data = np.random.randn(1000)

# Crear el histograma
plt.hist(data, bins=30, edgecolor='black')

# Agregar título y etiquetas
plt.title('Histograma')
plt.xlabel('Valores')
plt.ylabel('Frecuencia')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Número de bins:** Cambia `bins=30` al número de intervalos que prefieras.
- **Datos personalizados:** Reemplaza `data` con tu propio conjunto de datos.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 6. Gráfica de pastel

Las gráficas de pastel son útiles para mostrar proporciones.

**Ejemplo:**

```python
import matplotlib.pyplot as plt

# Datos
etiquetas = ['Manzanas', 'Bananas', 'Cerezas', 'Dátiles']
tamaños = [15, 30, 45, 10]

# Crear la gráfica de pastel
plt.pie(tamaños, labels=etiquetas, autopct='%1.1f%%', startangle=90)

# Asegurar que el gráfico sea circular
plt.axis('equal')

# Agregar título
plt.title('Distribución de Frutas')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Destacar una porción:** Usa `explode = (0, 0.1, 0, 0)` y añade `explode=explode` a `plt.pie`.
- **Colores personalizados:** Usa `colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']` y añade `colors=colors` a `plt.pie`.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 7. Diagrama de caja

Los diagramas de caja muestran la distribución de datos basada en cuartiles.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos
data = [np.random.normal(0, std, 100) for std in range(1, 4)]

# Crear el diagrama de caja
plt.boxplot(data, labels=['Desv=1', 'Desv=2', 'Desv=3'])

# Agregar título
plt.title('Diagrama de Caja')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Datos personalizados:** Reemplaza `data` con tus propios conjuntos de datos.
- **Opciones de visualización:** Añade `vert=False` para una orientación horizontal.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 8. Mapa de calor

Los mapas de calor son útiles para visualizar matrices y correlaciones.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos
matriz = np.random.rand(10, 10)

# Crear el mapa de calor
plt.imshow(matriz, cmap='hot', interpolation='nearest')

# Agregar barra de color
plt.colorbar()

# Agregar título
plt.title('Mapa de Calor')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Cambiar el mapa de color:** Modifica `cmap='hot'` por otros como `'viridis'`, `'plasma'`, `'cool'`.
- **Datos personalizados:** Usa tu propia matriz de datos en lugar de `np.random.rand(10, 10)`.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 9. Gráficas en 3D

Matplotlib permite crear gráficas en 3D utilizando `mpl_toolkits.mplot3d`.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Crear figura
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# Datos
X = np.arange(-5, 5, 0.25)
Y = np.arange(-5, 5, 0.25)
X, Y = np.meshgrid(X, Y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Crear la superficie
ax.plot_surface(X, Y, Z, cmap='viridis')

# Agregar título
ax.set_title('Gráfica 3D de Superficie')

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Función Z personalizada:** Cambia `Z = np.sin(np.sqrt(X**2 + Y**2))` por otra función de X e Y.
- **Gráficas de dispersión 3D:** Usa `ax.scatter(X, Y, Z)` para crear una gráfica de dispersión en 3D.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 10. Subplots (Gráficas múltiples)

Puedes crear múltiples gráficas en una sola figura.

**Ejemplo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Datos
x = np.linspace(0, 2 * np.pi, 100)
y_sin = np.sin(x)
y_cos = np.cos(x)

# Crear subplots
fig, axs = plt.subplots(2, 1, figsize=(8, 6))

# Gráfica de seno
axs[0].plot(x, y_sin)
axs[0].set_title('Seno')

# Gráfica de coseno
axs[1].plot(x, y_cos, 'r')
axs[1].set_title('Coseno')

# Ajustar el espacio entre subplots
plt.tight_layout()

# Mostrar la gráfica
plt.show()

```

**Cómo modificarlo:**

- **Configuración de subplots:** Cambia `2, 1` en `plt.subplots(2, 1)` por el número de filas y columnas que necesites.
- **Compartir ejes:** Añade `sharex=True` o `sharey=True` en `plt.subplots` para compartir ejes entre subplots.

[Volver al Índice](https://www.notion.so/Gr-ficos-simples-con-Matplotlib-de00e03603ee4a4fbf85b87ed8a4c61f?pvs=21)

---

## 11. Personalización de gráficas

Matplotlib ofrece muchas opciones para personalizar tus gráficas.

**Cambiar el estilo:**

```python
plt.style.use('ggplot')

```

**Agregar leyendas:**

```python
plt.plot(x, y, label='Etiqueta')
plt.legend()

```

**Ajustar límites de los ejes:**

```python
plt.xlim(0, 10)
plt.ylim(-1, 1)

```

**Rotar etiquetas del eje X:**

```python
plt.xticks(rotation=45)

```

**Guardar la gráfica como imagen:**

```python
plt.savefig('nombre_de_la_imagen.png', dpi=300)

```

**Ejemplo completo:**

```python
import matplotlib.pyplot as plt
import numpy as np

# Estilo
plt.style.use('seaborn-darkgrid')

# Datos
x = np.linspace(0, 10, 100)
y = np.exp(-x) * np.cos(2 * np.pi * x)

# Crear la gráfica
plt.plot(x, y, 'o-', label='Atenuación')

# Personalización
plt.title('Ejemplo de Personalización')
plt.xlabel('Tiempo')
plt.ylabel('Amplitud')
plt.legend()
plt.grid(True)

# Guardar y mostrar
plt.savefig('grafica_personalizada.png', dpi=300)
plt.show()

```
