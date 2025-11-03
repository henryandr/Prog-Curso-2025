# Archivos

## Introducción

Los archivos son una parte fundamental de la informática y la programación. Representan una forma de almacenar datos de manera persistente, permitiendo que la información sea guardada, leída y compartida a través del tiempo. Los archivos pueden contener una amplia variedad de datos, desde texto y números hasta imágenes, videos y programas completos. En el contexto de la programación, trabajar con archivos es esencial para tareas como el manejo de configuraciones, el procesamiento de información, la lectura y escritura de datos, y muchas otras aplicaciones. A lo largo de esta introducción, exploraremos los conceptos básicos del manejo de archivos y cómo los programadores pueden utilizarlos para interactuar con datos de manera efectiva y eficiente.

Desde otra perspectiva, un archivo informático es una colección de bytes almacenados en un dispositivo. En el sistema operativo, se representa como un flujo unidimensional de bytes y se identifica por su tamaño en bytes. El software interpreta el contenido del archivo, ya sea texto, imagen o datos, según su nombre y contenido.

## Estructura interna de un archivo

La estructura interna de un archivo se compone de una secuencia lineal de bytes organizados en un formato específico. Cada archivo contiene una cabecera que almacena información sobre el tipo de archivo, su tamaño y otros metadatos. A continuación, los datos se organizan de acuerdo con la estructura definida por el formato del archivo, que puede variar ampliamente según el tipo de archivo. Los datos pueden estar compuestos por texto, números, imágenes, o cualquier otro tipo de información. El sistema operativo y las aplicaciones utilizan esta estructura para leer y escribir datos en el archivo, lo que permite su manipulación y almacenamiento de manera eficiente.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/c58121c7-f4b3-4329-98d9-6a12b1c46f82/Untitled.png)

La estructura del archivo dependerá del tipo de datos que va a contener, de esta manera las aplicaciones que los usarán, sabrán cómo procesarlos. Los programas **crean, modifican, leen, borran y gestionan** los archivos dependiendo de su funcionalidad. Por ejemplo: archivo de configuración. La persona que crea el programa decide los tipos de archivos que necesita, su nombre, su extensión y su estructura interna.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/11c7c8c4-e798-4b95-986a-0df8fdbe18cc/Untitled.png)

🧐 Para los más curiosos, aquí les dejo un artículo sobre la estructura de archivos [**Portables Ejecutables**](https://tech-zealots.com/malware-analysis/pe-portable-executable-structure-malware-analysis-part-2/).

</aside>
💡 **¡Importante!**
La manera como se organizan los datos en un archivo depende completamente de la persona que diseña el archivo

</aside>

## Extensiones de archivos

Las extensiones de archivos son etiquetas de tres o cuatro caracteres que siguen al nombre de un archivo y están separadas por un punto, como `".txt"` o `".jpg"`. Estas extensiones indican el formato o el tipo de contenido que se encuentra en el archivo. Por ejemplo, un archivo con la extensión `".docx"` generalmente contiene un documento de Microsoft Word, mientras que un archivo `".mp3"` es típicamente un archivo de audio. Las extensiones son cruciales para que el sistema operativo y las aplicaciones reconozcan y trabajen con los archivos adecuadamente, ya que les proporcionan información sobre cómo deben interpretar y procesar el contenido.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/29c9bc8f-4891-4abc-91e2-0499ab25ecbf/Untitled.png)

## Interacción con los archivos

Los archivos informáticos son elementos versátiles que pueden ser creados, movidos, modificados, aumentados, reducidos y eliminados en un sistema de almacenamiento. Por lo general, son los programas informáticos los que se encargan de gestionar estos archivos, abriendo, editando o guardando datos en ellos. Sin embargo, los usuarios también pueden desempeñar un papel activo en la manipulación de archivos, permitiéndoles interactuar con estos según sus necesidades y preferencias. Esto brinda a los usuarios un mayor control sobre sus datos y la capacidad de organizar y personalizar su espacio de almacenamiento de acuerdo con sus requisitos individuales.

En la siguiente tabla encontrarás un resumen de los gestores de archivos en diferentes sistemas operativos:

