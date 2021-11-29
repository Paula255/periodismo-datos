# Elaboración de una infografía

## Actuaciones del cuerpo de bomberos de Madrid

### Mapa

![Mapa](/img/Mapa-bomberos.png "Mapa de distritos")

La primera infografía es un mapa que utiliza una escala de color para representar los valores. De esta manera, se ilustran los distritos con más actuaciones del cuerpo de bomberos en el mes de octubre.

En el mapa se observa que el distrito con un número más elevado es Centro

La escala de color utilizada, identificada en la leyenda de la esquina superior izquierda, se justifica por dos motivos:

- El rojo es un color tradicionalmente asociado a los bomberos y su uniforme en el imaginario colectivo.

- También es un color que se asocia al riesgo o peligro, dos ideas que se relacionan con la temática del mapa. Para el público, resultará evidente que hay un problema en aquellos distritos con un color más oscuro.

La imagen adjuntada es un archivo .png estático. Por ese motivo, no se visualizan las etiquetas con los nombres del distrito, por lo que se dificulta la identificación. Este problema se solventa en la imagen interactiva, ya que la etiqueta con el nombre y la cifra total del mes de octubre aparece al situar el cursor sobre un área determinada.

En el pie de foto se encuentra identificada la fuente, la autoría del mapa y la herramienta que se ha usado para crearlo. Además, se clarifica que no se han considerado todos los tipos de actuaciones, sino solo aquellas por fuegos, rescates, daños por agua y daños en construcciones.

### Gráficos de dispersión

![Dispersion](/img/Dispersion-construcciones.png "Daños en construcciones")

![Dispersion](/img/Dispersion-fuegos.png "Actuaciones por fuego")

Ejes y descripción

Colores

El principal problema de estos gráficos es que, dado el volumen de datos y la longitud de algunas etiquetas, no se ven todas. Esto hace que este tipo de gráfico resulte confuso en para este *dataset* en concreto. Además, no se aprovecha esa tercera variable de cambio de tamaño de los puntos.

### Gráficos de columnas agrupadas

![Agrupadas](/img/Agrupadas-agua.png "Daños por agua")

![Agrupadas](/img/Agrupadas-rescates.png "Rescates y salvamentos")

### Gráfico de columnas apiladas

![Apiladas](/img/Apiladas-centro.png "Tipos de intervenciones en Centro")

## Memoria

### Obtención de datos

La base de datos utilizada forma parte del [catálogo de datos abiertos](https://datos.madrid.es/portal/site/egob/menuitem.9e1e2f6404558187cf35cf3584f1a5a0/?vgnextoid=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default) del Ayuntamiento de Madrid. Para descargar el archivo .csv, he utilizado el comando wget desde la terminal.

### Limpieza de datos

Una vez descargado el documento .csv, se ha utilizado OpenRefine para limpiar y cribar los datos. El archivo original presenta los datos de las actuaciones del cuerpo de bomberos en cada distrito de Madrid a lo largo del año 2021 (hasta el mes de octubre). Las columnas recogen la cantidad de salidas según el motivo. La última columna es un sumatorio para dar el número total de actuaciones. La fecha está dividida en dos columnas separadas: mes y año.

El primer paso ha consistido en crear una sola columna de fecha concatenando las columnas de mes y año. Para ello, se ha creado una columna basada en ellas sumando ambos valores en todas las filas con un espacio como separación. Una vez creada la columna, he eliminado mes y año. Estas celdas en el documento original utilizan las mayúsculas. Con la opción de transformaciones comunes, se cambió con la expresión value.ToTitlecase('').

Los valores de las columnas de daños y totales son números. Con transformaciones comunes, se indica que se reconozcan como cifras y se cambie el formato.

Al haber eliminado varios tipos de daños e intervenciones para hacer manejable el *dataset*, la columna de totales no se ajusta al resultado adecuado. Por tanto, es necesario crear una nueva columna que sea la suma de los cuatro tipos de actuaciones que he considerado. De nuevo se ha empleado la opción de crear una columna basada en otra. La expresión de GREL utilizada ha sido: cells.["Nombre de columna 1"].value + cells.["Nombre de columna 2"] ...

El resultado final de este archivo csv con el que se va a trabajar es el siguiente:

- **Columna de fecha**. A pesar de la posibilidad de convertir estos valores en fechas con la opción value.ToDate('') tras un tratamiento de conversión cambiando el espacio por / para que sea reconocible por OpenRefine, finalmente se descarta por no ser útil para la visualización posterior. Además, dado que el *dataset* original no especifica el día ni la hora de los datos, surge un problema con la transformación: considera que son del día 1 de cada mes a las 00:00:00. Por este motivo, se ha decidido mantenerlo como texto.
- **Columna de distrito**. Se eliminan las mayúsculas a excepción de la primera de cada palabra.
- **Cuatro columnas de distintos tipos de daño**.
- **Nueva columna de totales**.

#### Facetas

Las distintas facetas permiten segmentar los datos.

- **Faceta de línea de tiempo**. Este tipo permite hacer una selección temporal. Sin embargo, necesita de una columna con formato fecha. Tras descartar este formato por los motivos expuestos anteriormente, se suprime también esta faceta.
- **Faceta de texto**. En esta ocasión, se han creado dos facetas de texto: una sobre la columna Fecha y otra sobre la columna Distrito. De esta manera, segmentamos los datos en el tiempo y espacio.

#### Exportar *comma separated values* o .csv

Jugando con las facetas y la opción de *Undo/Redo* se ha exportado un archivo .csv para cada infografía.

- Un archivo con el nombre de distrito y los totales en octubre para el mapa.
- Cuatro archivos con el nombre del distrito y las cantidades de cada tipo de actuación y el total en octubre para establecer una comparación en los gráficos de dispersión y de columas agrupadas.
- Un archivo con los distintos tipos de daños y los totales en todos los meses del año (a excepción de mayo) para un solo distrito: Centro.

### Visualización 

Para el trabajo en Datawrapper, ha sido necesario y útil consultar [Datawrapper Academy](https://academy.datawrapper.de/).

#### Mapa

Para elaborar el mapa se necesitan, al menos, dos columnas: una con el nombre de los lugares y otra con la variable que se quiere visualizar. En este caso, se ha prescindido de la columna de fechas y solo se ha considerado el sumatorio final de todas las actuaciones.

Tras cargar los datos, he elegido la plantilla de mapa de mi interés. Datawrapper dispone de un amplio y variado catálogo de distintas escalas. Una vez se ha elegido la plantilla correspondiente, es necesario solucionar errores relacionados con la denominación de los Distritos. Algunos caracteres no coinciden, por lo que hay que indicar al programa cuál es cada uno utilizando las sugerencias que ofrece.

Color

Etiquetas

Notas

#### Dispersión

Gráfico

#### Columnas agrupadas

Agrupadas

#### COlumnas apiladas

Apiladas
