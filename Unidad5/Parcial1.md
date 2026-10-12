# Examen Final

Un aeropuerto lo contacta para desarrollar un programa que permita analizar información de sus 8 hangares. Le solicitan que el programa tenga el siguiente menú (Valor 1.0):

1. Imprimir información de los hangares **(Valor 1.5)**
2. Calcular total de aviones en los hangares **(Valor 1.5)**
3. Calcular total de cobro por uso de hangares **(Valor 1.0)**
4. Salir

Para cada una de las opciones se debe leer el archivo hangares.txt que tiene la siguiente estructura:

```text
\#hangar;tipo;\#aviones
```

Donde “#hangar” es un identificador único de cada hangar, “tipo” es una clasificación del hangar por el sistema de extinción de incendios (va de 1 a 4) y “#aviones” son la cantidad de aviones en el hangar. Por ejemplo, si se tiene el siguiente archivo:

```csv
1;1;4
4;2;2
```

La información significa que hay datos de dos de los ocho hangares:

- El hangar 1 con tipo de sistema de extinción de incendios 1 tiene 4 aviones.
- El hangar 4 con tipo de sistema de extinción de incendios 2 tiene 2 aviones.

Cada una de las opciones debe realizar las siguientes tareas:

- La opción “Imprimir información de los hangares” debe leer el archivo hangares.txt e imprimir la información en consola de todos los hangares en el archivo con el formato “El hangar X con tipo de sistema de extinción de incendios Y tiene Z aviones.”. Por ejemplo, si usamos el archivo del ejemplo de arriba, el resultado sería:

```bash
El hangar 1 con tipo de sistema de extinción de incendios 1 tiene 4 aviones.
El hangar 4 con tipo de sistema de extinción de incendios 2 tiene 2 aviones.
```

- La opción “Calcular total de aviones en los hangares” debe leer el archivo hangares.txt y calcular el total de aviones en todos los hangares que hay en el archivo. Por ejemplo, si usamos el archivo del ejemplo de arriba, el resultado sería 6 ([4 + 2])
- La opción “Calcular total de cobro por uso de hangares” debe leer el archivo hangares.txt y crear un nuevo archivo llamado cobro.txt donde se almacena el costo del alquiler total por el uso de los hangares. Para calcular el cobro se debe tener en cuenta el número de aviones y el tipo de sistema de extinción de incendios de cada hangar.

Los costos según el tipo son:

Tipo|Costo por avión (Dólares)
----|-----
1|150
2|250
3|600
4|750

El formato del archivo **cobro.txt** debe ser:

```text
\#totalAviones;cobroTotal
```

Por ejemplo, si usamos el archivo del ejemplo de arriba, el nuevo archivo sería:

```text
6;1100
```

## RECOMENDACIONES

- Realice el ejercicio por pasos, resolviendo primero con lo que se sienta más cómodo.
- Piense antes de programar. Es más fácil programar cuando se tiene claro lo que se quiere lograr.
NOTAS
- No se reciben parciales después de la fecha de entrega. Por favor, montar lo desarrollado antes de que plataforma TEAMS cierre el examen.
- Usar funciones vistas en clase. Queda a su consideración qué va en un módulo y qué como función.
- Recuerde que el examen es individual. Cualquier parecido significativo entre dos códigos será considerado como fraude.

¡Muchos éxitos!
