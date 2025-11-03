# Claves y Soluciones - Examen Parcial C

## Sección 1: Preguntas de Selección Múltiple (18 puntos)

### Pregunta 1 (3 puntos)
**Respuesta correcta:** B - `readline()`

**Justificación:** El método `readline()` lee una línea completa del archivo, incluyendo el carácter de nueva línea '\n', hasta encontrar el final de la línea o del archivo.

### Pregunta 2 (3 puntos)
**Respuesta correcta:** C - Rodea los valores con comillas para mantenerlos como un solo campo

**Justificación:** El módulo `csv` maneja automáticamente el quoting (comillas) cuando detecta que un valor contiene el delimitador, asegurando que se trate como un solo campo.

### Pregunta 3 (3 puntos)
**Respuesta correcta:** B - Línea 1Línea 2 (en una sola línea)

**Justificación:** El método `write()` no añade saltos de línea automáticamente. Para escribir en líneas separadas, se debe incluir explícitamente '\n'.

### Pregunta 4 (3 puntos)
**Respuesta correcta:** B - `csv.reader(file, delimiter=';')`

**Justificación:** El parámetro `delimiter` permite especificar el carácter delimitador. Por defecto es la coma, pero se puede cambiar a punto y coma, tabulador, etc.

### Pregunta 5 (3 puntos)
**Respuesta correcta:** C - `os.path.exists()`

**Justificación:** La función `os.path.exists()` del módulo `os` verifica si existe una ruta (archivo o directorio) en el sistema de archivos.

### Pregunta 6 (3 puntos)
**Respuesta correcta:** B - `writerow()`

**Justificación:** El método `writerow()` de un objeto `csv.writer` escribe una lista de valores como una fila en el archivo CSV.

---

## Sección 2: Ejercicio Práctico 1 (10 puntos)

### Solución propuesta:

```python
def main():
    try:
        # Leer el archivo
        with open('documento.txt', 'r', encoding='utf-8') as archivo:
            contenido = archivo.read()
            lineas = contenido.split('\n')
        
        # Contar líneas
        total_lineas = len(lineas)
        
        # Contar caracteres totales
        total_caracteres = len(contenido)
        
        # Contar caracteres sin espacios
        caracteres_sin_espacios = len(contenido.replace(' ', '').replace('\n', '').replace('\t', ''))
        
        # Encontrar la palabra más larga
        palabras = contenido.split()
        palabra_mas_larga = ""
        if palabras:
            palabra_mas_larga = max(palabras, key=len)
        
        # Guardar resultados
        with open('analisis.txt', 'w', encoding='utf-8') as archivo:
            archivo.write(f"Total de líneas: {total_lineas}\n")
            archivo.write(f"Total de caracteres: {total_caracteres}\n")
            archivo.write(f"Caracteres sin espacios: {caracteres_sin_espacios}\n")
            archivo.write(f"Palabra más larga: {palabra_mas_larga} ({len(palabra_mas_larga)} caracteres)\n")
        
        print("Análisis completado y guardado en analisis.txt")
        
    except FileNotFoundError:
        print("Error: El archivo documento.txt no existe")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del archivo (1 pt): Usa with y maneja encoding
- Conteo de líneas (2 pts): Cuenta líneas usando split('\n') o readlines()
- Conteo de caracteres (2 pts): len() para total y sin espacios
- Palabra más larga (3 pts): Separa palabras, usa max() con key=len
- Escritura correcta del archivo (1 pt): Formato especificado
- Manejo de errores (1 pt): Try-except

---

## Sección 3: Ejercicio Práctico 2 (12 puntos)

### Solución propuesta:

```python
import csv

def main():
    try:
        ventas_por_mes = {}
        
        # Leer el archivo CSV
        with open('ventas.csv', 'r', newline='', encoding='utf-8') as archivo:
            lector = csv.reader(archivo)
            encabezados = next(lector)  # Saltar encabezados
            
            for fila in lector:
                mes = fila[0]
                cantidad = int(fila[2])
                precio_unitario = int(fila[3])
                
                # Calcular venta
                total_venta = cantidad * precio_unitario
                
                # Acumular por mes
                if mes in ventas_por_mes:
                    ventas_por_mes[mes] += total_venta
                else:
                    ventas_por_mes[mes] = total_venta
        
        # Calcular total general
        total_general = sum(ventas_por_mes.values())
        
        # Encontrar mes con mayores ventas
        mes_mayor = max(ventas_por_mes, key=ventas_por_mes.get)
        valor_mayor = ventas_por_mes[mes_mayor]
        
        # Escribir archivo resumen
        with open('resumen_ventas.csv', 'w', newline='', encoding='utf-8') as archivo:
            escritor = csv.writer(archivo)
            escritor.writerow(['Mes', 'TotalVentas'])
            
            for mes, total in ventas_por_mes.items():
                escritor.writerow([mes, total])
        
        # Imprimir resultados
        print(f"Total general de ventas: ${total_general}")
        print(f"Mes con mayores ventas: {mes_mayor} con ${valor_mayor}")
        print("Archivo resumen_ventas.csv creado exitosamente")
        
    except FileNotFoundError:
        print("Error: El archivo ventas.csv no existe")
    except ValueError:
        print("Error: Valores numéricos inválidos en el archivo")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del CSV (3 pts): Usa csv.reader, salta encabezados, newline=''
