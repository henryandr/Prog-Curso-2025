# Tuplas

### Concepto y Sintaxis

Las tuplas son colecciones ordenadas e **inmutables** de elementos. Al igual que las listas, pueden contener objetos de diferentes tipos, pero una vez creadas, no pueden ser modificadas.

**Sintaxis básica:**

```python
# Tupla vacía
coordenada = ()

# Tupla con elementos
coordenada = (33.9425, -118.4081)  # LAX (Aeropuerto de Los Ángeles)

# Tupla con un solo elemento (requiere coma al final)
rumbo = (270,)  # Sin la coma sería tratado como un entero entre paréntesis

# Tupla sin paréntesis (empaquetado implícito)
avion_info = "Boeing 787", "Dreamliner", 2009, 242

```

**Acceso a elementos:**

```python
# Indexación (similar a las listas)
print(coordenada[0])  # 33.9425
print(avion_info[-1])  # 242 (pasajeros)

# Slicing
print(avion_info[0:2])  # ("Boeing 787", "Dreamliner")

# Desempaquetado de tuplas
fabricante, modelo, año, capacidad = avion_info
print(f"El {fabricante} {modelo} se lanzó en {año}")

# Desempaquetado con *
lat, lon = coordenada
print(f"Latitud: {lat}, Longitud: {lon}"
```

### Ejemplos en Ingeniería Aeronáutica (Tuplas)

**Ejemplo 1: Base de datos de aeronaves**

```python
# Representando una flota de aeronaves con tuplas
# (modelo, envergadura (m), longitud (m), mtow (kg), velocidad_max (km/h))
fleet_data = [
    ("Airbus A320", 35.80, 37.57, 78000, 871),
    ("Boeing 737-800", 35.79, 39.47, 79010, 853),
    ("Embraer E190", 28.72, 36.24, 51800, 871),
    ("Bombardier CRJ-900", 24.85, 36.40, 38330, 870)
]

# Encontrar el avión con mayor envergadura (paso a paso)
print("=== Buscando el avión con mayor envergadura ===")

# Inicializamos variables para el seguimiento
avion_mayor_envergadura = None
mayor_envergadura_valor = 0

# Recorremos cada avión en la flota
for avion in fleet_data:
    # Extraemos los datos del avión actual
    modelo = avion[0]
    envergadura = avion[1]
    longitud = avion[2]
    mtow = avion[3]
    velocidad_max = avion[4]
    
    print(f"Revisando: {modelo} - Envergadura: {envergadura} m")
    
    # Comparamos si esta envergadura es mayor que la que teníamos guardada
    if envergadura > mayor_envergadura_valor:
        # Si es mayor, actualizamos nuestros valores
        mayor_envergadura_valor = envergadura
        avion_mayor_envergadura = avion
        print(f"  → Nuevo récord encontrado: {modelo}")
    else:
        print(f"  → No supera el récord actual")

# Mostramos el resultado
print(f"\nResultado: Avión con mayor envergadura: {avion_mayor_envergadura[0]} ({avion_mayor_envergadura[1]} m)")

print("\n" + "="*50)

# Calcular velocidad promedio de la flota (paso a paso)
print("=== Calculando velocidad promedio de la flota ===")

# Inicializamos variables para el cálculo
suma_velocidades = 0
contador_aviones = 0

# Recorremos cada avión para sumar las velocidades
for avion in fleet_data:
    # Extraemos el modelo y la velocidad del avión actual
    modelo = avion[0]
    velocidad = avion[4]
    
    print(f"Procesando: {modelo} - Velocidad: {velocidad} km/h")
    
    # Sumamos la velocidad al total
    suma_velocidades = suma_velocidades + velocidad
    contador_aviones = contador_aviones + 1
    
    print(f"  → Suma acumulada: {suma_velocidades} km/h")
    print(f"  → Aviones procesados: {contador_aviones}")

# Calculamos el promedio
velocidad_promedio = suma_velocidades / contador_aviones

# Mostramos el resultado
print(f"\nCálculo final:")
print(f"Suma total de velocidades: {suma_velocidades} km/h")
print(f"Número de aviones: {contador_aviones}")
print(f"Velocidad promedio de la flota: {velocidad_promedio:.2f} km/h")

```

