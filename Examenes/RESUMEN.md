# Resumen Ejecutivo - Exámenes Parciales A, B, C, D

## Objetivo Completado

Se han generado exitosamente 4 versiones equivalentes de exámenes parciales en formato LaTeX para evaluar competencias en manejo de archivos de texto y CSV en Python.

## Archivos Creados

### Exámenes (LaTeX)
1. **Parcial_A.tex** - Versión A con enfoque académico
2. **Parcial_B.tex** - Versión B con enfoque comercial
3. **Parcial_C.tex** - Versión C con enfoque analítico
4. **Parcial_D.tex** - Versión D con enfoque organizacional
5. **exam_template.tex** - Plantilla reutilizable mejorada

### Claves de Respuestas (Markdown)
1. **Claves_A.md** - Respuestas, justificaciones y soluciones completas en Python
2. **Claves_B.md** - Respuestas, justificaciones y soluciones completas en Python
3. **Claves_C.md** - Respuestas, justificaciones y soluciones completas en Python
4. **Claves_D.md** - Respuestas, justificaciones y soluciones completas en Python

### Documentación
1. **README.md** - Documentación completa del proyecto
2. **COMPILACION.md** - Guía de compilación LaTeX
3. **BLUEPRINT.md** - Blueprint detallado y validación
4. **RESUMEN.md** - Este documento

## Especificaciones Cumplidas

✅ **Duración:** 100 minutos por examen  
✅ **Puntuación:** 50 puntos exactos por examen  
✅ **Formato:** LaTeX profesional basado en Parcial2.tex con mejoras  
✅ **Tema:** Manejo de archivos de texto y CSV en Python  
✅ **Idioma:** Español  
✅ **Cobertura:** 100% de objetivos de Archivos.md y Reto.md  

## Estructura de Cada Examen

```
┌─────────────────────────────────────────────┐
│ Sección 1: Selección Múltiple               │
│ • 6 preguntas × 3 puntos = 18 puntos       │
│ • Tiempo: ~15 minutos                       │
│ • Nivel: Básico-Medio                       │
├─────────────────────────────────────────────┤
│ Sección 2: Ejercicio Práctico 1            │
│ • 10 puntos                                 │
│ • Tiempo: ~25 minutos                       │
│ • Nivel: Medio                              │
├─────────────────────────────────────────────┤
│ Sección 3: Ejercicio Práctico 2            │
│ • 12 puntos                                 │
│ • Tiempo: ~35 minutos                       │
│ • Nivel: Avanzado                           │
├─────────────────────────────────────────────┤
│ Sección 4: Ejercicio Práctico 3            │
│ • 10 puntos                                 │
│ • Tiempo: ~25 minutos                       │
│ • Nivel: Avanzado                           │
└─────────────────────────────────────────────┘
        Total: 50 puntos / 100 minutos
```

## Temas Evaluados

### Archivos de Texto
- ✅ Función `open()` con diferentes modos (r, w, a)
- ✅ Métodos de lectura: `read()`, `readline()`, `readlines()`
- ✅ Métodos de escritura: `write()`, `writelines()`
- ✅ Sentencia `with` para gestión de recursos
- ✅ Manejo de encoding UTF-8
- ✅ Procesamiento de contenido textual

### Archivos CSV
- ✅ Módulo csv: `reader()`, `writer()`, `DictReader()`, `DictWriter()`
- ✅ Parámetro `newline=''` para evitar líneas en blanco
- ✅ Delimitadores personalizados (punto y coma, etc.)
- ✅ Manejo de encabezados
- ✅ Quoting para valores con caracteres especiales
- ✅ Conversión de tipos de datos

### Programación Práctica
- ✅ Funciones modulares
- ✅ Menús interactivos con bucles
- ✅ Validación de entrada de usuario
- ✅ Manejo de excepciones (try-except)
- ✅ Persistencia de datos
- ✅ Estructuras de datos (listas, diccionarios, sets)

### Análisis de Datos
- ✅ Conteo (palabras, caracteres, líneas, vocales)
- ✅ Estadísticas (promedio, máximo, mínimo, suma)
- ✅ Ordenamiento y filtrado
- ✅ Agrupación por categorías
- ✅ Eliminación de duplicados

## Diferenciación entre Versiones

| Aspecto | Versión A | Versión B | Versión C | Versión D |
|---------|-----------|-----------|-----------|-----------|
| **Enfoque** | Académico | Comercial | Analítico | Organizacional |
| **Ejercicio 1** | Análisis de texto (vocales) | Estadísticas numéricas | Análisis de documentos | Procesamiento de palabras |
| **Ejercicio 2** | Notas estudiantes | Inventario productos | Ventas por mes | Nómina empleados |
| **Ejercicio 3** | Registro temperaturas | Gestión contactos | Lista de tareas | Registro de gastos |
| **Solapamiento** | Minimal | Minimal | Minimal | Minimal |

## Mejoras sobre Parcial2.tex

1. **Tipografía:** Uso de microtype para mejor justificación
2. **Código:** Entorno listings con resaltado de sintaxis Python
3. **Variables:** Macros configurables (\examversion, \examduration, \exampoints)
4. **Modularidad:** Estructura clara y reutilizable
5. **Colores:** Mejor legibilidad del código
6. **Documentación:** Comentarios inline en LaTeX

## Uso Recomendado

### Para el Docente

