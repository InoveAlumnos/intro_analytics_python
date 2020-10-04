![Inove banner](/inove.jpg)
Inove Escuela de Código\
info@inove.com.ar\
Web: [Inove](http://inove.com.ar)

# Buscador de alquileres [Python_2]
Programa que se utiliza para buscar alquileres en mercadolibre y generar un reporte web. Luego se debe filtrar y analizar la información de interés y generar datos sobres los alquileres disponibles.

Este proyecto está basado en el proyecto de Python Inicial:\
[https://github.com/InoveAlumnos/alquileres_python_1](https://github.com/InoveAlumnos/alquileres_python_1)

La diferencia radica en que ahora no se utilizará un CSV de entrada o de salida sinó que se consumirá directamente la API de Mercadolibre.

# Entrada del sistema
El objetivo es consumir los datos que provee la siguiente URL:\
url = 'https://api.mercadolibre.com/sites/MLA/search?category=MLA1459&q=Departamentos%20Alquilers%20Mendoza%20&limit=50'

Notar que en el medio de la URL se está especificando que queremos obtener los Departamentos y Alquileres en la Ciudad de "__Mendoza__". Esto pueden modificarlo para jugar y obtener diferentes resultados.

Cuando realicen encuestas a esta URL recibiran un JSON como el siguiente

```
{
  "site_id": "MLA",
  "query": "Departamentos Alquilers Mendoza ",
  "paging": {},
  "results": [
    {},
    {},
    {},
    {},
    {},
    ...
}
```
Lo que nos interesa son los datos que se encuentran dentro de la lista de "__results__". Para poder acceder a esos datos deberan primero realizar el request de la misma forma que se realizó en clase, y luego con el JSON que obtenemos del request, encontraremos la lista de deparamentos y alquileres dentro de:
```
json_response["results"]
```
En "results" tendrá una lista de diccionarios donde cada fila contiene los datos de un departamento, esa lista la pueden iterar para recorrer los resultados obtenidos de la API. Recomendamos primero chusmear la URL en su explorador web.\
En cada diccionario de cada departamento encontrará más información dentro del diccionario "__attributes__", como por ejemplo la cantida de ambientes:\
```
      "attributes": [
        {},
        {},
        {},
        {
          "id": "ROOMS",
          "value_id": null,
          "value_name": "1",
          "value_struct": null,
          "values": [],
          "source": 1572,
          "name": "Ambientes",
          "attribute_group_id": "FIND",
          "attribute_group_name": "Ficha técnica"
        },
        {},
        {},
        {},
        {}
      ],
```
Debe extraer la información que crea relevante para este proyecto.

Se debe ingresar a su programa los rangos de precio y ambientes (y cualquier otro dato de interés del alumno) para que el programa analice los datos obtenidos.

# Salida del sistema
De los datos obtenidos se solicita analizar los siguientes resultados (y cualquier otro que desee agregar el alumno):
- Se debe informar la cantidad de alquileres disponibles, la cantidad de alquileres en pesos y en dólares.
- El programa debe hacer la selección de los alquileres deseados según el criterio de rangos ingresados. Se debe informar la cantidad de alquileres encontrados en el rango aceptado, cuál es el más barato, el más caro y el promedio, y en todos los casos la cantidad de ambientes de estos departamentos.
- Se debe generar un reporte con los alquileres encontrados en el rango deseado y enviarlos por HTTP como response y reporte del programa.

# Notas
Este proyecto puede utilizarse como base o referencia para hacer uno parecido o distinto del mismo tema. Se solicita que el contenído mínimo del proyecto alcance los especificado en las "entradas y salida del sistema" pudiendo el alumno modificar o agregar requerimientos. El objetivo en este proyecto esque consuman una API, trabajen los datos y por último retornar una respuesta HTTP con un reporte.\
En cada caso puntual se discutirá con el alumno como puede ser modificado el proyecto según sus deseos o necesidades.

Estos temas se discuten en el campus del curso en el foro correspondiente al proyecto. Cada alumno deberá iniciar un tema de discucisión sobre el proyecto que desea realizar y como este lo desea implementar.

# Consultas
alumnos@inove.com.ar
