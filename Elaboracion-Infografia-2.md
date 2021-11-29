# Elaboración de una infografía

## Actuaciones del cuerpo de bomberos de Madrid

### Mapa

![Mapa](/img/Mapa-bomberos.png "Mapa de distritos")

La primera infografía es un mapa que utiliza una escala de color para representar los valores. De esta manera, se ilustran los distritos con más actuaciones del cuerpo de bomberos en el mes de octubre.

En el mapa se observa que el distrito con un número más elevado es Centro, mientras que los del noreste de la ciudad son los que menos incidencias presentan.

La escala de color utilizada, identificada en la leyenda de la esquina superior izquierda, se justifica por dos motivos:

- El rojo es un color tradicionalmente asociado a los bomberos y su uniforme en el imaginario colectivo.

- También es un color que se asocia al riesgo o peligro, dos ideas que se relacionan con la temática del mapa. Para el público, resultará evidente que hay un problema en aquellos distritos con un color más oscuro.

La imagen adjuntada es un archivo .png estático. Por ese motivo, no se visualizan las etiquetas con los nombres del distrito, por lo que se dificulta la identificación. Este problema se solventa en la imagen interactiva, ya que la etiqueta con el nombre y la cifra total del mes de octubre aparece al situar el cursor sobre un área determinada. Tampoco permite utilizar los botones de *zoom* de la esquina inferior derecha.

En el pie de foto se encuentra identificada la fuente, la autoría del mapa y la herramienta que se ha usado para crearlo. Además, se clarifica que no se han considerado todos los tipos de actuaciones, sino solo aquellas por fuegos, rescates, daños por agua y daños en construcciones.

### Gráficos de dispersión

![Dispersion](/img/Dispersion-construcciones.png "Daños en construcciones")

![Dispersion](/img/Dispersion-fuegos.png "Actuaciones por fuego")

Se trata de un gráfico que representa en el eje vertical o Y el total de actuaciones, mientras que en el horizontal o X se destina a los daños específicos. Este tipo de gráficos admite una tercera variable en el tamaño del punto, pero en esta ocasión se ha mantenido el tamaño fijo por no disponer de un dato relevante para incluirlo. Tampoco se ha cambiado la forma del punto, puesto que las opciones disponibles (estrella, diamante, cuadrado...) no parecían procedentes ni adecuadas. También se ha añadido la línea de tendencia.

Este gráfico permite una comparación entre los distintos distritos, pero también se advierte la relación entre el tipo de intervención concreta y el total durante el mes de octubre. El principal problema de estos gráficos es que, dado el volumen de datos y la longitud de algunas etiquetas, no se ven todas. Esto hace que este tipo de gráfico resulte confuso en para este *dataset* en concreto. Además, no se aprovecha esa tercera variable de cambio de tamaño de los puntos.

Los colores utilizados son el rojo para el fuego y un tono marrón para los daños en construcciones. Estos colores crean una continuidad con el primer mapa. Además, puesto que se trata de la representación de un problema relacionado con el fuego, se ha elegido un color con gran calidez para representarlo.

De la misma forma que en el mapa, en el pie de foto se indica fuente, autoría y herramienta.

### Gráficos de columnas agrupadas

![Agrupadas](/img/Agrupadas-agua.png "Daños por agua")

![Agrupadas](/img/Agrupadas-rescates.png "Rescates y salvamentos")

Estos gráficos de barras verticales o columnas agrupadas permiten, igual que los de dispersión, comparar cada tipo de daño con el total del distrito y con el resto de distritos. En el eje horizontal se presenta la etiqueta de nombre y en el vertical, la cantidad. Cada distrito tiene asociadas dos columnas: la relativa al daño concreto y la del total en el mes de octubre.

La leyenda de color se encuentra bajo el título, en la esquina superior izquierda. En este caso, los daños por agua se muestran en dos tipos de azules, uno más oscuro que el otro, por ser este el color tradicionalmente asociado a este elemento. En el caso de los salvamentos, dado que no hay un tono vinculado a ellos en el imaginario colectivo, no se ha seguido un criterio concreto. Sobre cada columna aparecen indicados los datos, algo que no es posible en el gráfico de dispersión.

