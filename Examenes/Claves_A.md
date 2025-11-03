# Claves y Soluciones - Examen Parcial A

## Sección 1: Preguntas de Selección Múltiple (18 puntos)

### Pregunta 1 (3 puntos)
**Respuesta correcta:** C - `open('datos.csv', 'r', newline='')`

**Justificación:** El parámetro `newline=''` es necesario cuando se trabaja con archivos CSV para evitar problemas con diferentes representaciones de saltos de línea en distintos sistemas operativos. Esto previene la adición de líneas en blanco adicionales.

### Pregunta 2 (3 puntos)
**Respuesta correcta:** B - `data1` contiene los primeros 10 caracteres y `data2` los siguientes 10

**Justificación:** Cada operación de lectura mueve el puntero del archivo hacia adelante. La segunda llamada a `read(10)` continúa desde donde terminó la primera lectura.

### Pregunta 3 (3 puntos)
**Respuesta correcta:** C - `quoting=csv.QUOTE_ALL`

**Justificación:** El parámetro `csv.QUOTE_ALL` hace que todos los valores en el CSV se rodeen con comillas, independientemente de su contenido.

### Pregunta 4 (3 puntos)
**Respuesta correcta:** B - Cierra automáticamente el archivo al salir del bloque

**Justificación:** La sentencia `with` implementa un gestor de contexto que asegura que los recursos (como archivos) se cierren automáticamente al salir del bloque, incluso si ocurre una excepción.

### Pregunta 5 (3 puntos)
**Respuesta correcta:** B - `csv.DictReader()`

**Justificación:** `csv.DictReader()` lee cada fila del CSV como un diccionario ordenado, donde las claves son los nombres de las columnas (tomados del encabezado).

### Pregunta 6 (3 puntos)
**Respuesta correcta:** B - El contenido anterior se elimina y se sobrescribe

**Justificación:** El modo 'w' (write) siempre sobrescribe el archivo si existe. Si se desea preservar el contenido anterior, se debe usar el modo 'a' (append).

---

## Sección 2: Ejercicio Práctico 1 (10 puntos)

### Solución propuesta:

```python
# Programa para contar palabras y vocales en un archivo de texto

def contar_vocales(texto):
    """Cuenta las ocurrencias de cada vocal en el texto"""
    vocales = {'a': 0, 'e': 0, 'i': 0, 'o': 0, 'u': 0}
    texto_lower = texto.lower()
    
    for vocal in vocales:
        vocales[vocal] = texto_lower.count(vocal)
    
    return vocales

def main():
    try:
        # Leer el archivo de entrada
        with open('entrada.txt', 'r', encoding='utf-8') as archivo:
            contenido = archivo.read()
        
        # Contar palabras
        palabras = contenido.split()
        total_palabras = len(palabras)
        
        # Contar vocales
        conteo_vocales = contar_vocales(contenido)
        
        # Guardar resultados
        with open('resultados.txt', 'w', encoding='utf-8') as archivo:
            archivo.write(f"Total de palabras: {total_palabras}\n")
            archivo.write(f"Vocal a: {conteo_vocales['a']}\n")
            archivo.write(f"Vocal e: {conteo_vocales['e']}\n")
            archivo.write(f"Vocal i: {conteo_vocales['i']}\n")
            archivo.write(f"Vocal o: {conteo_vocales['o']}\n")
            archivo.write(f"Vocal u: {conteo_vocales['u']}\n")
        
        print("Resultados guardados exitosamente en resultados.txt")
        
    except FileNotFoundError:
        print("Error: El archivo entrada.txt no existe")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del archivo (2 pts): Usa `with` y maneja encoding
- Conteo de palabras correcto (2 pts): Usa `split()` y `len()`
- Conteo de vocales correcto (3 pts): Itera o usa `count()`, maneja mayúsculas/minúsculas
- Escritura correcta del archivo (2 pts): Formato especificado
- Manejo de errores (1 pt): Try-except para FileNotFoundError

---

## Sección 3: Ejercicio Práctico 2 (12 puntos)

### Solución propuesta:

```python
import csv

