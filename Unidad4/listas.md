## Concepto y Sintaxis

Las listas son colecciones ordenadas y **mutables** de elementos. Pueden contener objetos de diferentes tipos y admiten la duplicación de elementos.

## **Sintaxis básica:**

Ejecuta el siguiente código en tu computador.

```python
# Lista vacía
componentes = []

# Lista con elementos
componentes = ["alas", "fuselaje", "motores", "tren de aterrizaje"]

# Lista con diferentes tipos de datos
datos_vuelo = [202, "Boeing 737", True, 10500.5]

# Listas anidadas
matriz_rotacion = [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
```

Responde la siguientes preguntas:

- ¿Es posible crear listas que contengan diferentes tipos de datos?
- ¿Una lista puede contener otra lista?
- ¿Una lista es un objeto?

## **Acceso a elementos:**

Ahora vas a practicar, intenta acceder a los diferentes elementos de la lista. Utiliza el siguiente código. Además, vas a cambiar el código para responder las siguientes preguntas:

- ¿Qué sucede si intento acceder a un índice negativo?
- ¿Cuantas “vueltas” puedo darle a la lista usando índices negativos? ¿Entiendes a lo que me refiero?
- ¿Para que se utilizan los dos puntos (:) dentro de los corchetes?

```python
# Indexación (comienza en 0)
print(componentes[0])  # "alas"
print(componentes[-1])  # "tren de aterrizaje" (indexación negativa)

# Slicing (rebanado)
print(componentes[1:3])  # ["fuselaje", "motores"]
print(componentes[:2])   # ["alas", "fuselaje"]
print(componentes[2:])   # ["motores", "tren de aterrizaje"]
```

## Ejemplos usando listas

Analiza los siguientes ejemplos, ten en cuenta que probablemente hayan métodos nuevos que no conoces. Toma nota de esos métodos y trata de crear una hipótesis acerca de lo que crees que realiza. En la siguiente sección estudiaremos con más detenimiento los métodos de las listas.

### **Ejemplo 1: Registro de datos de vuelo**

```python
# Datos de vuelo para un avión comercial
tiempo = [0, 10, 20, 30, 40, 50, 60]  # segundos
altitud = [0, 100, 500, 1000, 1500, 2000, 2200]  # metros
velocidad = [0, 50, 100, 150, 200, 250, 300]  # km/h
estado = ["despegue", "ascenso inicial", "ascenso", "ascenso", "ascenso", "nivelación", "crucero"]

# Imprimir informe de despegue
print("INFORME DE DESPEGUE:")
for t, a, v, est in zip(tiempo, altitud, velocidad, estado):
    print(f"T+{t}s: Altitud={a}m, Velocidad={v}km/h, Fase={act}")
```

### **Ejemplo 2: Cálculo de centro de masa**

```python
# Lista de componentes con sus masas (kg) y posiciones (m)
componentes = ["motor izquierdo", "motor derecho", "fuselaje", "ala izquierda", "ala derecha", "cola"]
masas = [1200, 1200, 5000, 800, 800, 600]
posiciones_x = [2, 2, 0, -2, 2, -6]

# Cálculo del centro de masa en eje X sin list comprehensions
masa_total = 0
momento_total = 0

for i in range(len(masas)):
    masa_total += masas[i]
    momento_total += masas[i] * posiciones_x[i]

centro_masa_x = momento_total / masa_total

print(f"Centro de masa en eje X: {centro_masa_x:.2f} m")
```

## Métodos Principales (Listas)

Las listas tienen numerosos métodos incorporados:

| Método | Descripción | Ejemplo |
| --- | --- | --- |
| `append()` | Añade un elemento al final | `componentes.append("alerones")` |
| `insert()` | Inserta elemento en posición específica | `componentes.insert(1, "cabina")` |
| `extend()` | Añade elementos de otro iterable | `componentes.extend(["flaps", "spoilers"])` |
| `remove()` | Elimina la primera ocurrencia | `componentes.remove("alerones")` |
| `pop()` | Elimina y retorna el elemento en la última posición | `último = componentes.pop()` |
| `clear()` | Elimina todos los elementos | `componentes.clear()` |
| `index()` | Retorna el índice de la primera ocurrencia | `pos = componentes.index("motores")` |
| `count()` | Cuenta las ocurrencias de un elemento | `num = componentes.count("alas")` |
| `sort()` | Ordena la lista in-place | `velocidades.sort()` |
| `reverse()` | Invierte la lista in-place | `componentes.reverse()` |
| `copy()` | Retorna una copia superficial | `copia = componentes.copy()` |

