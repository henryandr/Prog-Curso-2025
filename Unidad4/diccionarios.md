### Concepto y Sintaxis

Los diccionarios son colecciones **no ordenadas** y **mutables** de pares clave-valor. Las claves deben ser únicas e inmutables (como strings, números o tuplas), mientras que los valores pueden ser de cualquier tipo.

**Sintaxis básica:**

```python
# Diccionario vacío
aeronave = {}

# Diccionario con elementos
aeronave = {
    "modelo": "Boeing 787-9",
    "envergadura": 60.17,  # metros
    "longitud": 62.81,     # metros
    "mtow": 254000,        # kg
    "velocidad_max": 954   # km/h
}

# Diccionario con diferentes tipos de datos como valores
vuelo = {
    "numero": "AA123",
    "origen": "KLAX",
    "destino": "KJFK",
    "distancia": 3983,
    "a_tiempo": True,
    "tripulacion": ["Capitán Smith", "F/O Johnson", "F/E Williams"]
}

# Creación con dict()
motor = dict(fabricante="GE", modelo="GE9X", empuje=470, bypass_ratio=10)

```

**Acceso y modificación:**

```python
# Acceso a valores
print(aeronave["modelo"])  

# Modificación de valores
aeronave["mtow"] = 260000

# Añadir nuevo par clave-valor
aeronave["alcance"] = 14140  # km

# Eliminar par clave-valor
del aeronave["velocidad_max"]

# Comprobar existencia de clave
if "alcance" in aeronave:
    print(f"El alcance es {aeronave['alcance']} km")

# Método get() (devuelve None o un valor por defecto si la clave no existe)
velocidad = aeronave.get("velocidad_max", "No disponible")
```

# Ejercicios Prácticos

Estos ejercicios te ayudarán a familiarizarte con la creación, acceso y modificación de diccionarios. Lee cuidadosamente cada instrucción y escribe el código correspondiente.

### Ejercicio 1: Creación de un diccionario

Crea un diccionario llamado `vuelo` que contenga la siguiente información inicial:

- Clave `'aerolinea'` con el valor `'Avianca'`
- Clave `'vuelo'` con el valor `'AV123'`
- Clave `'origen'` con el valor `'BOG'`
- Clave `'destino'` con el valor `'MDE'`

### Ejercicio 2: Acceso a los valores

Usando el diccionario `vuelo` creado en el Ejercicio 1, extrae el valor del `'destino'` y guárdalo en una variable llamada `ciudad_llegada`. Luego, imprime esa variable.

### Ejercicio 3: Modificación de un valor existente

El vuelo ha sido desviado por mal clima. Modifica el valor de la clave `'destino'` en el diccionario `vuelo` para que ahora sea `'CLO'` (Cali). Imprime el diccionario para verificar el cambio.

### Ejercicio 4: Agregar un nuevo par clave-valor

El sistema necesita registrar el estado actual del vuelo. Agrega una nueva clave llamada `'estado'` al diccionario `vuelo` y asígnale el valor `'En el aire'`. Imprime el diccionario.

### Ejercicio 5: Uso del método `.get()` (Acceso seguro)

Intenta acceder a la clave `'piloto'` en el diccionario `vuelo`. Como no existe, si usas corchetes `[]` el programa fallará. Utiliza el método `.get()` para buscar la clave `'piloto'` y haz que devuelva el mensaje `"Piloto no asignado"` si no la encuentra. Imprime el resultado.

### Ejercicio 6: Eliminar un dato (clave y valor)

El sistema ya no necesita almacenar el número de vuelo por motivos de privacidad en esta vista. Elimina la clave `'vuelo'` (y su respectivo valor) del diccionario. Puedes usar la palabra reservada `del` o el método `.pop()`. Imprime el diccionario final.

# Ejemplos Completos en Ingeniería Aeronáutica

**Ejemplo 1: Sistema de gestión de flota**