| Sistema Operativo | Gestor de Archivos |
| --- | --- |
| Windows | Explorador de Windows (File Explorer) |
| macOS | Finder |
| Linux (varios) | Nautilus (GNOME), Dolphin (KDE), Thunar (Xfce), Nemo (Cinnamon), etc. |
| Android | Administrador de archivos (varía según el fabricante) |

En sistemas operativo GNU/Linux, el gestor de archivos puede variar según el entorno de escritorio utilizado, ya que hay múltiples entornos de escritorio disponibles para elegir.

## Manejo de archivos en Python

Existen dos tipos principales de archivos: de texto y binarios. Los archivos de texto almacenan información de manera legible para los seres humanos, utilizando caracteres y símbolos. Son ideales para el almacenamiento de datos que debe ser entendido y modificado por los humanos, como documentos, código fuente y configuraciones. En contraste, los archivos binarios almacenan información de una manera que la máquina pueda entender y procesar directamente. Son utilizados para datos no legibles por humanos, como imágenes, videos, archivos ejecutables y bases de datos.

## Secuencia para manejo de archivos con Python

Observa el siguiente gráfico que describe la secuencia de pasos que deben llevarse a cabo para realizar una acción sobre un archivo.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/e85947fd-13cd-4a0f-8385-db83dd765800/Untitled.png)

1. **Apertura del archivo:** En primer lugar, debes abrir el archivo. Al abrir un archivo, puedes especificar si deseas abrirlo en modo lectura, escritura o ambos. La apertura del archivo crea una conexión entre el programa y el archivo en el sistema de archivos.
2. **Lectura de datos (si es necesario):** Si deseas leer datos del archivo, puedes usar funciones de lectura para acceder al contenido del archivo y traerlo a tu programa. Esto es común cuando necesitas procesar información que ya está en el archivo.
3. **Escritura de datos (si es necesario):** Si deseas escribir datos en el archivo, puedes utilizar funciones de escritura para agregar contenido al archivo o modificarlo. Esto es común cuando deseas guardar resultados o datos generados por tu programa en el archivo.
4. **Cierre del archivo:** Después de realizar todas las operaciones necesarias en el archivo, es importante cerrarlo correctamente. Esto libera los recursos del sistema y asegura que todos los datos se escriban en el archivo antes de que se cierre.
5. **Manejo de errores:** Durante todo el proceso, debes manejar los errores que puedan ocurrir, como archivos que no existen, problemas de permisos, etc. Esto asegura que tu programa sea robusto y maneje situaciones inesperadas de manera adecuada.

## Abrir un archivo en Python

Para abrir un archivo en Python se usa la siguiente función.

```python
var_archivo = open(*nombre_archivo [,modo][,tamaño_buffer]*)
```

El ***modo*** y el ***tamaño_buffer*** son parámetros opcionales de la función open.

`var_archivo` es el objeto que se retorna la función `open()` y con el cual tendremos acceso a todas los métodos que nos permitirán interactuar con el archivo.

## Modos de apertura

Escritura (w) siempre sobrescribe el archivo. Adición (a) escribe al final del archivo. Lectura (r) necesita que el archivo exista, de otro modo, producirá un error.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/02c0faed-67db-4983-90f8-e5241784386a/Untitled.png)

## Lectura de archivos

Existen tres métodos principales que nos permiten leer de un archivo:

`read()`: lee la cantidad especificada de Bytes. Si no se especifica una cantidad, lee todo el archivo.

```python
data = var_archivo.read(*[tamaño_datos]*) 
```

`readline()`: lee de a una sola línea (hasta encontrar el caracter **\n**) del archivo.

```python
data = var_archivo.readline() 
```

`readlines()`: lee todas las líneas (separadas por el caracter **\n**) del archivo. La variable de retorno es una lista, donde cada posición es una línea del archivo.

```python
data = var_archivo.readlines() 
```

### Ejercicio 1

1. Abre tu *block de notas* y crea un archivo de texto. Escribe en él tres líneas de texto. Guárdalo con el nombre: `texto.txt`. Recuerda dónde lo guardaste, porque vas a necesitar ese dato. Yo lo guardé en la misma carpeta de mi *script* de Python.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/86ff57e3-0a96-46be-a958-59ebefbb5e94/f062088d-9fe2-49d9-b0fc-8c4babb505e8/Untitled.png)