### **Ejemplo de uso:**

```python
# Registro de temperaturas del motor durante un vuelo
temperaturas_motor = [120, 350, 380, 375, 390, 400, 405, 390, 385, 370]

# Añadir nueva lectura
temperaturas_motor.append(360)

# Encontrar temperatura máxima
temp_max = max(temperaturas_motor)
print(f"Temperatura máxima: {temp_max}°C")

# Encontrar posición de la temperatura máxima
pos_max = temperaturas_motor.index(temp_max)
print(f"Temperatura máxima alcanzada en la lectura #{pos_max+1}")

# Ordenar para análisis
temperaturas_ordenadas = sorted(temperaturas_motor)  # No modifica la original
print(f"Temperaturas ordenadas: {temperaturas_ordenadas}")

# Modificar la lista original
temperaturas_motor.sort(reverse=True)  # Orden descendente
print(f"Temperaturas (mayor a menor): {temperaturas_motor}")
```

## Ejercicios Prácticos

### **Ejercicio 1: Análisis de eficiencia de combustible**

Desarrolle una función que calcule la eficiencia de combustible de una aeronave a lo largo de diferentes etapas de vuelo.

```python
def analizar_eficiencia(distancias, combustible_consumido):
    """
    Calcula la eficiencia de combustible en km/L para cada tramo del vuelo
    y devuelve estadísticas relevantes.

    Args:
        distancias: Lista de distancias recorridas en km por tramo
        combustible_consumido: Lista de combustible consumido en L por tramo

    Returns:
        Las estadísticas de eficiencia
    """
    # Su código aquí
    # 1. Calcular la eficiencia para cada tramo (distancia/combustible)
    # 2. Determinar tramo más eficiente y menos eficiente
    # 3. Calcular eficiencia promedio
    pass

# Datos de prueba
tramos_distancia = [800, 1200, 1000, 750]  # km
tramos_combustible = [2400, 3000, 2800, 2000]  # L

# Probando la función
# resultado = analizar_eficiencia(tramos_distancia, tramos_combustible)
# print(resultado)

```

### Ejercicio 2: Selección de cajas para carga en una aeronave

En una operación de carga aérea, se tiene una lista de cajas, cada una con un peso diferente. La aeronave tiene un límite máximo de peso que no debe ser superado por la suma de los pesos de las cajas seleccionadas. Debes escribir una función que recorra la lista de pesos de las cajas y agregue cada caja mientras no se exceda el peso máximo permitido. La función debe mostrar en pantalla los índices de las cajas seleccionadas y el peso total cargado.

Completa el código a continuación utilizando únicamente listas y ciclos:

```python
def cargar_cajas(pesos, peso_maximo):
    """
    Selecciona cajas para cargar en la aeronave sin exceder el peso máximo.

    Args:
        pesos: lista de pesos de las cajas (kg)
        peso_maximo: peso máximo permitido (kg)
    """
    # Tu código aquí

# Datos de prueba
pesos_cajas = [120, 400, 300, 180, 450, 200]
peso_max_avion = 1000

cargar_cajas(pesos_cajas, peso_max_avion)
```

### **Ejercicio 3: Análisis de trayectoria**

Desarrolle una función que analice una trayectoria de vuelo y detecte desviaciones significativas del rumbo planeado.

```python
def analizar_trayectoria(rumbo_planeado, rumbo_real, umbral_desviacion=5):
    """
    Identifica puntos en la trayectoria donde el avión se desvió
    significativamente del rumbo planeado.

    Args:
        rumbo_planeado: Lista de ángulos planeados (grados)
        rumbo_real: Lista de ángulos reales seguidos (grados)
        umbral_desviacion: Desviación máxima permitida en grados

    Returns:
        Lista de índices donde la desviación superó el umbral
    """
    # Su código aquí
    pass

# Datos de prueba
planeado = [45, 45, 45, 90, 90, 90, 180, 180, 225, 225, 270]
real = [43, 47, 48, 86, 91, 95, 183, 176, 222, 230, 265]

# Probando la función
# desviaciones = analizar_trayectoria(planeado, real, 5)
# print(f"Se detectaron desviaciones significativas en los puntos: {desviaciones}")
```