```python
# Base de datos de flota
flota = {
    "N123AA": {
        "modelo": "Boeing 787-9",
        "año": 2018,
        "horas_vuelo": 12500,
        "ciclos": 1350,
        "estado": "En servicio",
        "base": "DFW",
        "proxima_revision": "2023-07-15"
    },
    "N456AA": {
        "modelo": "Boeing 777-300ER",
        "año": 2014,
        "horas_vuelo": 26800,
        "ciclos": 2940,
        "estado": "En mantenimiento",
        "base": "MIA",
        "proxima_revision": "2023-03-30"
    }
}

# Añadir nueva aeronave
flota["N789AA"] = {
    "modelo": "Airbus A321neo",
    "año": 2022,
    "horas_vuelo": 1200,
    "ciclos": 420,
    "estado": "En servicio",
    "base": "LAX",
    "proxima_revision": "2024-01-10"
}

# Actualizar datos de mantenimiento
flota["N456AA"]["estado"] = "En servicio"
flota["N456AA"]["horas_vuelo"] += 12  # Después de un vuelo
flota["N456AA"]["ciclos"] += 1

# Mostrar información detallada
for matricula, datos in flota.items():
    print(f"\\nAeronave: {matricula}")
    for clave, valor in datos.items():
        print(f"  {clave}: {valor}")

# Filtrar aeronaves por modelo
```

**Ejemplo 2: Cálculo de rendimiento en diferentes condiciones**

```python
# Rendimiento de aeronave en diferentes condiciones
rendimiento_b737 = {
    "nivel_mar": {
        "velocidad_despegue": 250,  # km/h
        "distancia_despegue": 2300,  # metros
        "velocidad_ascenso": 550,  # km/h
        "regimen_ascenso": 700  # pies/minuto
    },
    "altitud_media": {  # 5000 pies
        "velocidad_despegue": 260,
        "distancia_despegue": 2600,
        "velocidad_ascenso": 520,
        "regimen_ascenso": 650
    },
    "altitud_alta": {  # 10000 pies
        "velocidad_despegue": 270,
        "distancia_despegue": 3200,
        "velocidad_ascenso": 500,
        "regimen_ascenso": 550
    }
}

# Calcular penalización porcentual por altitud
def calcular_penalizacion(condiciones, referencia="nivel_mar"):
    """Calcula la penalización porcentual en rendimiento debido a la altitud"""
    resultados = {}
    condicion_base = rendimiento_b737[referencia]
    condicion_comparada = rendimiento_b737[condiciones]

    for parametro in condicion_base:
        base = condicion_base[parametro]
        comparado = condicion_comparada[parametro]

        # Para distancia, mayor es peor; para el resto, menor es peor
        if parametro == "distancia_despegue":
            penalizacion = (comparado - base) / base * 100
        else:
            penalizacion = (base - comparado) / base * 100

        resultados[parametro] = round(penalizacion, 1)

    return resultados

# Calcular penalizaciones
penalizacion_alta = calcular_penalizacion("altitud_alta")
print("\\nPenalización por operar en altitud alta (%):")
for parametro, valor in penalizacion_alta.items():
    print(f"  {parametro}: {valor}%")
```

### Métodos Principales (Diccionarios)

| Método | Descripción | Ejemplo |
| --- | --- | --- |
| `clear()` | Elimina todos los elementos | `aeronave.clear()` |
| `copy()` | Retorna una copia superficial | `copia = aeronave.copy()` |
| `fromkeys()` | Crea diccionario con claves y valor por defecto | `dict.fromkeys(["mtow", "zfw"], 0)` |
| `get()` | Retorna valor de clave o valor por defecto | `aeronave.get("modelo", "Desconocido")` |
| `items()` | Retorna vista de pares clave-valor | `for in aeronave.items(): ...` |
| `keys()` | Retorna vista de claves | `for k in aeronave.keys(): ...` |
| `values()` | Retorna vista de valores | `for v in aeronave.values(): ...` |
| `pop()` | Elimina clave y retorna su valor | `mtow = aeronave.pop("mtow")` |
| `popitem()` | Elimina y retorna par arbitrario (último) | `ultimo = aeronave.popitem()` |
| `setdefault()` | Inserta par si clave no existe | `aeronave.setdefault("alcance", 0)` |
| `update()` | Actualiza con pares de otro diccionario | `aeronave.update(datos_nuevos)` |