**Ejemplo 2: Navegación mediante waypoints**

Este código implementa un **sistema de cálculo de distancias entre waypoints de navegación aérea** utilizando coordenadas geográficas. El programa define una ruta de vuelo desde Los Ángeles (LAX) hasta Denver con waypoints intermedios, donde cada punto se representa como una tupla con nombre, latitud, longitud y altitud mínima 📍.

La **ecuación principal es la fórmula de Haversine**:

`$d = 2R × arctan2(√a, √(1-a))$`

donde

`$a = sin²(Δφ/2) + cos(φ₁) × cos(φ₂) × sin²(Δλ/2)$`

siendo φ las latitudes, λ las longitudes y R el radio terrestre (`6371 km`) 🌍.

El algoritmo convierte las diferencias de coordenadas a radianes, calcula la distancia ortodrómica (gran círculo) entre cada par de waypoints consecutivos, y suma iterativamente todas las distancias parciales para obtener la **distancia total de la ruta** 🛩️. Esta implementación es fundamental en la planificación de vuelos ya que proporciona estimaciones precisas de distancias considerando la curvatura terrestre, lo que es esencial para cálculos de combustible, tiempo de vuelo y optimización de rutas aéreas ⛽.

```python
# Waypoints definidos como tuplas (nombre, latitud, longitud, altitud mínima)
ruta_vuelo = [
    ("MADOW", 33.9425, -118.4081, 0),      # LAX departure
    ("SADDE", 34.3015, -118.4000, 7000),   # SoCal waypoint
    ("LRAIN", 36.2049, -115.1760, 19000),  # Near Las Vegas
    ("DNVER", 39.8561, -104.6737, 0)       # Denver arrival
]

# Cálculo de distancia aproximada de ruta
import math

def distancia_haversine(lat1, lon1, lat2, lon2):
    """Calcula la distancia en km entre dos puntos usando la fórmula de Haversine"""
    R = 6371  # Radio de la Tierra en km
    dLat = math.radians(lat2 - lat1)
    dLon = math.radians(lon2 - lon1)
    a = (math.sin(dLat/2) * math.sin(dLat/2) +
         math.cos(math.radians(lat1)) * math.cos(math.radians(lat2)) *
         math.sin(dLon/2) * math.sin(dLon/2))
    c = 2 * math.atan2(math.sqrt(a), math.sqrt(1-a))
    return R * c

distancia_total = 0
for i in range(len(ruta_vuelo) - 1):
    distancia_tramo = distancia_haversine(
        ruta_vuelo[i][1], ruta_vuelo[i][2],
        ruta_vuelo[i+1][1], ruta_vuelo[i+1][2]
    )
    distancia_total += distancia_tramo
    print(f"Tramo {ruta_vuelo[i][0]} a {ruta_vuelo[i+1][0]}: {distancia_tramo:.2f} km")

print(f"Distancia total del vuelo: {distancia_total:.2f} km")

```

### Métodos Principales (Tuplas)

Debido a su inmutabilidad, las tuplas tienen muy pocos métodos incorporados en comparación con las listas:

| Método | Descripción | Ejemplo |
| --- | --- | --- |
| `count()` | Cuenta las ocurrencias de un elemento | `coordenadas.count(0)` |
| `index()` | Retorna el índice de la primera ocurrencia | `pos = avion_info.index("Dreamliner")` |

Aunque tienen pocos métodos específicos, podemos usar muchas funciones generales con tuplas:

```python
# Tupla de sensores con sus valores
lecturas_sensor = (1013.25, 22.5, 65.3, 12.2)  # presión, temp, humedad, viento

# Longitud de la tupla
print(f"Número de sensores: {len(lecturas_sensor)}")

# Valor máximo y mínimo
print(f"Lectura máxima: {max(lecturas_sensor)}")
print(f"Lectura mínima: {min(lecturas_sensor)}")

# Conversión entre tuplas y listas
lista_sensores = list(lecturas_sensor)
lista_sensores.append(98.6)  # Añadir un valor (solo posible en listas)
nuevas_lecturas = tuple(lista_sensores)  # Convertir de nuevo a tupla

```

### Ejercicios Prácticos (Tuplas)

**Ejercicio 1: Cálculo de rendimiento de aeronave**

