# Exámenes Parciales - Manejo de Archivos de Texto y CSV

Este directorio contiene cuatro versiones de exámenes parciales (A, B, C y D) para el curso de Programación, enfocados en evaluar competencias en manejo de archivos de texto y CSV en Python.

## Estructura de Archivos

```
Examenes/
├── README.md                 # Este archivo
├── exam_template.tex         # Plantilla LaTeX mejorada
├── Parcial_A.tex            # Examen versión A
├── Parcial_B.tex            # Examen versión B
├── Parcial_C.tex            # Examen versión C
├── Parcial_D.tex            # Examen versión D
├── Claves_A.md              # Respuestas y soluciones versión A
├── Claves_B.md              # Respuestas y soluciones versión B
├── Claves_C.md              # Respuestas y soluciones versión C
└── Claves_D.md              # Respuestas y soluciones versión D
```

## Características de los Exámenes

### Especificaciones Generales

- **Duración:** 100 minutos
- **Puntos totales:** 50 puntos
- **Idioma:** Español
- **Lenguaje de programación:** Python
- **Formato:** LaTeX (compilable a PDF)

### Distribución de Puntos

Cada examen tiene la misma estructura y distribución de puntos:

1. **Selección Múltiple:** 18 puntos (6 preguntas × 3 puntos)
2. **Ejercicio Práctico 1:** 10 puntos
3. **Ejercicio Práctico 2:** 12 puntos
4. **Ejercicio Práctico 3:** 10 puntos

**Total:** 50 puntos

### Tiempo Estimado por Sección

- Selección Múltiple: 15 minutos
- Ejercicio Práctico 1: 25 minutos
- Ejercicio Práctico 2: 35 minutos
- Ejercicio Práctico 3: 25 minutos

**Total:** 100 minutos

## Contenido Temático

### Objetivos de Aprendizaje Evaluados

Los exámenes evalúan las siguientes competencias, basadas en Archivos.md y Graficos.md:

1. **Apertura y cierre de archivos**
   - Modos de apertura: 'r', 'w', 'a', 'r+'
   - Uso de la sentencia `with` para gestión automática de recursos
   - Manejo de encoding (UTF-8)

2. **Lectura de archivos de texto**
   - Métodos: `read()`, `readline()`, `readlines()`
   - Iteración sobre líneas
   - Procesamiento de contenido

3. **Escritura de archivos de texto**
   - Métodos: `write()`, `writelines()`
   - Formato de salida
   - Saltos de línea y formato

4. **Manejo de archivos CSV**
   - Módulo `csv`: `reader()`, `writer()`, `DictReader()`, `DictWriter()`
   - Parámetro `newline=''` y su importancia
   - Delimitadores personalizados
   - Manejo de encabezados
   - Quoting y caracteres especiales

5. **Procesamiento y análisis de datos**
   - Conteo de palabras, caracteres, líneas
   - Estadísticas: promedio, máximo, mínimo
   - Ordenamiento y eliminación de duplicados
   - Agrupación por categorías

6. **Manejo de errores**
   - `FileNotFoundError`
   - `ValueError`
   - Try-except apropiado

7. **Aplicaciones prácticas**
   - Sistemas de menú repetitivo
   - Persistencia de datos
   - CRUD (Crear, Leer, Actualizar, Eliminar)
   - Validación de entrada de usuario

## Diferencias entre Versiones

Aunque los cuatro exámenes tienen la misma estructura y nivel de dificultad, cada versión presenta:

- **Preguntas de selección múltiple diferentes:** Las preguntas evalúan los mismos conceptos pero con diferentes enfoques y distractores
- **Ejercicios prácticos únicos:** Cada versión tiene problemas diferentes pero de complejidad equivalente
- **Contextos de aplicación variados:** 
  - Versión A: Análisis de texto, notas estudiantiles, registro de temperaturas
  - Versión B: Estadísticas numéricas, inventario de productos, gestión de contactos
  - Versión C: Análisis de documentos, ventas por mes, lista de tareas
  - Versión D: Procesamiento de palabras, nómina de empleados, registro de gastos

Esta variación minimiza el riesgo de copia entre estudiantes mientras mantiene la equivalencia en dificultad y cobertura temática.

## Matriz de Trazabilidad

### Versión A