def main():
    try:
        estudiantes = []
        
        # Leer el archivo CSV
        with open('estudiantes.csv', 'r', newline='', encoding='utf-8') as archivo:
            lector = csv.DictReader(archivo)
            
            for fila in lector:
                nombre = fila['Nombre']
                nota1 = float(fila['Nota1'])
                nota2 = float(fila['Nota2'])
                nota3 = float(fila['Nota3'])
                
                # Calcular promedio
                promedio = round((nota1 + nota2 + nota3) / 3, 2)
                
                # Determinar estado
                estado = "Aprobado" if promedio >= 3.5 else "Reprobado"
                
                estudiantes.append({
                    'Nombre': nombre,
                    'Promedio': promedio,
                    'Estado': estado
                })
        
        # Escribir el archivo de promedios
        with open('promedios.csv', 'w', newline='', encoding='utf-8') as archivo:
            campos = ['Nombre', 'Promedio', 'Estado']
            escritor = csv.DictWriter(archivo, fieldnames=campos)
            
            escritor.writeheader()
            escritor.writerows(estudiantes)
        
        print("Archivo promedios.csv creado exitosamente")
        
    except FileNotFoundError:
        print("Error: El archivo estudiantes.csv no existe")
    except ValueError:
        print("Error: Las notas deben ser valores numéricos")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del CSV con encabezados (3 pts): Usa `csv.DictReader` con `newline=''`
- Cálculo correcto de promedios (3 pts): Suma y divide entre 3, redondea a 2 decimales
- Determinación correcta del estado (2 pts): Compara con 3.5
- Escritura correcta del nuevo CSV (3 pts): Usa `csv.DictWriter` con encabezados
- Manejo de errores y buenas prácticas (1 pt): Try-except, encoding

---

## Sección 4: Ejercicio Práctico 3 (10 puntos)

### Solución propuesta:

```python
def cargar_temperaturas():
    """Carga las temperaturas desde el archivo si existe"""
    temperaturas = []
    try:
        with open('temperaturas.txt', 'r') as archivo:
            for linea in archivo:
                temperaturas.append(float(linea.strip()))
    except FileNotFoundError:
        pass  # El archivo no existe aún, lista vacía
    return temperaturas

def guardar_temperaturas(temperaturas):
    """Guarda las temperaturas en el archivo"""
    with open('temperaturas.txt', 'w') as archivo:
        for temp in temperaturas:
            archivo.write(f"{temp}\n")

def agregar_temperatura(temperaturas):
    """Agrega una nueva temperatura a la lista"""
    try:
        temp = float(input("Ingrese la temperatura: "))
        temperaturas.append(temp)
        print("Temperatura agregada exitosamente")
    except ValueError:
        print("Error: Debe ingresar un número válido")

def mostrar_temperaturas(temperaturas):
    """Muestra todas las temperaturas registradas"""
    if not temperaturas:
        print("No hay temperaturas registradas")
    else:
        print("\nTemperaturas registradas:")
        for i, temp in enumerate(temperaturas, 1):
            print(f"{i}. {temp}°C")

def calcular_promedio(temperaturas):
    """Calcula y muestra el promedio de temperaturas"""
    if not temperaturas:
        print("No hay temperaturas registradas")
    else:
        promedio = sum(temperaturas) / len(temperaturas)
        print(f"Temperatura promedio: {promedio:.2f}°C")

def main():
    # Cargar datos existentes al iniciar
    temperaturas = cargar_temperaturas()
    
    while True:
        print("\n=== REGISTRO DE TEMPERATURAS ===")
        print("1. Agregar temperatura")
        print("2. Mostrar todas las temperaturas")
        print("3. Calcular temperatura promedio")
        print("4. Guardar datos en archivo")
        print("5. Salir")
        
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == '1':
            agregar_temperatura(temperaturas)
        elif opcion == '2':
            mostrar_temperaturas(temperaturas)
        elif opcion == '3':
            calcular_promedio(temperaturas)
        elif opcion == '4':
            guardar_temperaturas(temperaturas)
            print("Datos guardados exitosamente")
        elif opcion == '5':
            # Preguntar si desea guardar antes de salir
            respuesta = input("¿Desea guardar los datos antes de salir? (s/n): ")
            if respuesta.lower() == 's':
                guardar_temperaturas(temperaturas)
                print("Datos guardados")
            print("¡Hasta luego!")
            break
        else:
            print("Opción no válida")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Menú funcional y repetitivo (2 pts): Bucle while con opciones claras
- Funciones para agregar y mostrar datos (2 pts): Funciones separadas
- Cálculo correcto del promedio (2 pts): sum() / len()
- Guardar datos en archivo (2 pts): Escribe una temperatura por línea
- Cargar datos al inicio (2 pts): Lee archivo si existe

---

## Resumen de Puntuación
- Selección Múltiple: 18 puntos (6 × 3)
- Ejercicio 1: 10 puntos
- Ejercicio 2: 12 puntos
- Ejercicio 3: 10 puntos
- **Total: 50 puntos**
