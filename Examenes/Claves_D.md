# Claves y Soluciones - Examen Parcial D

## Sección 1: Preguntas de Selección Múltiple (18 puntos)

### Pregunta 1 (3 puntos)
**Respuesta correcta:** A - `'w'` sobrescribe el archivo, `'a'` agrega al final

**Justificación:** El modo 'w' (write) elimina el contenido existente y sobrescribe el archivo, mientras que el modo 'a' (append) preserva el contenido y agrega nuevos datos al final.

### Pregunta 2 (3 puntos)
**Respuesta correcta:** B - No añade saltos de línea automáticamente

**Justificación:** El método `writelines()` concatena los elementos de la lista sin añadir saltos de línea entre ellos. Si se desean saltos de línea, deben incluirse en los elementos de la lista.

### Pregunta 3 (3 puntos)
**Respuesta correcta:** B - `reader = csv.reader(file, delimiter=';')`

**Justificación:** Para especificar un delimitador diferente al predeterminado (coma), se usa el parámetro `delimiter` en `csv.reader()`.

### Pregunta 4 (3 puntos)
**Respuesta correcta:** C - Puede haber pérdida de datos o recursos no liberados

**Justificación:** No cerrar archivos puede causar que los datos en buffer no se escriban al disco, además de consumir recursos del sistema innecesariamente.

### Pregunta 5 (3 puntos)
**Respuesta correcta:** B - `fieldnames`

**Justificación:** `csv.DictWriter` requiere el parámetro `fieldnames` que especifica los nombres de las columnas (claves del diccionario) que se escribirán en el CSV.

### Pregunta 6 (3 puntos)
**Respuesta correcta:** B - Hola Mundo\n (con el salto de línea)

**Justificación:** El método `readline()` incluye el carácter de nueva línea '\n' en la cadena retornada. El parámetro `end=''` en print previene añadir un salto de línea adicional.

---

## Sección 2: Ejercicio Práctico 1 (10 puntos)

### Solución propuesta:

```python
def main():
    try:
        # Leer el archivo
        with open('palabras.txt', 'r', encoding='utf-8') as archivo:
            contenido = archivo.read()
        
        # Separar palabras y convertir a minúsculas
        palabras = contenido.lower().split()
        
        # Eliminar duplicados usando set y ordenar
        palabras_unicas = sorted(set(palabras))
        
        # Contar palabras únicas
        total_unicas = len(palabras_unicas)
        
        # Escribir archivo ordenado
        with open('palabras_ordenadas.txt', 'w', encoding='utf-8') as archivo:
            for palabra in palabras_unicas:
                archivo.write(f"{palabra}\n")
        
        # Mostrar resultado
        print(f"Total de palabras únicas: {total_unicas}")
        print("Archivo palabras_ordenadas.txt creado exitosamente")
        
    except FileNotFoundError:
        print("Error: El archivo palabras.txt no existe")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del archivo (2 pts): Usa with y encoding
- Conteo de palabras (1 pt): Usa len()
- Ordenamiento alfabético (2 pts): Usa sorted()
- Eliminación de duplicados (2 pts): Usa set()
- Escritura correcta del archivo (2 pts): Una palabra por línea
- Manejo de errores (1 pt): Try-except

---

## Sección 3: Ejercicio Práctico 2 (12 puntos)

### Solución propuesta:

```python
import csv

PAGO_HORA_EXTRA = 50000

def main():
    try:
        empleados = []
        nomina_por_depto = {}
        max_salario = 0
        empleado_max = ""
        
        # Leer el archivo CSV
        with open('empleados.csv', 'r', newline='', encoding='utf-8') as archivo:
            lector = csv.reader(archivo)
            encabezados = next(lector)  # Saltar encabezados
            
            for fila in lector:
                nombre = fila[0]
                departamento = fila[1]
                salario = int(fila[2])
                horas_extra = int(fila[3])
                
                # Calcular salario total
                pago_extra = horas_extra * PAGO_HORA_EXTRA
                salario_total = salario + pago_extra
                
                # Guardar información del empleado
                empleados.append({
                    'Nombre': nombre,
                    'Departamento': departamento,
                    'SalarioBase': salario,
                    'HorasExtra': horas_extra,
                    'SalarioTotal': salario_total
                })
                
                # Acumular por departamento
                if departamento in nomina_por_depto:
                    nomina_por_depto[departamento] += salario_total
                else:
                    nomina_por_depto[departamento] = salario_total
                
                # Buscar empleado con mayor salario
                if salario_total > max_salario:
                    max_salario = salario_total
                    empleado_max = nombre
        
        # Escribir archivo de nómina
        with open('nomina.csv', 'w', newline='', encoding='utf-8') as archivo:
            escritor = csv.writer(archivo)
            escritor.writerow(['Nombre', 'Departamento', 'SalarioBase', 'HorasExtra', 'SalarioTotal'])
            
            for emp in empleados:
                escritor.writerow([
                    emp['Nombre'],
                    emp['Departamento'],
                    emp['SalarioBase'],
                    emp['HorasExtra'],
                    emp['SalarioTotal']
                ])
        
        # Imprimir resultados
        for depto, total in nomina_por_depto.items():
            print(f"Nómina total de {depto}: ${total}")
        print(f"Empleado con mayor salario: {empleado_max} con ${max_salario}")
        print("Archivo nomina.csv creado exitosamente")
        
    except FileNotFoundError:
        print("Error: El archivo empleados.csv no existe")
    except ValueError:
        print("Error: Valores numéricos inválidos")
    except Exception as e:
        print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Lectura correcta del CSV (2 pts): Usa csv.reader con newline=''