**Ejemplo de uso avanzado:**

```python
# Datos meteorológicos para diferentes aeropuertos
meteo = {
    "KLAX": {"temp": 22, "viento": 10, "direccion": 270, "visibilidad": 10000},
    "KJFK": {"temp": 15, "viento": 15, "direccion": 180, "visibilidad": 8000},
    "KORD": {"temp": 5, "viento": 25, "direccion": 320, "visibilidad": 5000}
}

# Añadir un nuevo aeropuerto con setdefault
meteo.setdefault("KMIA", {"temp": 28, "viento": 8, "direccion": 90, "visibilidad": 9000})

# Actualizar datos existentes con update
meteo["KORD"].update({"temp": 3, "visibilidad": 3000, "precipitacion": "nieve"})

# Crear copia y hacer modificaciones
meteo_actualizado = meteo.copy()
for aeropuerto in meteo_actualizado:
    # Convertir temperatura de Celsius a Fahrenheit
    meteo_actualizado[aeropuerto]["temp_F"] = round(meteo_actualizado[aeropuerto]["temp"] * 9/5 + 32, 1)

    # Categorizar visibilidad
    if meteo_actualizado[aeropuerto]["visibilidad"] < 5000:
        meteo_actualizado[aeropuerto]["categoria"] = "IMC"  # Instrumental Meteorological Conditions
    else:
        meteo_actualizado[aeropuerto]["categoria"] = "VMC"  # Visual Meteorological Conditions

# Mostrar datos actualizados
for aeropuerto, datos in meteo_actualizado.items():
    print(f"\\nAeropuerto: {aeropuerto}")
    for parametro, valor in datos.items():
        print(f"  {parametro}: {valor}")
```

### Ejercicios Prácticos (Diccionarios)

**Ejercicio 1: Sistema de gestión de mantenimiento**

Desarrolle un sistema para gestionar el mantenimiento de una flota de aeronaves, incluyendo el seguimiento de componentes y alertas de mantenimiento.

```python
def actualizar_horas_vuelo(flota, registro_vuelos):
    """
    Actualiza las horas de vuelo y ciclos de componentes basados en nuevos vuelos.

    Args:
        flota: Dict con datos de aeronaves y componentes
        registro_vuelos: Lista de dicts con datos de vuelos recientes
            {matricula, horas, ciclos, fecha}

    Returns:
        Dict actualizado y lista de alertas de mantenimiento necesario
    """
    # Su código aquí
    pass

# Datos de prueba
flota_aeronaves = {
    "N123AB": {
        "modelo": "Boeing 737-800",
        "componentes": {
            "motores": {"horas_totales": 12500, "ciclos": 4200, "limite_horas": 15000},
            "tren_aterrizaje": {"horas_totales": 10000, "ciclos": 4200, "limite_ciclos": 5000},
            "apu": {"horas_totales": 8500, "ciclos": 6300, "limite_horas": 10000}
        }
    },
    "N456CD": {
        "modelo": "Airbus A320",
        "componentes": {
            "motores": {"horas_totales": 18200, "ciclos": 7300, "limite_horas": 20000},
            "tren_aterrizaje": {"horas_totales": 15600, "ciclos": 7300, "limite_ciclos": 8000},
            "apu": {"horas_totales": 12400, "ciclos": 9100, "limite_horas": 15000}
        }
    }
}

vuelos_recientes = [
    {"matricula": "N123AB", "horas": 4.5, "ciclos": 2, "fecha": "2023-03-15"},
    {"matricula": "N456CD", "horas": 3.2, "ciclos": 1, "fecha": "2023-03-15"},
    {"matricula": "N123AB", "horas": 5.8, "ciclos": 2, "fecha": "2023-03-16"},
    {"matricula": "N456CD", "horas": 6.7, "ciclos": 3, "fecha": "2023-03-16"}
]

# Probando la función
# flota_actualizada, alertas = actualizar_horas_vuelo(flota_aeronaves, vuelos_recientes)
# print("\\nAlertas de mantenimiento:")
# for alerta in alertas:
#     print(f"  {alerta}")
```

