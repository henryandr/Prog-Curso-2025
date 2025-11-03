# Claves y Soluciones - Examen Parcial B

## Sección 1: Preguntas de Selección Múltiple (18 puntos)

### Pregunta 1 (3 puntos)
**Respuesta correcta:** B - `open('archivo.txt', 'a')`

**Justificación:** El modo 'a' (append) agrega contenido al final del archivo sin eliminar el contenido existente. El modo 'w' sobrescribiría el archivo.

### Pregunta 2 (3 puntos)
**Respuesta correcta:** B - Una lista donde cada elemento es una línea del archivo

**Justificación:** El método `readlines()` lee todas las líneas del archivo y las retorna como una lista, donde cada elemento es una cadena que representa una línea (incluyendo el carácter '\n').

### Pregunta 3 (3 puntos)
**Respuesta correcta:** B - Para evitar líneas en blanco adicionales entre filas

**Justificación:** En algunos sistemas operativos (especialmente Windows), no usar `newline=''` puede causar que se inserten líneas en blanco adicionales entre las filas del CSV debido a la conversión automática de saltos de línea.

### Pregunta 4 (3 puntos)
**Respuesta correcta:** B - Se cierra automáticamente

**Justificación:** El gestor de contexto `with` garantiza que el archivo se cierre automáticamente al salir del bloque, liberando recursos del sistema.

### Pregunta 5 (3 puntos)
**Respuesta correcta:** A - La coma (,)

**Justificación:** Por defecto, `csv.reader()` usa la coma como delimitador. Si se necesita otro delimitador, debe especificarse con el parámetro `delimiter`.

### Pregunta 6 (3 puntos)
**Respuesta correcta:** C - Se genera una excepción `FileNotFoundError`

**Justificación:** Python lanza una excepción `FileNotFoundError` cuando se intenta abrir en modo lectura un archivo que no existe.

---

## Sección 2: Ejercicio Práctico 1 (10 puntos)

### Solución propuesta:

```python
def main():
    try:
        numeros = []
        
        # Leer el archivo y extraer todos los números
        with open('notas.txt', 'r', encoding='utf-8') as archivo:
            for linea in archivo:
                # Separar los números de cada línea
                valores = linea.split()
                for valor in valores:
                    numeros.append(float(valor))
        
        # Calcular estadísticas
        cantidad = len(numeros)
        promedio = sum(numeros) / cantidad
        maximo = max(numeros)
        minimo = min(numeros)
        
        # Escribir resultados
        with open('estadisticas.txt', 'w', encoding='utf-8') as archivo:
            archivo.write(f"Cantidad de números: {cantidad}\n")
            archivo.write(f"Promedio: {promedio:.2f}\n")
            archivo.write(f"Máximo: {maximo}\n")
            archivo.write(f"Mínimo: {minimo}\n")
        
        print("Estadísticas calculadas y guardadas exitosamente")
        print(f"Cantidad: {cantidad}, Promedio: {promedio:.2f}")
        print(f"Máximo: {maximo}, Mínimo: {minimo}")
        
    except FileNotFoundError:
        print("Error: El archivo notas.txt no existe")
    except ValueError:
        print("Error: El archivo contiene valores no numéricos")
    except ZeroDivisionError:
        print("Error: El archivo está vacío")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura y procesamiento del archivo (2 pts): Lee líneas, separa valores, convierte a float
- Cálculo del promedio (2 pts): sum() / len()
- Identificación de máximo y mínimo (2 pts): Usa max() y min()
- Conteo de números (1 pt): len()
- Escritura correcta del archivo (2 pts): Formato especificado
- Manejo de errores (1 pt): Try-except apropiado

---

## Sección 3: Ejercicio Práctico 2 (12 puntos)

### Solución propuesta:

```python
import csv

def main():
    try:
        productos = []
        max_valor = 0
        producto_max = ""
        
        # Leer el archivo CSV
        with open('productos.csv', 'r', newline='', encoding='utf-8') as archivo:
            lector = csv.DictReader(archivo)
            
            for fila in lector:
                producto = fila['Producto']
                precio = int(fila['Precio'])
                cantidad = int(fila['Cantidad'])
                
                # Calcular valor total
                valor_total = precio * cantidad
                
                # Buscar el máximo
                if valor_total > max_valor:
                    max_valor = valor_total
                    producto_max = producto
                
                productos.append({
                    'Producto': producto,
                    'Precio': precio,
                    'Cantidad': cantidad,
                    'ValorTotal': valor_total
                })
        
        # Escribir el archivo de inventario
        with open('inventario.csv', 'w', newline='', encoding='utf-8') as archivo:
            campos = ['Producto', 'Precio', 'Cantidad', 'ValorTotal']
            escritor = csv.DictWriter(archivo, fieldnames=campos)
            
            escritor.writeheader()
            escritor.writerows(productos)
        
        # Mostrar resultado
        print(f"El producto con mayor valor en inventario es: {producto_max} con ${max_valor}")
        print("Archivo inventario.csv creado exitosamente")
        
    except FileNotFoundError:
        print("Error: El archivo productos.csv no existe")
    except ValueError:
        print("Error: Los valores numéricos no son válidos")
    except KeyError as e:
        print(f"Error: Falta la columna {e} en el CSV")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta con DictReader (3 pts): Usa csv.DictReader con newline=''