1. **Distribución aleatoria:** Asignar versiones A-D aleatoriamente a los estudiantes
2. **Compilación:** Seguir instrucciones en COMPILACION.md
3. **Evaluación:** Usar las rúbricas detalladas en Claves_*.md
4. **Tiempo:** Respetar estrictamente los 100 minutos
5. **Revisión:** Evaluar tanto funcionalidad como buenas prácticas

### Para Compilar

```bash
# Ubicarse en el directorio
cd Examenes

# Asegurar que existe LogoUPB.jpg o comentar líneas del logo

# Compilar cada examen
pdflatex Parcial_A.tex
pdflatex Parcial_B.tex
pdflatex Parcial_C.tex
pdflatex Parcial_D.tex
```

**Nota:** Ver COMPILACION.md para instrucciones detalladas y solución de problemas.

## Validación de Calidad

### Checklist Completado ✅

- [x] 50 puntos exactos por examen
- [x] 100 minutos de duración estimada
- [x] Cobertura completa de Archivos.md
- [x] Cobertura completa de Reto.md
- [x] Preguntas MCQ con respuesta única correcta
- [x] Distractores plausibles basados en errores comunes
- [x] Ejercicios con rúbricas claras
- [x] Soluciones completas y funcionales
- [x] Código siguiendo buenas prácticas
- [x] Formato LaTeX consistente
- [x] Instrucciones claras y sin ambigüedades
- [x] Lenguaje profesional e inclusivo
- [x] Equivalencia de dificultad entre versiones
- [x] Solapamiento minimizado entre versiones

### Matriz de Cobertura

Todos los objetivos de aprendizaje están cubiertos en cada versión:

| Objetivo | A | B | C | D |
|----------|---|---|---|---|
| Apertura de archivos | ✓ | ✓ | ✓ | ✓ |
| Lectura de archivos | ✓ | ✓ | ✓ | ✓ |
| Escritura de archivos | ✓ | ✓ | ✓ | ✓ |
| Sentencia with | ✓ | ✓ | ✓ | ✓ |
| CSV reader/writer | ✓ | ✓ | ✓ | ✓ |
| CSV Dict* | ✓ | ✓ | ✓ | ✓ |
| Manejo de errores | ✓ | ✓ | ✓ | ✓ |
| Menús interactivos | ✓ | ✓ | ✓ | ✓ |
| Persistencia | ✓ | ✓ | ✓ | ✓ |
| Estadísticas | ✓ | ✓ | ✓ | ✓ |

## Recursos Incluidos

### Para Estudiantes
- Instrucciones claras en cada examen
- Formato consistente y profesional
- Tiempo estimado por sección
- Rúbricas transparentes (en claves para el docente)

### Para Docentes
- Respuestas correctas con justificaciones
- Soluciones completas en Python
- Rúbricas de evaluación detalladas
- Matrices de trazabilidad
- Guías de uso y aplicación

### Para Administración
- Documentación completa del proceso
- Blueprint con análisis de diseño
- Validación de requisitos
- Guías de compilación

## Próximos Pasos

1. **Obtener logo:** Solicitar LogoUPB.jpg o usar placeholder
2. **Compilar:** Generar PDFs de los 4 exámenes
3. **Revisar:** Verificar formato final en PDF
4. **Distribuir:** Asignar versiones a estudiantes
5. **Aplicar:** Administrar exámenes
6. **Evaluar:** Usar rúbricas proporcionadas

## Contacto

**Preparado por:** Sistema de Generación de Exámenes  
**Para:** Henry Andrade, IEo, Ph.D.  
**Institución:** Universidad Pontificia Bolivariana - Sede Medellín  
**Facultad:** Ingeniería Aeronáutica  
**Curso:** Programación  
**Fecha:** Diciembre 2024

## Licencia y Uso

Estos exámenes son propiedad de la Universidad Pontificia Bolivariana y están destinados exclusivamente para uso académico en el curso de Programación.

**Prohibido:**
- Distribución no autorizada
- Uso comercial
- Modificación sin autorización
- Publicación en plataformas públicas

**Permitido:**
- Uso en el curso autorizado
- Adaptación para necesidades específicas (con aprobación)
- Archivo para registro académico

---

## Resumen de Archivos

```
Examenes/
├── Parcial_A.tex         (Examen versión A - LaTeX)
├── Parcial_B.tex         (Examen versión B - LaTeX)
├── Parcial_C.tex         (Examen versión C - LaTeX)
├── Parcial_D.tex         (Examen versión D - LaTeX)
├── exam_template.tex     (Plantilla reutilizable - LaTeX)
├── Claves_A.md          (Respuestas y soluciones A - Markdown)
├── Claves_B.md          (Respuestas y soluciones B - Markdown)
├── Claves_C.md          (Respuestas y soluciones C - Markdown)
├── Claves_D.md          (Respuestas y soluciones D - Markdown)
├── README.md            (Documentación principal - Markdown)
├── COMPILACION.md       (Guía de compilación - Markdown)
├── BLUEPRINT.md         (Blueprint y validación - Markdown)
└── RESUMEN.md           (Este documento - Markdown)

Total: 13 archivos
Tamaño aproximado: ~100KB
Líneas de código/documentación: ~3000+
```

---

**Estado del Proyecto: ✅ COMPLETADO**

Todos los requisitos especificados en el problem statement han sido cumplidos exitosamente.
