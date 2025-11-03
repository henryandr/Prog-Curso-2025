# Reto Unidad 5

---

## **Título:** Aplicación CLI (*Command Line Interface*) de análisis y graficación de datos

## Objetivo

Debes desarrollar una herramienta en Python que permita al usuario seleccionar el tipo de archivo a procesar: `.txt` o `.csv`. Para ello, el usuario deberá contar previamente con el archivo correspondiente: en el caso de los archivos `.csv`, se requiere que sean obtenidos de fuentes con datos reales disponibles en páginas de datos abiertos, como registros de calidad del aire en Medellín, estadísticas de salud pública, eficiencia de motores o consumo de combustible. La aplicación validará los datos cargados y realizará análisis estadísticos utilizando estructuras de datos básicas, además de generar visualizaciones con la biblioteca Matplotlib.

---

## **Requerimientos:**

La aplicación debe interactuar con el usuario y permitirle elegir las acciones a ejecutar, de la siguiente manera.

### **Menú Principal**

El menú principal debe mostrar tres posibles opciones:

1. Listar archivos presentes en la ruta actual o ingresar una ruta donde buscar los archivos. Esta opción es con el fin de mostrarle al usuario los nombres exactos de los archivos que existen en la carpeta de trabajo.
2. Procesar archivo de texto (.txt)
3. Procesar archivo separado por comas (.csv)
4. Salir

### **Submenú para archivos de texto (.txt)**

- Aquí debes crear un submenú donde proporcionas las siguientes opciones, cada opción llama a una **función** realizada para el caso específico:
  - **Contar número de palabras y caracteres**: Debe contar el número de palabras en el archivo de texto. Además, debe contar el número de caracteres, incluidos los espacios en blanco, y el número de caracteres sin contar los espacios en blanco. Todos los resultados deben ser mostrados en pantalla.
  - **Reemplazar una palabra por otra**: Debe permitir al usuario reemplazar una palabra por otra en el archivo de texto. La función debe recibir tanto la palabra a buscar, como la palabra por la que se tiene que reemplazar.
  - **Histograma de ocurrencia de las vocales:** Cuenta el número de ocurrencias de cada una de las vocales del archivo de texto y crea un histograma que lo muestra de forma gráfica.

### **Submenú para archivos .csv**

- Debe proporcionar las siguientes opciones, donde cada opción llama a una **función** realizada para el caso específico:
  - **Mostrar las 15 primeras filas**: con el fin de tener un vistazo rápido del documento que se va a analizar, esta función le permite al usuario observar el contenido de las primeras 15 líneas del archivo. Así, el usuario podrá decidir sus próximas acciones.
  - **Calcular Estadísticas**: el usuario le pasa a la función cuál es la columna que quiere seleccionar, de ese modo, la función calcula el número de datos, el promedio, la mediana, la desviación estándar, el valor máximo y el mínimo de dicha columna y retorna el resultado, para ser mostrado en la función principal (*main()*).
  - **Graficar una columna completa con los datos**: Debes mostrar dos gráficos diferentes. La opción debe permitir al usuario elegir una columna de datos numéricos y mostrar una gráfica de dispersión con los datos. Asegúrate de que la fila tenga datos numéricos. El gráfico debe tener título, nombre de los ejes y colores seleccionados por código. Adicionalmente, debes reorganizar los datos de alguna de las columnas para realizar un gráfico de barras o similar.

### **Otras opciones**

- Los estudiantes deben discutir con el profesor otras opciones posibles que pueden ser útiles para trabajar con archivos de texto y archivos .csv.

## **Evaluación**

La evaluación se realizará con base en la implementación correcta de los requerimientos mencionados anteriormente. Se evaluarán los siguientes aspectos:

- Correcta implementación de la lógica de programación.
- Uso correcto de las bibliotecas estándar de Python (por ejemplo, `csv` para trabajar con archivos separados por comas).
- Claridad y legibilidad del código.
- Funcionalidad y usabilidad de la aplicación.

</aside>
🚫 **¡Nota Importante!**
No se permite el uso de funciones avanzadas no vistas en clase. Por ejemplo, ***list comprehensions***. No se permite el uso de bibliotecas no vistas en clase. Cualquier uso de herramientas de Inteligencia Artificial, debe ser informado al profesor, de otro modo, el código podría ser invalidado.

</aside>

## ⚠️ Sustentación del trabajo

El trabajo debe ser sustentado de manera efectiva, ya que la nota principal se basa en la calidad de la sustentación del código. Asegúrense de que su trabajo sea claro y conciso, y que puedan defender y explicar su código de manera convincente. Recuerden que lo importante no es simplemente entregar un código que funcione correctamente, sino que también sean capaces de sustentar y explicar su lógica y diseño.

## **Sustentación del Proyecto**

La sustentación se realizará mediante una conversación con el profesor o con un video de duración aproximada de 8 minutos. Esto se debe decidir en conjunto con el profesor. El objetivo es presentar una explicación clara y concisa de las funciones del código.

## **Lo que se debe hacer:**

- Explicar cómo organizaste el código
• Mostrar el uso de condicionales, bucles y listas
• Demostrar el uso de métodos específicos para manejar cadenas de caracteres o datos separados por comas, etc.

## **Lo que no se debe hacer:**

- No explicar cosas obvias
• No se debe explicar el objetivo del reto (el profesor ya lo conoce)
• No se debe explicar detalles innecesarios

### 4. Entregables

1. Código fuente en el repositorio de la unidad 4 bien comentado y el README.
2. **Documento de análisis** (`docs/analisis.md`) explicando cómo utilizó los conceptos estudiados en la unidad.
3. **Video corto** (5–8 minutos) mostrando:
    - Explicación del análisis del problema
    - Explicación de las partes más relevantes del código fuente
    - Demostración de funcionamiento
