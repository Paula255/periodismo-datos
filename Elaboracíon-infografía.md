# Elaboración de una infografía

## Gráfico

![Infografia](/img/Infografia-feliz-dia.png)

Con los datos extraídos del proyecto TRESCA, he creado un gráfico de barras verticales. En el eje X u horizontal, se representan los valores de fecha; en el Y o vertical, la variable 'cantidad de tweets'.

El color elegido para las barras es el añil. Esto favorece el contraste con el fondo blanco, pero, a la vez, mantiene el vínculo con el color corporativo de Twitter, ya que los datos se han obtenido de esta red social. Es necesario señalar que solo se han tenido en cuenta aquellas tendencias o hashtags con más de 10.000 tweets, puesto que este es el umbral a partir del cual se disponen de datos numéricos.

El gráfico busca mostrar cuántos tweets bajo el hashtag #feliz + el día correspondiente se publicaron en la primera semana de cuarentena en marzo de 2020.

## Memoria de trabajo

### Open Refine

En primer lugar, el archivo feliz.csv fue tratado desde Open Refine. Para poder trabajar con estos datos, eliminé varias columnas cuya información no era relevante para la infografía planteada. El resultado de esta primera limpieza fue un conjunto de tres columnas: fecha, texto del HT y número de tweets.

A continuación, se utilizó la opción de 'transformaciones comunes' para dar formato de fecha a la primera columna y de número a la última. Este paso es necesario para poder trabajar con las facetas, que permiten segmentar los datos con facilidad.

Facetas utilizadas:

- Faceta de línea de tiempo o *timeline facet*: gracias a esta función, se puede seleccionar la horquilla temporal deseada. En este caso, primero fue necesario eliminar una serie de líneas o *rows* que databan de 1970. Con una primera faceta de línea de tiempo, se seleccionaron estas líneas y se suprimieron utilizando la herramienta de estrella para seleccionarlas (*star rows* > *remove matching rows*). Una vez solucionado este problema, se redujo la horquilla hasta conseguir abarcar justo siete días, del 18 al 24 de marzo de 2020.

- Faceta de texto: esta faceta se aplicó a la segunda columna, que recogía los nombres de los HT o tendencias. Con el botón 'incluir', se filtraron los HT hasta visualizar solo aquellos de mi interés. Así, se excluyeron todos los datos que no correspondiesen a tweets de #Feliz + día de la semana. Además, con la función *cluster* o agrupar, se fundieron en un solo dato aquellos que guardaban semejanzas notables. Un ejemplo es #FelizSábado y #Felizsábado.

- Faceta numérica: finalmente, esta faceta hizo posible considerar solo aquellos HT que tuviesen un valor en la columna de número de tweets. Eso significa que filtró aquellos que no tuviesen una celda en blanco en esta columna.

Tras aplicar estas facetas, fue necesario reconvertir la columna de fechas en texto de nuevo para tratar el formato de la fecha. Se editaron las celdas para conseguir que solo apareciese día, mes y año. Las horas fueron suprimidas.

Finalmente, una vez se terminó el proceso de limpieza y la criba de los datos, se exportó el proyecto en formato .csv (*comma separated values* o valores separados por comas).

### Datawrapper

A continuación, cargué el .csv en Datawrapper.

#### *Check & Describe*

Datawrapper detectó que la primera columna de datos correspondía a una fecha y, consecuentemente, utilizó el formato fecha, que se corresponde al color verde según la leyenda. De la misma forma ocurre con la cantidad de tweets, que se presentó en azul por ser un dato numérico. Se comprobó que ninguna celda aparecía en rojo, lo que indicaba que no había ningún problema en el dataset, y se procedió al siguiente paso: la visualización.

#### *Visualize*

Este es uno de los pasos más importantes, puesto que se elige el tipo de gráfico deseado. En este caso, se eligió un gráfico de barras verticales o columnas por permitir comparar entre distintos días el volumen de tweets. Dado que son datos agrupados en días, he considerado preferible la columna a la línea, puesto que esta refleja mejor una evolución temporal, mientras que en este caso se busca una comparación entre bloques diarios.

En el eje horizontal se ha personalizado el formato en el que se muestra la fecha. Con ayuda del manual de Datawrapper, se ha configurado para que aparezcan las dos primeras letras del día de la semana con el objetivo de poder identificar cuál será el # correspondiente. También se ha incluido el día y  el mes (las tres primeras letras). Por tanto, el formato de fecha ha sido dd, D, MMM.

Las etiquetas de los datos aparecen cuando se sitúa el cursor sobre la columna deseada.

Para terminar, se añadió el título, la breve descripción y *footer* o pie de imagen. En este se incluye la autoría del gráfico (Paula Buedo), la fuente del dataset original (proyecto TRESCA) y la opción de descargar la imagen o los datos, además de la atribución de la herramienta. También incluye la anotación sobre la consideración en exclusividad de aquellos datos que superasen los 10.000 tweets.

#### *Publish & Embed*

Tras publicar la infografía, Datawrapper ofrece descargar la imagen en formato .png, tal y como se ha adjuntado en este archivo. Sin embargo, también permite compartirla a través de un [enlace](https://datawrapper.dwcdn.net/HYh7Z/1/). Además, ofrece un código html para incrustarla en una web:

<iframe title="Tweets deseando feliz día (2020)" aria-label="Gráfico de columnas" id="datawrapper-chart-HYh7Z" src="https://datawrapper.dwcdn.net/HYh7Z/1/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="490"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(e){if(void 0!==e.data["datawrapper-height"]){var t=document.querySelectorAll("iframe");for(var a in e.data["datawrapper-height"])for(var r=0;r<t.length;r++){if(t[r].contentWindow===e.source)t[r].style.height=e.data["datawrapper-height"][a]+"px"}}}))}();
</script>