| Pregunta | Tipo | Tema | Dificultad | Puntos |
|----------|------|------|------------|--------|
| 1 | MCQ | CSV - parámetro newline | Medio | 3 |
| 2 | MCQ | Puntero de archivo en lectura | Medio | 3 |
| 3 | MCQ | CSV - quoting | Medio | 3 |
| 4 | MCQ | Sentencia with | Básico | 3 |
| 5 | MCQ | CSV - DictReader | Medio | 3 |
| 6 | MCQ | Modos de apertura | Básico | 3 |
| 7 | Práctica | Análisis de texto + escritura | Medio | 10 |
| 8 | Práctica | CSV - lectura y escritura con estadísticas | Avanzado | 12 |
| 9 | Práctica | Aplicación CRUD con menú | Avanzado | 10 |

### Versión B

| Pregunta | Tipo | Tema | Dificultad | Puntos |
|----------|------|------|------------|--------|
| 1 | MCQ | Modo append | Básico | 3 |
| 2 | MCQ | Método readlines() | Básico | 3 |
| 3 | MCQ | CSV - newline en escritura | Medio | 3 |
| 4 | MCQ | Sentencia with - cierre automático | Básico | 3 |
| 5 | MCQ | CSV - delimitador por defecto | Básico | 3 |
| 6 | MCQ | FileNotFoundError | Básico | 3 |
| 7 | Práctica | Procesamiento numérico de texto | Medio | 10 |
| 8 | Práctica | CSV - DictReader/DictWriter | Avanzado | 12 |
| 9 | Práctica | Aplicación CRUD con persistencia | Avanzado | 10 |

### Versión C

| Pregunta | Tipo | Tema | Dificultad | Puntos |
|----------|------|------|------------|--------|
| 1 | MCQ | Método readline() | Básico | 3 |
| 2 | MCQ | CSV - quoting automático | Medio | 3 |
| 3 | MCQ | Método write() sin newline | Medio | 3 |
| 4 | MCQ | CSV - parámetro delimiter | Básico | 3 |
| 5 | MCQ | os.path.exists() | Medio | 3 |
| 6 | MCQ | CSV - writerow() | Básico | 3 |
| 7 | Práctica | Análisis completo de texto | Medio | 10 |
| 8 | Práctica | CSV - agrupación y estadísticas | Avanzado | 12 |
| 9 | Práctica | Aplicación con estados | Avanzado | 10 |

### Versión D

| Pregunta | Tipo | Tema | Dificultad | Puntos |
|----------|------|------|------------|--------|
| 1 | MCQ | Diferencia entre 'w' y 'a' | Básico | 3 |
| 2 | MCQ | writelines() sin newline | Medio | 3 |
| 3 | MCQ | CSV - delimiter personalizado | Básico | 3 |
| 4 | MCQ | Importancia de cerrar archivos | Medio | 3 |
| 5 | MCQ | CSV - DictWriter fieldnames | Medio | 3 |
| 6 | MCQ | readline() incluye newline | Medio | 3 |
| 7 | Práctica | Ordenamiento y duplicados | Medio | 10 |
| 8 | Práctica | CSV - cálculos complejos | Avanzado | 12 |
| 9 | Práctica | Aplicación con validación | Avanzado | 10 |

## Errores Comunes Evaluados (Distractores)

Los exámenes incluyen distractores basados en errores comunes:

1. **Encoding:** Olvidar especificar UTF-8 o usar encoding incorrecto
2. **Newline en CSV:** No usar `newline=''` causando líneas en blanco
3. **Puntero de archivo:** No entender que el puntero avanza con cada lectura
4. **Cierre de archivos:** No cerrar archivos correctamente
5. **Modos de apertura:** Confundir 'w' (sobrescribe) con 'a' (agrega)
6. **Saltos de línea:** write() no añade '\n' automáticamente
7. **CSV delimitadores:** Usar delimitadores incorrectos o no especificarlos
8. **Conversión de tipos:** No convertir strings a números en CSV
9. **Quoting en CSV:** No manejar valores con comas internas
10. **Manejo de errores:** No implementar try-except para FileNotFoundError

## Cómo Compilar los Exámenes

### Requisitos

- LaTeX (TeX Live, MiKTeX, o MacTeX)
- Paquetes requeridos:
  - exam
  - graphicx
  - tcolorbox
  - listings
  - xcolor
  - microtype
  - geometry
  - fancyhdr
  - enumitem

### Compilación

#### Linux/Mac

```bash
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

#### Windows

```cmd
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

### Notas sobre la Compilación

1. **Logo:** Los archivos LaTeX requieren un archivo `LogoUPB.jpg` en el mismo directorio. Si no existe, se debe:
   - Proporcionar el logo de la Universidad Pontificia Bolivariana
   - O comentar las líneas que incluyen el logo en los archivos .tex