1. Abre el IDLE de Python o Visual Studio Code, el que prefieras. Crea un script con el siguiente código:

```python
fp = open("texto.txt","r")
datos = fp.read(5)
print(datos)
datos = fp.read(5)
print(datos)
fp.close()
```

Responde las siguientes preguntas:

1. ¿Cuál es la diferencia entre la primera y la segunda llamada al método `read()`?
2. ¿Por qué no se imprimen los mismos datos, si el código es el mismo en ambas operaciones de lectura?
3. ¿Por qué debo escribir `fp` antes de llamar al método `read()`?

### Ejercicio 2

```python
fichero = open("texto.txt","r")
linea = fichero.readline()
print(linea)
linea = fichero.readline()
print(linea)
linea = fichero.readline()
print(linea)
fichero.close()
```

Responde las siguientes preguntas:

1. ¿Por qué es importante utilizar el método `close()`?

Ahora es tu turno.

Debes crear un script de Python y probar la función `readlines()`. Escribe tus observaciones en tus apuntes.

</aside>
💡 **Reflexiona**
¿Qué sucede después de cada operación de lectura? ¿Notaste que la siguiente operación de lectura no inicia desde el comienzo del archivo, sino desde donde había quedado la lectura anterior? Debes tener esto en mente cada vez que realices una operación de lectura o escritura.

</aside>

## Escritura de archivos

Los métodos que se pueden usar para escribir los archivos son:

`write()`: escribe la variable *data* (string o numérica) en el archivo.

```python
var_archivo.write(*data*)
```

`writelines()`: escribe la variable tipo lista *data_list* en el archivo. Los elementos de la lista son concatenados (quedan unidos) y no son separados por ningún carácter.

```python
data = var_archivo.writelines(*data_list*) 
```

### Ejercicio 3

Ejecuta el siguiente código:

```python
from random import randint

lista = []
for i in range(50):
    lista.append(randint(0,100))

maximo = str(max(lista))
minimo = str(min(lista))
prom = str(sum(lista)/len(lista))

file_datos = open("datos.txt","w")
file_datos.write(maximo)
file_datos.write("\n")
file_datos.write(minimo)
file_datos.write("\n")
file_datos.write(prom)
file_datos.write("\n")
file_datos.close()
print("Archivo creado...")
```

Analiza el anterior código y responde las siguientes preguntas:

1. ¿Qué hace el programa anterior?
2. ¿Para qué sirve la línea `file_datos.write("\n")`?

## Creación de contextos (with)

En Python, la sentencia **`with`** se utiliza para crear contextos de ejecución controlados, lo que resulta fundamental para una programación más limpia y segura. La importancia del uso de contextos radica en la gestión adecuada de recursos, como archivos, conexiones de red o bases de datos, garantizando que se liberen de manera correcta y automática al finalizar su uso.

Cuando abres un archivo u otro recurso dentro de un bloque `with`, Python se encarga de asegurar que el recurso se abra al comienzo del bloque y se cierre de manera segura al final del bloque. Esto garantiza que no olvides cerrar el recurso manualmente y evita posibles fugas de recursos.

Por ejemplo, en el código que proporcioné anteriormente:

```python
with open(nombre_archivo, "r") as archivo:
    # Hacer operaciones con el archivo
# El archivo se cierra automáticamente al salir del bloque with
```

Cuando el bloque `with` se ejecuta, el archivo se abre y se asigna a la variable `archivo`. Una vez que se sale del bloque, Python se encarga de cerrar automáticamente el archivo. Esto es útil y seguro, ya que evita olvidos y errores comunes relacionados con la gestión de recursos.

### Ejercicio 4

En el siguiente ejemplo te muestro la forma de utilizar with en el manejo de archivos de texto.

