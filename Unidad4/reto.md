# **Reto de Programación: Gestión de Mantenimiento de Flota Aeronáutica ✈️**

**Duración estimada:** 3 semanas (Se irán cubriendo conceptos teóricos en clase durante este periodo)

**Modalidad:** Trabajo en grupos de 2 personas

## **1. Contexto del Problema**

Una aerolínea regional necesita un prototipo de sistema básico para gestionar las horas de vuelo de sus aeronaves y el inventario de piezas críticas sometidas a mantenimiento. Como ingenieros aeronáuticos, su misión es diseñar un algoritmo en Python que permita registrar y consultar esta información utilizando las estructuras de datos vistas en clase (Listas y Diccionarios).

## **2. Descripción de la Tarea**

Deben crear un programa interactivo por consola que permita a los técnicos de mantenimiento realizar las siguientes acciones:

1. **Registro de Aeronaves:** El programa debe permitir al usuario ingresar datos de aeronaves. Cada aeronave debe tener:
    - Matrícula (ej. HK-4532)
    - Modelo (ej. A320, ATR72)
    - Horas de vuelo acumuladas
2. **Registro de Componentes:** Por cada aeronave, se deben poder registrar componentes críticos (ej. Motor izquierdo, Tren de aterrizaje, Alabes del compresor) junto con sus horas de uso actuales y el límite de horas permitidas antes del mantenimiento.
3. **Almacenamiento de Datos:** Toda la información recolectada desde el teclado (`input()`) debe almacenarse de forma estructurada en **listas** y **diccionarios**.
4. **Consulta de Mantenimiento:** El sistema debe recorrer los datos almacenados y mostrar un reporte en pantalla de qué componentes de qué aeronaves han superado su límite de horas y requieren mantenimiento inmediato.

### **⚠️ Restricciones Técnicas MUY IMPORTANTES**

<aside>
🚫

- **Prohibido el uso de *list comprehensions*** (comprensión de listas). Todas las iteraciones deben hacerse con ciclos `for` o `while` clásicos.
**Prohibido el uso de librerías externas o funciones avanzadas no vistas en clase** (por ejemplo, Pandas, itertools, POO avanzada si no se ha visto, etc.). El código debe reflejar el nivel actual del curso.

</aside>

## **3. Entregables**

1. **Diagrama Esquemático / Diagrama de Bloques (Semana 1):**
    - Un diagrama que ilustre cómo fluirá la información desde que el usuario la ingresa hasta que se guarda en las listas/diccionarios, y cómo se estructura esa memoria (ej. Un diccionario general que contiene listas de diccionarios). Puede hacerse a mano alzada (bien presentado) o en software (Draw.io, Lucidchart).
2. **Código Fuente (`.py`) (Semana 3):**
    - El script de Python debidamente comentado.
3. **Sustentación Oral (Semana 3 - Estrategia Anti-IA):**
    - El trabajo tiene un componente de **entrevista técnica obligatoria**. Ambos miembros del equipo deberán explicar línea por línea cómo construyeron la solución y relacionar exactamente su código con el diagrama de bloques entregado. Si el código funciona pero los estudiantes no logran explicar cómo lo hace, **la nota de esa sección será 0**.

---

## **4. Rúbrica de Evaluación**

| Criterio | Excelente (5.0 - 4.0) | Aceptable (3.9 - 3.0) | Insuficiente (2.9 - 0.0) | Peso |
| --- | --- | --- | --- | --- |
| **1. Diagrama y Lógica** | El diagrama es claro, lógico y representa fielmente la estructura de datos utilizada (listas/diccionarios) y el flujo del programa. | El diagrama existe pero es confuso o difiere ligeramente de la estructura del código final entregado. | No entrega diagrama o este no tiene relación alguna con la lógica de programación requerida. | **20%** |
| **2. Uso de Estructuras (Listas/Dicts)** | Utiliza diccionarios y listas de manera correcta y anidada para almacenar los datos de aeronaves y piezas generados por el usuario. | Usa las estructuras, pero de forma redundante o ineficiente (ej. variables separadas en lugar de una lista). | No utiliza listas ni diccionarios, o lo hace de manera que el programa pierde datos. | **30%** |
| **3. Cumplimiento de Restricciones** | Respeta totalmente las restricciones: usa estructuras de control clásicas, no usa *list comprehensions* ni código ajeno al curso. | N/A (Se cumple o no se cumple). | Utiliza list comprehensions, código avanzado de dudosa autoría (ej. generado por IA) o estructuras no enseñadas. | **20%** |
| **4. Funcionalidad del Código** | El programa pide datos, los almacena correctamente e imprime el reporte de piezas que requieren mantenimiento sin errores. | El código corre pero tiene errores menores al imprimir reportes o al validar tipos de datos (ej. texto en vez de números). | El código no se ejecuta (errores de sintaxis) o no cumple con el objetivo principal del reporte de mantenimiento. | **15%** |
| **5. Sustentación (Anti-IA)** | Explica con fluidez el código, comprende la razón de ser de cada ciclo y variable, y conecta su explicación con el diagrama. | Logra explicar la funcionalidad general pero titubea o desconoce el funcionamiento de bloques específicos de su propio código. | No puede explicar cómo funciona la lógica implementada, demostrando que no es el autor intelectual del código. | **15%** |

*Nota para los estudiantes: El código perfecto no garantiza una buena nota si no demuestran apropiación del conocimiento durante la sustentación.*