- Cálculo del salario total (3 pts): Salario + (HorasExtra × 50000)
- Cálculo de nómina por departamento (2 pts): Acumula en diccionario
- Identificación del empleado con mayor salario (2 pts): Compara durante lectura
- Escritura correcta del archivo (2 pts): Formato especificado con encabezados
- Manejo de tipos y buenas prácticas (1 pt): Conversiones correctas

---

## Sección 4: Ejercicio Práctico 3 (10 puntos)

### Solución propuesta:

```python
CATEGORIAS_VALIDAS = ['Alimentación', 'Transporte', 'Entretenimiento', 'Otros']

def cargar_gastos():
    """Carga los gastos desde el archivo"""
    gastos = []
    try:
        with open('gastos.txt', 'r', encoding='utf-8') as archivo:
            for linea in archivo:
                if ';' in linea:
                    partes = linea.strip().split(';')
                    if len(partes) == 3:
                        categoria, descripcion, monto = partes
                        gastos.append({
                            'categoria': categoria,
                            'descripcion': descripcion,
                            'monto': float(monto)
                        })
    except FileNotFoundError:
        pass
    return gastos

def guardar_gastos(gastos):
    """Guarda los gastos en el archivo"""
    with open('gastos.txt', 'w', encoding='utf-8') as archivo:
        for gasto in gastos:
            archivo.write(f"{gasto['categoria']};{gasto['descripcion']};{gasto['monto']}\n")

def registrar_gasto(gastos):
    """Registra un nuevo gasto"""
    print("\nCategorías válidas:", ", ".join(CATEGORIAS_VALIDAS))
    categoria = input("Ingrese la categoría: ").strip()
    
    if categoria not in CATEGORIAS_VALIDAS:
        print("Error: Categoría no válida")
        return
    
    descripcion = input("Ingrese la descripción: ").strip()
    if not descripcion:
        print("Error: La descripción no puede estar vacía")
        return
    
    try:
        monto = float(input("Ingrese el monto: "))
        if monto <= 0:
            print("Error: El monto debe ser un número positivo")
            return
        
        gastos.append({
            'categoria': categoria,
            'descripcion': descripcion,
            'monto': monto
        })
        print("Gasto registrado exitosamente")
        
    except ValueError:
        print("Error: El monto debe ser un número válido")

def ver_gastos(gastos):
    """Muestra todos los gastos"""
    if not gastos:
        print("\nNo hay gastos registrados")
    else:
        print("\n=== TODOS LOS GASTOS ===")
        for i, gasto in enumerate(gastos, 1):
            print(f"{i}. {gasto['categoria']} - {gasto['descripcion']}: ${gasto['monto']:.2f}")

def calcular_por_categoria(gastos):
    """Calcula el total por categoría"""
    if not gastos:
        print("\nNo hay gastos registrados")
        return
    
    totales = {}
    for gasto in gastos:
        categoria = gasto['categoria']
        if categoria in totales:
            totales[categoria] += gasto['monto']
        else:
            totales[categoria] = gasto['monto']
    
    print("\n=== TOTAL POR CATEGORÍA ===")
    for categoria, total in sorted(totales.items()):
        print(f"{categoria}: ${total:.2f}")

def calcular_total(gastos):
    """Calcula el total de todos los gastos"""
    if not gastos:
        print("\nNo hay gastos registrados")
    else:
        total = sum(gasto['monto'] for gasto in gastos)
        print(f"\nGasto total: ${total:.2f}")

def main():
    gastos = cargar_gastos()
    
    while True:
        print("\n=== REGISTRO DE GASTOS ===")
        print("1. Registrar gasto")
        print("2. Ver todos los gastos")
        print("3. Calcular total de gastos por categoría")
        print("4. Calcular gasto total")
        print("5. Salir")
        
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == '1':
            registrar_gasto(gastos)
        elif opcion == '2':
            ver_gastos(gastos)
        elif opcion == '3':
            calcular_por_categoria(gastos)
        elif opcion == '4':
            calcular_total(gastos)
        elif opcion == '5':
            guardar_gastos(gastos)
            print("Gastos guardados. ¡Hasta luego!")
            break
        else:
            print("Opción no válida")

if __name__ == "__main__":
    main()
```

**Rúbrica:**
- Menú funcional y repetitivo (2 pts): Bucle while con 5 opciones
- Registrar gastos con validación (2 pts): Valida categoría y monto > 0
- Ver todos los gastos (1 pt): Lista todos los registros
- Calcular totales por categoría (2 pts): Acumula por categoría
- Calcular gasto total (1 pt): sum() de todos los montos
- Persistencia correcta (2 pts): Carga al inicio, guarda al salir

---

## Resumen de Puntuación
- Selección Múltiple: 18 puntos (6 × 3)
- Ejercicio 1: 10 puntos
- Ejercicio 2: 12 puntos
- Ejercicio 3: 10 puntos
- **Total: 50 puntos**