**Ejercicio 2: Análisis de rendimiento de aeronave**

Implemente un algoritmo que analice el rendimiento de una aeronave en diferentes condiciones operativas y proporcione recomendaciones para optimizarlo.

```python
def analizar_rendimiento(datos_vuelo, especificaciones):
    """
    Analiza el rendimiento de una aeronave comparando datos de vuelo
    con especificaciones del fabricante.

    Args:
        datos_vuelo: Dict con registros reales de operación
        especificaciones: Dict con valores óptimos según fabricante

    Returns:
        Dict con análisis y recomendaciones
    """
    # Su código aquí
    pass

# Datos de prueba
especificaciones_b737 = {
    "consumo_optimo": {  # litros/hora
        "crucero": {"FL290": 2200, "FL330": 2100, "FL370": 2050},
        "ascenso": {"inicial": 3100, "medio": 2800, "final": 2500},
        "descenso": {"inicial": 1800, "medio": 1500, "final": 1200}
    },
    "velocidades_optimas": {  # nudos
        "crucero": {"FL290": 450, "FL330": 460, "FL370": 470},
        "ascenso": {"inicial": 290, "medio": 280, "final": 270},
        "descenso": {"inicial": 280, "medio": 270, "final": 250}
    }
}

datos_operacionales = {
    "vuelo_123": {
        "consumo": {
            "crucero": {"FL290": 2350, "FL330": 2150, "FL370": 2080},
            "ascenso": {"inicial": 3300, "medio": 2950, "final": 2600},
            "descenso": {"inicial": 1850, "medio": 1600, "final": 1300}
        },
        "velocidades": {
            "crucero": {"FL290": 440, "FL330": 455, "FL370": 465},
            "ascenso": {"inicial": 280, "medio": 270, "final": 260},
            "descenso": {"inicial": 290, "medio": 280, "final": 260}
        }
    }
}

# Probando la función
# analisis = analizar_rendimiento(datos_operacionales["vuelo_123"], especificaciones_b737)
# print("\\nAnálisis de rendimiento:")
# for categoria, datos in analisis.items():
#     print(f"\\n{categoria.upper()}:")
#     for subcategoria, valores in datos.items():
#         print(f"  {subcategoria}: {valores}")
```

**Ejercicio 3: Simulador de costos operativos**

Desarrolle un simulador que calcule los costos operativos de diferentes rutas y aeronaves para ayudar en la toma de decisiones económicas.

```python
def simular_costos(rutas, aeronaves, precios_combustible, tarifas_aeroportuarias):
    """
    Simula los costos operativos de diferentes combinaciones de rutas y aeronaves.

    Args:
        rutas: Dict con información de rutas (distancia, tiempo estimado)
        aeronaves: Dict con especificaciones de aeronaves
        precios_combustible: Dict con precios de combustible por aeropuerto
        tarifas_aeroportuarias: Dict con tarifas por aeropuerto

    Returns:
        Dict con análisis de costos por combinación ruta-aeronave
    """
    # Su código aquí
    pass

# Datos de prueba
rutas_ejemplo = {
    "LAX-JFK": {"distancia": 3983, "tiempo_estimado": 5.5, "origen": "LAX", "destino": "JFK"},
    "JFK-LHR": {"distancia": 5541, "tiempo_estimado": 7.0, "origen": "JFK", "destino": "LHR"},
    "LAX-NRT": {"distancia": 8773, "tiempo_estimado": 11.5, "origen": "LAX", "destino": "NRT"}
}

aeronaves_ejemplo = {
    "B737-800": {
        "capacidad_pax": 162,
        "consumo": 2600,  # litros/hora
        "velocidad_crucero": 840,  # km/h
        "costos_tripulacion": 1200,  #
```