- Cálculo de ventas por mes (3 pts): Acumula ventas usando diccionario
- Total general y mes con mayores ventas (2 pts): sum() y max()
- Escritura correcta del resumen (3 pts): Usa csv.writer con encabezados
- Manejo de tipos y buenas prácticas (1 pt): Conversión correcta, encoding

---

## Sección 4: Ejercicio Práctico 3 (10 puntos)

### Solución propuesta:

```python
def cargar_tareas():
    """Carga las tareas desde el archivo"""
    tareas = []
    try:
        with open('tareas.txt', 'r', encoding='utf-8') as archivo:
            for linea in archivo:
                if ';' in linea:
                    estado, descripcion = linea.strip().split(';', 1)
                    tareas.append({'estado': estado, 'descripcion': descripcion})
    except FileNotFoundError:
        pass
    return tareas

def guardar_tareas(tareas):
    """Guarda las tareas en el archivo"""
    with open('tareas.txt', 'w', encoding='utf-8') as archivo:
        for tarea in tareas:
            archivo.write(f"{tarea['estado']};{tarea['descripcion']}\n")

def agregar_tarea(tareas):
    """Agrega una nueva tarea"""
    descripcion = input("Ingrese la descripción de la tarea: ").strip()
    if not descripcion:
        print("Error: La descripción no puede estar vacía")
        return
    
    tareas.append({'estado': 'P', 'descripcion': descripcion})
    print("Tarea agregada exitosamente")

def marcar_completada(tareas):
    """Marca una tarea como completada"""
    listar_tareas_pendientes(tareas, mostrar_numeracion=True)
    
    try:
        numero = int(input("\nIngrese el número de la tarea a marcar como completada: "))
        
        # Encontrar la tarea pendiente por su número
        pendientes = [t for t in tareas if t['estado'] == 'P']
        
        if 1 <= numero <= len(pendientes):
            tarea = pendientes[numero - 1]
            tarea['estado'] = 'C'
            print("Tarea marcada como completada")
        else:
            print("Número de tarea inválido")
    except ValueError:
        print("Error: Debe ingresar un número válido")

def listar_tareas_pendientes(tareas, mostrar_numeracion=False):
    """Lista las tareas pendientes"""
    pendientes = [t for t in tareas if t['estado'] == 'P']
    
    if not pendientes:
        print("\nNo hay tareas pendientes")
    else:
        print("\n=== TAREAS PENDIENTES ===")
        for i, tarea in enumerate(pendientes, 1):
            if mostrar_numeracion:
                print(f"{i}. {tarea['descripcion']}")
            else:
                print(f"• {tarea['descripcion']}")

def listar_tareas_completadas(tareas):
    """Lista las tareas completadas"""
    completadas = [t for t in tareas if t['estado'] == 'C']
    
    if not completadas:
        print("\nNo hay tareas completadas")
    else:
        print("\n=== TAREAS COMPLETADAS ===")
        for tarea in completadas:
            print(f"✓ {tarea['descripcion']}")

def main():
    tareas = cargar_tareas()
    
    while True:
        print("\n=== GESTIÓN DE TAREAS ===")
        print("1. Agregar tarea")
        print("2. Marcar tarea como completada")
        print("3. Listar tareas pendientes")
        print("4. Listar tareas completadas")
        print("5. Salir")
        
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == '1':
            agregar_tarea(tareas)
        elif opcion == '2':
            marcar_completada(tareas)
        elif opcion == '3':
            listar_tareas_pendientes(tareas)
        elif opcion == '4':
            listar_tareas_completadas(tareas)
        elif opcion == '5':
            guardar_tareas(tareas)
            print("Tareas guardadas. ¡Hasta luego!")
            break
        else:
            print("Opción no válida")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Menú funcional y repetitivo (2 pts): Bucle while
- Agregar tareas correctamente (2 pts): Añade con estado 'P'
- Marcar tareas como completadas (2 pts): Cambia estado de 'P' a 'C'
- Listar tareas por estado (2 pts): Filtra por estado
- Persistencia correcta (2 pts): Carga al inicio, guarda al salir

---

## Resumen de Puntuación
- Selección Múltiple: 18 puntos (6 × 3)
- Ejercicio 1: 10 puntos
- Ejercicio 2: 12 puntos
- Ejercicio 3: 10 puntos
- **Total: 50 puntos**