Desarrolle una función que calcule el rendimiento de diferentes aeronaves en términos de eficiencia de combustible, velocidad y carga.

```python
def comparar_rendimiento(aeronaves):
    """
    Analiza el rendimiento de diferentes aeronaves basado en sus características.

    Args:
        aeronaves: Lista de tuplas con formato:
            (nombre, consumo_combustible, velocidad_crucero, capacidad_carga)
            donde consumo está en L/km, velocidad en km/h y carga en kg

    Returns:
        Tupla con (aeronave_más_eficiente, aeronave_más_rápida, aeronave_mayor_capacidad)
    """
    # Su código aquí
    pass

# Datos de prueba (nombre, consumo L/km, velocidad km/h, carga kg)
aviones = [
    ("Boeing 747-8F", 12.5, 908, 134200),
    ("Airbus A330-200F", 8.0, 871, 70000),
    ("Boeing 777F", 7.2, 896, 103000),
    ("Antonov An-124", 15.6, 800, 150000)
]

# Probando la función
# mejor_eficiencia, mas_rapido, mayor_carga = comparar_rendimiento(aviones)
# print(f"Más eficiente: {mejor_eficiencia}")
# print(f"Más rápido: {mas_rapido}")
# print(f"Mayor capacidad: {mayor_carga}")

```

**Ejercicio 2: Optimización de rutas de vuelo**

Implemente un algoritmo que calcule la ruta óptima entre aeropuertos considerando distancia y condiciones climáticas.

```python
def optimizar_ruta(origen, destino, waypoints, condiciones_clima):
    """
    Determina la mejor ruta considerando distancia y clima.

    Args:
        origen: Tupla (nombre, latitud, longitud)
        destino: Tupla (nombre, latitud, longitud)
        waypoints: Lista de tuplas (nombre, latitud, longitud)
        condiciones_clima: Diccionario con claves = nombres de waypoints
                          valores = índice de riesgo climático (0-10)

    Returns:
        Lista de tuplas con la ruta óptima incluyendo origen y destino
    """
    # Su código aquí
    pass

# Datos de prueba
origen = ("KLAX", 33.9425, -118.4081)  # Los Angeles
destino = ("KJFK", 40.6413, -73.7781)  # New York JFK
puntos_intermedios = [
    ("KDEN", 39.8561, -104.6737),  # Denver
    ("KORD", 41.9742, -87.9073),   # Chicago
    ("KCLE", 41.4075, -81.8511),   # Cleveland
    ("KBNA", 36.1245, -86.6782)    # Nashville
]
clima = {"KDEN": 2, "KORD": 8, "KCLE": 5, "KBNA": 3}

# Probando la función
# mejor_ruta = optimizar_ruta(origen, destino, puntos_intermedios, clima)
# print("Ruta óptima:")
# for punto in mejor_ruta:
#     print(f"  {punto[0]} ({punto[1]}, {punto[2]})")

```

**Ejercicio 3: Análisis de configuración de ala**

Desarrolle una función que analice el rendimiento de diferentes configuraciones de ala basándose en datos de túnel de viento.

```python
def analizar_perfil_ala(datos_tunel):
    """
    Analiza datos de pruebas de túnel de viento para diferentes perfiles de ala.

    Args:
        datos_tunel: Lista de tuplas con formato:
            (nombre_perfil, coef_sustentacion, coef_resistencia, angulo_ataque)

    Returns:
        Diccionario con análisis de los perfiles
    """
    # Su código aquí
    pass

# Datos de prueba (perfil, cl, cd, ángulo)
datos_prueba = [
    ("NACA2412", 0.25, 0.021, 0),
    ("NACA2412", 0.45, 0.028, 2),
    ("NACA2412", 0.85, 0.036, 5),
    ("NACA4415", 0.32, 0.022, 0),
    ("NACA4415", 0.52, 0.029, 2),
    ("NACA4415", 0.95, 0.041, 5),
    ("NACA6412", 0.36, 0.028, 0),
    ("NACA6412", 0.62, 0.039, 2),
    ("NACA6412", 1.05, 0.065, 5)
]

# Probando la función
# analisis = analizar_perfil_ala(datos_prueba)
# print(analisis)
```