Por este motivo, considero que, en comparación, este formato es más adecuado y legible.

### Gráfico de columnas apiladas

![Apiladas](/img/Apiladas-centro.png "Tipos de intervenciones en Centro")

Este gráfico permite comparar distintas variables. Por un lado, al considerar la columna en su totalidad, puede verse la evolución a lo largo de 2021 del conjunto de las incidencias. De igual forma, puede compararse la distinta evolución de los cuatro tipos de daños atendidos tanto en un mismo mes como en la horquilla temporal completa. Por tanto, puede observarse que en enero de 2021 se disparan las actuaciones por daños en construcciones (probablemente por los efectos de la borrasca Filomena) y en agosto se duplican los incendios.

El color, de nuevo, vuelve sobre la gama de rojos. Esta vez, la saturación es menor. Cada incidencia presenta un tono que varía en intensidad para favorecer la distinción entre ellas.

Las cifras aparecen identificadas dentro de cada sección. Sobre cada columna también se muestra el total. Sin embargo, no hay valores para el mes de mayo.

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

El siguiente paso ha sido elegir el degradado de colores deseado. Para ello, Datawrapper permite elegir cuatro tonos y establece un degradado entre ellos que será la escala de color.

En las etiquetas de la imagen interactiva se muestra el nombre de cada distrito y también la cifra total de incidencias. Esta etiqueta, sin embargo, se pierde a la hora de descargar la infografía en formato .png.

Dado que en el csv original había más tipos de incidencias, en la nota a pie de foto se especifica qué tipos se han considerado para elaborar este gráfico.

#### Dispersión

Para elaborar estos gráficos se han utilizado tres columnas: nombre (texto), total (cifra) e incidencia particular (cifra). Cada variable se ha asignado a un eje. Dada la separación de algunos valores, ha sido necesario modificar el rango de valores del eje horizontal. En el caso de los daños en construcciones, por ejemplo, se ha marcado un rango de 0 a 25.

El tamaño de cada punto es fijo, no responde a ninguna otra variable, pese a ser posible. Se ha intentado jugar con el tamaño del gráfico y de los puntos para intentar lograr que se identificasen, pero no ha sido posible porque algunos distritos comparten valores y se superponen en el gráfico.

#### Columnas agrupadas

En este caso, a pesar de utilizar las mismas tres columnas que el gráfico anterior, ha sido necesario transponerlas. Por tanto, los nombres de los distritos han pasado a ser las cabeceras de las columnas de cifras y los tipos de actuaciones del cuerpo y totales, las filas. 

#### Columnas apiladas

Finalmente, el gráfico de columnas apiladas también ha requerido transponer las filas y columnas. De esta forma, cada mes se sitúa en la cabecera de una columna y las filas son las intervenciones y el sumatorio.

A diferencia de los gráficos de columas agrupadas, en este caso la leyenda se ha situado a la izquierda y señala el título de cada área en la primera columna para que el público identifique a qué tipo de llamada ha acudido el cuerpo de bomberos.

## Enlaces a las visualizaciones interactivas

En algunos casos, la imagen estática que he adjuntado no muestra todas las opciones trabajadas.

[Mapa de distritos](https://datawrapper.dwcdn.net/EVHgX/1/)

[Gráfico de dispersión de fuegos](https://datawrapper.dwcdn.net/UCQpS/1/)

[Gráfico de dispersión de daños en construcciones](https://datawrapper.dwcdn.net/Nqfoq/1/)

[Gráfico de columnas agrupadas de rescates](https://datawrapper.dwcdn.net/cIhm8/1/)

[Gráfico de columnas agrupadas de daños por agua](https://datawrapper.dwcdn.net/GolKO/1/)

[Gráficos de columnas apiladas de Centro](https://datawrapper.dwcdn.net/EVHgX/1/)