```python
# Solicitamos al usuario el nombre del archivo a crear
nombre_archivo = input("Ingrese el nombre del archivo de texto: ")

# Usamos 'with' para crear el contexto y escribir datos en el archivo 
with open(nombre_archivo, 'w') as archivo:
    # Solicitamos al usuario los datos a escribir en el archivo
    datos = input("Ingrese los datos que desea escribir en el archivo: ")
    archivo.write(datos)

# Ahora usamos 'with' para crear el contexto donde leer los datos del archivo
with open(nombre_archivo, 'r') as archivo:
    contenido = archivo.read()
    print("Contenido del archivo:")
    print(contenido)
```

### Es tiempo de experimentar

Modifica el código anterior y trata de escribir diferentes tipos de datos en el archivo. Puedes verificar que los datos se hayan escrito usando el block de notas o con el mismo script de Python.

## Material complementario

## Página web

El siguiente material pertenece al sitio web: [**freecampcode.org**](https://www.freecodecamp.org/espanol/news/python-como-escribir-en-un-archivo-abrir-leer-escribir-y-otras-funciones-de-archivos-explicadas/)

Autora: **Estefania Cassingena Navone**

[**Python cómo escribir en un archivo - abrir, leer, escribir y otras funciones de archivos explicadas**](https://www.freecodecamp.org/espanol/news/python-como-escribir-en-un-archivo-abrir-leer-escribir-y-otras-funciones-de-archivos-explicadas/)

## Video en Youtube sobre archivos

**Fuente**: Canal de Youtube **UskoKruM2010**

<https://youtu.be/71xSLk8l25Q?si=UammTRGS8MPxo2mG>

---

## ❇️ Archivos separados por comas (CSV)

## **Introducción**

Los archivos CSV (Valores Separados por Comas) son un formato común para almacenar e intercambiar datos. Python proporciona varias bibliotecas y métodos para leer y escribir archivos CSV. En este tutorial, exploraremos cómo leer y escribir archivos CSV utilizando Python.

## **Lectura de Archivos CSV**

Para leer un archivo CSV, puedes utilizar la biblioteca `csv` de Python. Aquí tienes un ejemplo:

```python
import csv

with open('ejemplo.csv', 'r') as csvfile:   #usamos el manejador de contexto
    lector = csv.reader(csvfile) #se utiliza el método reader
    for fila in lector:          #con el for se itera sobre el objeto para leer
        print(fila)
```

En este ejemplo, abrimos el archivo `ejemplo.csv` en modo de lectura (`'r'`) y creamos un objeto `lector` utilizando la función `csv.reader`. El objeto `lector` es un iterador que devuelve cada fila del archivo CSV como una lista.

## Parámetro newline en modo lectura

El parámetro `newline` en el método `open` se utiliza para especificar el carácter de nueva línea que se utilizará en el archivo. En este caso, el parámetro `newline` se establece en `''`, lo que significa que no se utilizará ningún carácter de nueva línea especial.

En Python 3.x, el método `open` utiliza un carácter de nueva línea especial llamado `newline` para indicar el fin de la línea. Sin embargo, algunos archivos CSV pueden utilizar un carácter de nueva línea diferente, como `\\r\\n` o `\\n`. Si no se especifica un carácter de nueva línea, el método `open` puede interpretar incorrectamente el archivo.

Por ejemplo, si un archivo CSV utiliza `\\r\\n` como carácter de nueva línea, pero el método `open` utiliza `\\n` como carácter de nueva línea por defecto, el archivo puede no ser leído correctamente.

Al especificar `newline=''`, se indica que no se utilizará ningún carácter de nueva línea especial, lo que permite que el método `open` lea el archivo correctamente.

En resumen, el parámetro `newline` se utiliza para especificar el carácter de nueva línea que se utilizará en el archivo, lo que ayuda a evitar problemas de lectura incorrecta de archivos CSV.

Aquí tienes un ejemplo de cómo se utiliza el parámetro `newline` en el método `open`:

```python
with open('eggs.csv', newline='') as csvfile:
    reader = csv.reader(csvfile)
    for row in reader:
        print(row)
```

En este ejemplo, el parámetro `newline` se establece en `''`, lo que indica que no se utilizará ningún carácter de nueva línea especial. Esto ayuda a evitar problemas de lectura incorrecta del archivo CSV.

### Ejercicio 5

Practica el método reader que acabas de aprender. Crea un archivo separado por comas e intenta leerlo utilizando el código anterior. Este archivo será útil en los siguientes ejemplos.

## **Lectura de Archivos CSV con Encabezados**

Si tu archivo CSV tiene encabezados, puedes especificar la fila de encabezados utilizando la función `csv.reader`:

```python
import csv

with open('ejemplo.csv', 'r') as csvfile:
    lector = csv.reader(csvfile)
    encabezados = next(lector)  # Lee la fila de encabezados
    for fila in lector:
        print(fila)

```

En este ejemplo, utilizamos la función `next` para leer la fila de encabezados y almacenarla en la variable `encabezados`. Luego, iteramos sobre las filas restantes utilizando el objeto `lector`.

### Ejercicio 6

Bueno, ya te puedes imaginar el siguiente ejercicio. Agrega un encabezado a los datos que creaste atneriormente, ahora prueba el código anterior para serciorarte de que entendiste el concepto.

### Ejercicio 7

Ahora hagamos algo diferente. Abre tu archivo separado por comas en el block de notas, ahora presiona `Ctrl+R` para reemplazar las comas de tu archivo por el símbolo `:` (dos puntos). Recuerda que los archivos CSV no usan exclusivamente la coma para separar los valores, pueden aparecer otro tipo de símbolos y debes estar preraparado para manejarlos.

Ahora intenta nuevamente leer el archivo, con los códigos vistos anteriormente.

Discute con tus compañeros y con el profesor lo que sucede y cuál es la causa.

> **¿Cómo podrías solucionar el problema?** Investiga y comparte la respuesta con tus compañeros y profesor.
>

## **Escritura de Archivos CSV**

Para escribir un archivo CSV, puedes utilizar la biblioteca `csv` de Python de nuevo. Aquí tienes un ejemplo:

```python
import csv

with open('salida.csv', 'w', newline='') as csvfile:
    escritor = csv.writer(csvfile)
    escritor.writerow(['Nombre', 'Edad', 'Ciudad'])  # Escribe la fila de encabezados
    escritor.writerow(['John', 25, 'Nueva York'])
    escritor.writerow(['Jane', 30, 'Los Ángeles'])

```

En este ejemplo, abrimos el archivo `salida.csv` en modo de escritura (`'w'`) y creamos un objeto `escritor` utilizando la función `csv.writer`. Luego, escribimos la fila de encabezados utilizando el método `writerow` y dos filas adicionales.

## Parámetro newline en modo escritura

El parámetro `newline` en la función `open()` en Python se utiliza para especificar el carácter de nueva línea que se utilizará en el archivo. Por defecto, el parámetro `newline` se establece en `None`, lo que significa que el carácter de nueva línea se determinará según el sistema operativo en el que se está ejecutando el programa.

Sin embargo, en algunos casos, es posible que desees especificar un carácter de nueva línea específico para que se utilice en el archivo. Por ejemplo, si estás trabajando con un archivo que contiene caracteres de nueva línea en formato de Windows (`\\r\\n`), puedes especificar el parámetro `newline` como `'\\r\\n'` para que se utilice este carácter de nueva línea en el archivo.

Aquí te muestro un ejemplo:

```python
with open('example.txt', 'w', newline='\\r\\n') as f:
    f.write('Hello, world!')
```

En este ejemplo, se abre un archivo llamado `example.txt` en modo de escritura (`'w'`) y se especifica que se utilizará el carácter de nueva línea `\\r\\n` en el archivo. Luego, se escribe el texto `'Hello, world!'` en el archivo.

Es importante tener en cuenta que el parámetro `newline` solo se aplica cuando se abre el archivo en modo de escritura (`'w'`) o en modo de actualización (`'a'`). Si se abre el archivo en modo de lectura (`'r'`), el parámetro `newline` no tiene efecto.

### Ejercicio 8

Crea un archivo separado por comas utilizando el anterior código.

## **Escritura de Archivos CSV con Citas**

Si necesitas escribir archivos CSV con valores citados, puedes utilizar la función `csv.writer` con el parámetro `quoting` establecido en `csv.QUOTE_ALL`:

```python
import csv

with open('salida.csv', 'w', newline='') as csvfile:
    escritor = csv.writer(csvfile, quoting=csv.QUOTE_ALL)
    escritor.writerow(['Nombre', 'Edad', 'Ciudad'])  # Escribe la fila de encabezados
    escritor.writerow(['John', 25, 'Nueva York'])
    escritor.writerow(['Jane', 30, 'Los Ángeles'])

```

En este ejemplo, establecemos el parámetro `quoting` en `csv.QUOTE_ALL`, lo que citará todos los valores en el archivo CSV, pero… **¿qué son archivos csv con citas?**

💡 **!Excelente pregunta!**

La "Escritura de Archivos CSV con Citas" se refiere a la capacidad de citar los valores en un archivo CSV para que sean más fáciles de leer y entender.

En un archivo CSV, los valores suelen estar separados por comas (o otros caracteres de separación). Sin embargo, en algunos casos, los valores pueden contener comas o otros caracteres especiales que pueden causar problemas al leer el archivo. Por ejemplo, si un valor contiene una coma, el programa que lee el archivo CSV puede interpretar que es un separador de valores en lugar de un valor real.

Para solucionar este problema, se utiliza la citación de valores. La citación de valores es un mecanismo que permite rodear los valores con comillas (o otros caracteres) para que sean más fáciles de leer y entender.

En Python, la biblioteca `csv` proporciona la capacidad de citar los valores al escribir un archivo CSV utilizando el parámetro `quoting` en la función `csv.writer`. El parámetro `quoting` puede tener los siguientes valores:

- `csv.QUOTE_MINIMAL`: Citará los valores que contengan comas o otros caracteres especiales.
- `csv.QUOTE_ALL`: Citará todos los valores, incluyendo aquellos que no contengan comas o caracteres especiales.
- `csv.QUOTE_NONNUMERIC`: No citará los valores numéricos, pero sí citará los valores que contengan comas o caracteres especiales.

En el ejemplo que te mostré anteriormente, se utiliza `csv.QUOTE_ALL` para citar todos los valores en el archivo CSV. Esto significa que todos los valores, incluyendo aquellos que no contengan comas o caracteres especiales, serán rodeados con comillas para que sean más fáciles de leer y entender.

En resumen, la "Escritura de Archivos CSV con Citas" se refiere a la capacidad de citar los valores en un archivo CSV para que sean más fáciles de leer y entender, lo que puede ser especialmente útil cuando se trabajan con datos que contienen comas o caracteres especiales.

## Otros métodos de escritura

Además del método `writerow` que utilizamos anteriormente, hay otros métodos de `csv` que se pueden utilizar para escribir un archivo CSV. Aquí te menciono algunos de ellos:

1. `writerows`: Este método es similar al `writerow`, pero se utiliza para escribir varias filas en el archivo CSV de una sola vez.
2. `writerow` con `extrasaction`: Este método se utiliza para escribir una fila en el archivo CSV y especificar qué acción se debe realizar si se produce un error al escribir la fila.
3. `writerow` con `newline`: Este método se utiliza para escribir una fila en el archivo CSV y especificar el carácter de nueva línea que se utilizará en el archivo.
4. `writerow` con `dialect`: Este método se utiliza para escribir una fila en el archivo CSV y especificar el dialecto que se utilizará para leer y escribir el archivo.

Aquí tienes un ejemplo de cómo se utiliza el método `writerows` para escribir varias filas en un archivo CSV:

```python
import csv

with open('example.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    writer.writerows([
        ['Name', 'Age', 'City'],
        ['John', 25, 'New York'],
        ['Jane', 30, 'Los Angeles'],
        ['Bob', 35, 'Chicago']
    ])
```

En este ejemplo, se utiliza el método `writerows` para escribir varias filas en el archivo CSV. El método `writerows` acepta una lista de listas, donde cada lista representa una fila en el archivo CSV.

## **Recursos Adicionales**

- Documentación de Python: <https://docs.python.org/3/library/csv.html>
- Documentación de la biblioteca `csv`: <https://docs.python.org/3/library/csv.html>