2. **Compilación múltiple:** Puede ser necesario compilar dos veces para que las referencias cruzadas y la tabla de puntos se actualicen correctamente.

3. **Salida:** La compilación genera archivos PDF listos para imprimir o distribuir digitalmente.

## Uso de las Claves de Respuesta

Los archivos `Claves_*.md` contienen:

- Respuestas correctas para las preguntas de selección múltiple
- Justificaciones detalladas de cada respuesta
- Soluciones completas y comentadas para los ejercicios prácticos
- Rúbricas de evaluación con criterios específicos
- Código Python funcional y bien estructurado

### Criterios de Evaluación

Las rúbricas consideran:

1. **Corrección funcional:** El código hace lo que se pide
2. **Buenas prácticas:** Uso de `with`, manejo de errores, nombres descriptivos
3. **Eficiencia:** Uso apropiado de estructuras de datos
4. **Formato:** Código legible y bien organizado
5. **Completitud:** Implementación de todos los requerimientos

## Referencias y Materiales de Apoyo

Los exámenes están basados en los siguientes materiales del repositorio:

1. **Archivos.md:** Conceptos fundamentales sobre manejo de archivos de texto y CSV
   - Apertura, lectura, escritura, cierre
   - Módulo csv de Python
   - Sentencia with
   - Modos de apertura

2. **Graficos.md:** Uso de matplotlib (no evaluado directamente en estos exámenes, pero puede ser útil para extensiones)

3. **Reto.md:** Aplicación práctica tipo CLI que integra los conceptos
   - Menús interactivos
   - Procesamiento de archivos
   - Estadísticas y análisis

4. **Parcial1.md y Parcial2.tex:** Ejemplos de exámenes previos que sirvieron como referencia para el estilo y formato

## Mejoras a la Plantilla LaTeX

La plantilla `exam_template.tex` incluye mejoras sobre `Parcial2.tex`:

1. **Tipografía:** Uso de microtype para mejor justificación
2. **Código:** Entorno listings con sintaxis resaltada para Python
3. **Colores:** Definición de colores para mejor legibilidad del código
4. **Variables:** Macros para versión, duración y puntos
5. **Modularidad:** Estructura más clara y reutilizable
6. **Documentación:** Comentarios explicativos en el código LaTeX

## Validación de Cobertura

### Temas de Archivos.md Cubiertos

- ✅ Estructura interna de archivos
- ✅ Extensiones de archivos
- ✅ Secuencia de manejo de archivos
- ✅ Función open() y sus parámetros
- ✅ Modos de apertura (r, w, a, etc.)
- ✅ Métodos de lectura (read, readline, readlines)
- ✅ Métodos de escritura (write, writelines)
- ✅ Sentencia with para contextos
- ✅ Archivos CSV: reader, writer, DictReader, DictWriter
- ✅ Parámetro newline en CSV
- ✅ Delimitadores y quoting
- ✅ Manejo de errores

### Temas de Reto.md Cubiertos

- ✅ Menús interactivos repetitivos
- ✅ Validación de entrada de usuario
- ✅ Procesamiento de archivos .txt y .csv
- ✅ Estadísticas: conteo, promedio, máximo, mínimo
- ✅ Funciones específicas por tarea
- ✅ Persistencia de datos
- ✅ Visualización de información (sin gráficos matplotlib)

## Recomendaciones para Aplicación

### Para el Docente

1. **Distribución:** Asignar aleatoriamente las versiones A, B, C y D a los estudiantes
2. **Recursos:** Asegurar que todos los estudiantes tengan acceso a computadores con Python instalado
3. **Tiempo:** Respetar estrictamente el límite de 100 minutos
4. **Evaluación:** Usar las rúbricas proporcionadas para evaluación consistente
5. **Revisión:** Revisar tanto la funcionalidad como las buenas prácticas de programación

### Para los Estudiantes

1. **Preparación:** Repasar los materiales de Archivos.md y practicar los ejercicios
2. **Tiempo:** Distribuir el tiempo apropiadamente entre las secciones
3. **Pruebas:** Probar el código antes de finalizar
4. **Comentarios:** Incluir comentarios explicativos cuando sea apropiado
5. **Manejo de errores:** No olvidar implementar try-except

## Contacto y Soporte

Para preguntas o sugerencias sobre estos exámenes, contactar a:

**Preparado por:** Henry Andrade, IEo, Ph.D.
**Institución:** Universidad Pontificia Bolivariana - Sede Medellín
**Facultad:** Ingeniería Aeronáutica
**Curso:** Programación

---

*Última actualización: Diciembre 2024*