- Cálculo correcto del valor total (3 pts): Precio × Cantidad para cada producto
- Identificación del producto con mayor valor (2 pts): Compara valores durante la lectura
- Escritura correcta con DictWriter (3 pts): Usa csv.DictWriter con encabezados
- Manejo de tipos y buenas prácticas (1 pt): Conversión a int, manejo de errores

---

## Sección 4: Ejercicio Práctico 3 (10 puntos)

### Solución propuesta:

```python
def cargar_contactos():
    """Carga los contactos desde el archivo"""
    contactos = {}
    try:
        with open('contactos.txt', 'r', encoding='utf-8') as archivo:
            for linea in archivo:
                if ';' in linea:
                    nombre, telefono = linea.strip().split(';')
                    contactos[nombre] = telefono
    except FileNotFoundError:
        pass  # El archivo no existe aún
    return contactos

def guardar_contactos(contactos):
    """Guarda los contactos en el archivo"""
    with open('contactos.txt', 'w', encoding='utf-8') as archivo:
        for nombre, telefono in contactos.items():
            archivo.write(f"{nombre};{telefono}\n")

def agregar_contacto(contactos):
    """Agrega un nuevo contacto"""
    nombre = input("Ingrese el nombre: ").strip()
    if not nombre:
        print("Error: El nombre no puede estar vacío")
        return
    
    telefono = input("Ingrese el teléfono: ").strip()
    if not telefono:
        print("Error: El teléfono no puede estar vacío")
        return
    
    contactos[nombre] = telefono
    guardar_contactos(contactos)
    print(f"Contacto {nombre} agregado exitosamente")

def buscar_contacto(contactos):
    """Busca un contacto por nombre"""
    nombre = input("Ingrese el nombre a buscar: ").strip()
    if nombre in contactos:
        print(f"Teléfono de {nombre}: {contactos[nombre]}")
    else:
        print(f"No se encontró el contacto {nombre}")

def listar_contactos(contactos):
    """Lista todos los contactos"""
    if not contactos:
        print("No hay contactos registrados")
    else:
        print("\n=== LISTA DE CONTACTOS ===")
        for nombre, telefono in sorted(contactos.items()):
            print(f"{nombre}: {telefono}")

def eliminar_contacto(contactos):
    """Elimina un contacto"""
    nombre = input("Ingrese el nombre del contacto a eliminar: ").strip()
    if nombre in contactos:
        del contactos[nombre]
        guardar_contactos(contactos)
        print(f"Contacto {nombre} eliminado exitosamente")
    else:
        print(f"No se encontró el contacto {nombre}")

def main():
    contactos = cargar_contactos()
    
    while True:
        print("\n=== GESTIÓN DE CONTACTOS ===")
        print("1. Agregar contacto")
        print("2. Buscar contacto por nombre")
        print("3. Listar todos los contactos")
        print("4. Eliminar contacto")
        print("5. Salir")
        
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == '1':
            agregar_contacto(contactos)
        elif opcion == '2':
            buscar_contacto(contactos)
        elif opcion == '3':
            listar_contactos(contactos)
        elif opcion == '4':
            eliminar_contacto(contactos)
        elif opcion == '5':
            print("¡Hasta luego!")
            break
        else:
            print("Opción no válida")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Menú funcional y repetitivo (2 pts): Bucle while con opciones
- Funciones para agregar y listar (2 pts): Funciones separadas
- Búsqueda de contactos (2 pts): Busca en diccionario
- Eliminación de contactos (2 pts): Elimina del diccionario
- Persistencia en archivo (2 pts): Carga al inicio, guarda cambios

---

## Resumen de Puntuación
- Selección Múltiple: 18 puntos (6 × 3)
- Ejercicio 1: 10 puntos
- Ejercicio 2: 12 puntos
- Ejercicio 3: 10 puntos
- **Total: 50 puntos**
