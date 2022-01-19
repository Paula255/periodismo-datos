# Examen de Paula Buedo Torrejón. Periodismo de Datos, grupo 61.

## 4. ¿Qué medio de comunicación inglés es fundamental en el periodismo y la visualización de datos?

*The Guardian*, especialmente su *Datablog*, es un medio fundamental y pionero gracias a las aportaciones de Simon Rogers.

## 5. ¿Qué lenguajes informáticos conoces? Razona la respuesta.

Hay dos tipos de lenguajes informáticos (que nuestro software entiende): estructurales y de programación. Un ejemplo de lenguaje estructural es HTML. En cuanto a los lenguajes de programación, a pesar de no haberlos utilizados, conozco Java, C, C++, Python o R.

## 6. Cuál es la diferencia entre Internet y la Web. Razona la respuesta.

La web es una parte de Internet, pero no todo internet es la web. Internet es una red de redes que funciona gracias a los protocolos TCP/IP. Consta de unos 65500 puertos de comunicación. En uno de ellos se aloja la web, pero otros son utilizados, por ejemplo, por aplicaciones de mensajería instantanea o el correo electrónico (aunque también podemos acceder a ellas a través de la web).

## 7. ¿Qué fue determinante para el nacimiento del periodismo de datos moderno?

Podemos situar el nacimiento entorno a los años 2006 y 2008. En estas fechas, confluyeron tres fenómenos fundamentales:

- Abundancia de software libre.
- HTML5.
- OpenData.

## 8. Qué saberes están implicados en periodismo de datos. Razona la respuesta.

Hay tres saberes fundamentales: periodismo, datos y visualización. El periodismo es fundamental en tanto que es necesaria la investigación y la comunicación de los resultados de la misma. La materia prima de esta investigación son los datos, que por sí solos son registros electrónicos abstractos. Es necesario convertir esos datos en información que aporte un conocimiento. La visualización está muy relacionada con la forma de tratar esa información y transmitirla de forma efectiva. El periodismo de datos, además de investigar, debe cuidar esa visualización: códigos compartidos, accesibilidad, organización y limpieza...

## 11. Qué tipos de datos hay

Distinguimos 5 tipos de datos:

- Numéricos: estos valores son, evidentemente, números. Sin embargo, no todos los números son datos numéricos, ya que pueden utilizarse como idenficadores y, en ese caso, serían strings. Dentro de este tipo, hay distintas categorías.
	- *Integers*: son números enteros.
	- Decimales: números con pocos decimales. Hay que tener cuidado con la separación de millares y decimales, puesto que la notación anglosajona utiliza la coma para los millares y la española, el punto.
	- *Floats*: números con muchos decimales. Son los más rápidos de procesar.
	- Fecha: suele tener el formato YYYY-MM-DD, donde Y hace referencia al año (cuatro cifras), M al mes (dos cifras) y D al día (dos cifras). En herramientas como Datawrapper, este formato puede variar para, por ejemplo, escribir el mes en letra, variar el número de letras, escribir el día de la semana...
	- Periodo: P indica que se trata de un periodo y va seguido de una n y D para días, M para meses, Y para años... Para periodos aproximados, se utilizan números negativos.
- Strings: son cadenas de caracteres, el lenguaje natural que acostumbramos.
- Booleanos: son parejas de valores mutuamente excluyentes. Por ejemplo, 0-1, Yes-No, True-False...
- Nulos.

## 12. Elige una URL de una noticia de un medio de comunicación y explícala tal como hicimos en clase.

https://www.eldiario.es/sociedad/comunidades-tendran-bajar-tasas-universitarias-700-euros-proximo-curso_1_8665460.html

En primer lugar, la URL empieza con un protocolo de transmisión. HTTP (*HyperText Transfer Protocol*) es un protocolo para acceder a la web y que tiene 4 funciones: *post, get, delete* y *put*. La s se relaciona con *get*, ya que significa que la visualización es segura.

A continuación, el dominio: (www.)eldiario.es. Es el nombre que sustituye a la IP. El navegador consulta esta en el DNS y nos permite acceder.

Finalmente, en una estructura de ficheros, el nombre del recurso. Dentro de sociedad, la noticia concreta. Vemos que termina en .html, por lo que podemos saber que es un archivo escrito con ese lenguaje.

## 25. Si quisieras ver la web theguardian.com, ¿cómo lo harías desde la línea de comandos?

Lynx es un navegador de la línea de comandos. Puede lanzarse el comando Lynx a secas para abrir el navegador, pero en este caso, conociendo la URL, utilizaríamos la siguiente línea:

**lynx theguardian.com**

## 26. ¿Cómo te descargarías la web theguardian.com desde la línea de comandos?

Esta pregunta se relaciona con la anterior. Al comando Lynx se le puede agregar la opción -source antes de la URL de la web.

**lynx -source theguardian.com**

Nos aparecerá el código fuente de la web. Podemos guardarlo añadiendo un argumento más con el destino (ruta).

**lynx -source theguardian.com > nombre-de-archivo**

## 28. ¿Cómo verías las variable de entorno de tu shell "PATH"? Escribe su valor también.

Utilizaría el comando echo e indicaría que PATH es una variable de entorno con $ de la siguiente manera:

**echo $PATH**

El valor que me devuelve es:

/usr/local/bin:/usr/bin:/cygdrive/c/Program Files (x86)/Common Files/Oracle/Java/javapath:/cygdrive/c/Windows/system32:/cygdrive/c/Windows:/cygdrive/c/Windows/System32/Wbem:/cygdrive/c/Windows/System32/WindowsPowerShell/v1.0:/cygdrive/c/Program Files (x86)/ATI Technologies/ATI.ACE/Core-Static:/cygdrive/c/Program Files/Acer/Remote Files:/cygdrive/c/Program Files/Pandoc::/cygdrive/c/Users/PAULA/

## 29. Cuál es el primer comando que deberías usar en la terminal. Explica tu respuesta.

Usaré pwd para que me diga dónde estoy trabajando. El siguiente sería whoami para saber cuál es mi usuario.

## 30. ¿Como te mueves por el árbol de directorios de tu sistema de ficheros? Razona tu respuesta.

Me muevo utilizando el comando cd (*change directory*) y, según convenga, rutas absolutas o relativas.

## 31. Si quisieras clonar un repositorio git, ¿qué pasos tendrías que dar? ¿Cómo comprobarías que ha funcionado?

En primer lugar, es fundamental instalar git y las librerías necesarias para que este funcione con el gestor de paquetes Apt-Cyg (para Windows). A continuación, copiaremos el código correspondiente de la opción *clone* en Github (URL terminada en .git). Volvemos a la CL y escribirmos *git clone código-copiado-que-acaba-en.git**. Se creará un directorio con el nombre del repositorio y todo su contenido.

Hay varias formas para comprobar que ha funcionado. Una de ellas consiste en utilizar el tabulador para autocompletar el nombre del directorio. Si funciona, es que se ha clonado correctamente. Por otro lado, podemos utilizar el comando ls. Deberíamos poder localizar un directorio con el nombre del repositorio clonado. Además, al entrar en él (cd), otro ls nos mostrará todo el contenido del repositorio git.

## 39. ¿Qué se puede hacer para ver el contenido de un archivo de texto?

Podemos utilizar distintos comandos, a continuación explicaremos dos posibilidades:

### Opción 1: editor de texto

Si tenemos un editor de texto para la línea de comandos, como nano, podemos utilizar el comando nano y el nombre del archivo de texto.

nano hola.txt

### Opción 2: comando cat

También podemos abrirlo con el comando cat y el nombre del archivo como argumento.

cat hola.txt

## 40. ¿Cómo creamos un directorio? ¿Y dos directorios? Razona tu respuesta

Utilizaremos el comando mkdir (*make a directory*) seguido del nombre del directorio que queramos crear. Si queremos crear dos, pondremos uno a continuación del otro, como dos argumentos separados, y se ejecutará la acción.

**mkdir Dir-1**

**mkdir Dir-1 Dir-2**

Otra opción, si no se quisieran crear a la vez, sería utilizar dos veces el comando mkdir o copiar el primero y renombrarlo.

*cp Dir-1 Dir-2**

Para comprobar que hemos creado bien el/los directorio/s, iremos al directorio *parent* y pediremos que se nos liste el contenido con el comando ls. Nos deberían aparecen los dos nuevos directorios según los hayamos nombrado.

## 42. ¿En qué se diferencian las rutas absolutas de las relativas? Pon ejemplos de ambas.

Las rutas absolutas explicitan toda la estructura de directorios, mientras que las relativas toman de referencia el directorio actual. Esto quiere decir que la absoluta comprende desde el directorio raíz hasta la ramificación donde se quiere ejecutar la acción. La relativa dependerá del lugar donde se esté ejecutando la acción.

Veamos un ejemplo. Si desease abrir con el comando cat un archivo de texto hola.txt ubicado en un directorio llamado "Dir-C", se presentan los siguientes casos 

- Estoy en Dir-C, por lo que solo tengo que indicar al comando cat el argumento hola.txt. Estoy utilizando una ruta relativa, puesto que no indico toda la estructura de la ruta.
- Supongamos que existen los Dir-A y Dir-B. Podría indicar al comando cat Dir-A/Dir-B/Dir-C/hola.txt. Estaría utilizando una ruta absoluta.

## 43. Qué son las entidades HTML y cómo se representan. Por un ejemplo

El lenguaje HTML tiene una serie de caracteres reservados especiales. Por tanto, si queremos utilizar esos caracteres con una función distinta a la habitual, debemos indicárselo. Para eso sirven las entidades, que constan de un & al principio y un ; al final.

Imaginemos que queremos escribir como cadena de caracteres que 4 < 3 con el sentido "cuatro es menor que tres". En este caso, "<" es utilizado en el código para estructurar el contenido (por ejemplo, <h1> indica primer nivel de título). Tenemos que utilizar una entidad de la siguiente manera:

4 &lt; 3

NOTA: lt corresponde a *lower than*.

## 44. Dado el significado que tienen las comillas para el comando =echo=, cómo harías para que devolviera una frase como: "Hola          Mundo"

En el comando echo, las comillas delimitan el mensaje que nos va a devolver. Por tanto, si escribirmos **echo "Hola Mundo"**, nos devolverá **Hola Mundo**.

Si queremos que nos devuelva también las comillas, debemos escaparlas con \ de la siguiente forma:

**echo "\"Hola Mundo\""**

## 45. Pon un ejemplo de uso de "wildcards"

Son caracteres "comodines". Un ejemplo es *.

* sirve para sustuir un número ilimitado de caracteres. Por ejemplo, si queremos copiar todos los archivos .txt independientemente de su nombre, utilizaremos de la siguiente forma el wildcard:

**cp *.txt**

## 46. ¿Qué función tiene la almohadilla en Markdown y en un programa de la shell? Razona tu respuesta.

En Markdown, indica que el texto es un título, como ocurre en este documento. Equivale al <h-> de HTML, donde - son los distintos niveles de título. Una almohadilla equivale a <h1>, dos almohadillas a <h2>... En cambio, en los programas de la shell utilizamos la almohadilla para comentarios. Esto significa que, al ejecutarlos, no se leerán las líneas que empiecen con #.

## 53. Pon un par de ejemplos de Google Dorks u "operadores de búsqueda"

Hay una serie de fórmulas útiles para las búsquedas en navegadores, que son estos operadores. Hay multitud, pero estos son algunos ejemplos:

- "-xxx": elimina un término de la búsqueda.
- OR: funciona como la conjunción "o".
- Filetype: para un formato determinado.
- Site: para buscar en un sitio web concreto

## 66. Qué es una faceta temporal

OpenRefine permite crear facetas de distintos tipos para facilitar la gestión de los datos. Funcionan como unos "filtros". La temporal o de línea de tiempo nos permite filtrar en función de una fecha, por lo que es indispensable tener, al menos, una variable con datos de este tipo. Para ello, indicaremos con la función *common transformations* que esos valores son fechas (o con value.toDate). Podremos seleccionar en la línea de tiempo que se genera qué fechas queremos visualizar. En clase nos resultó útil para localizar errores en el archivo .csv del proyecto TRESCA, puesto que aparecían datos del siglo pasado.

## 68. Como convertirías markdown a html desde pandoc

Tras instalar el parseador y comprobar que puedo lanzarlo desde la CL, utilizaría la siguiente línea:

**pandoc archivo.md -o nuevo-archivo**

Esto traduce la sintaxis de md a HTML. Sin embargo, no da como resultado un archivo .HTML necesariamente. En esta asignatura, hemos utilizado el resultado de esa combinación para concatenarlo (cat) con un *header* y un *footer* y tener un archivo .html listo para publicarse con el estilo configurado.

## 71. Para qué usas cd y cómo.

Es el comando para cambiar de directorio. Se lanza con el nombre de directorio de destino como argumento. Si en lugar de un nombre, se escribe .., asciende un nivel.

## 72. Para qué usas cp y cómo.

Es el comando para copiar. Necesita dos argumentos: archivo que queramos copiar y destino, que puede ser una ruta absoluta o relativa.

## 73. Para qué usas mv y cómo.

Es el comando para mover. También necesita dos argumentos: archivo de origen y de destino. Puede utilizarse, además, para cambiar el nombre a un archivo o directorio.

## 74. Para qué usas mkdir y cómo

Es el comando para crear directorios. Como argumento, debemos indicarle el nombre del directorio que queramos crear.

## 79. ¿Qué es una API. Pon algún ejemplo.

Una API (*access programming interface*) es el sistema de códigos que utiliza el navegador para comunicarse con una página web.

Un ejemplo de API universal es HTTP. Twitter, por ejemplo, tiene su propia API.

## 92. ¿Qué harías si al ejecutar un comando te salta el aviso "command not found"? 

Tendría que instalarlo. En Windows, es necesario el gestor de paquetes Apt-Cyg. La línea para instalarlo sería la siguiente:

**apt-cyg install comando**

## 84. ¿Qué relación tiene el formato CSV con Excel?

Excel es un programa de Microsoft para abrir y trabajar con hojas de cálculo y datos. El formato .CSV puede abrirse con Excel, pero no es exclusivo de este. Significa "valores separados por comas" y es uno de los más extendidos.

## 85. ¿Que significa TSV?

Significa "valores separados por tabulación". Es un formato de datos no estandarizado, pero sencillo y abierto. Se lee en forma de tabla (filas y columnas).

## 81. Qué similitudes y diferencias tiene Markdown con respecto a HTML.

Ambos son lenguajes informáticos fácilmente convertibles.

Markdown es una sintaxis plana sencilla, mucho más cercana al lenguaje natural. HTML es la más extendida para crear páginas web y es más compleja de escribir y entender. Además, Markdown no admite comentarios en su código, algo que sí podemos hacer en HTML. Evidentemente, las extensiones de los archivos son también distintas, igual que sus resaltados de sintaxis.

## 82. Explica la URL https://github.com/pontedatos/uc3m-periodismo-datos

Https es el protocolo para acceder a la página web, donde s significa que es una visualización segura. El dominio para acceder sin conocer la IP es Github.com y lo demás es la estructura de ficheros.

## 97. Expón dos mejoras que has tenido en tu proceso de trabajo con el ordenador. Si en vez de mejoras ha sido lo contrario, exponlo también.

La primera y fundamental es el descubrimiento de nuevas herramientas, como navegadores que respetan la privacidad como Duckduckgo.com.

El trabajo con la terminal me ha descubierto una alternativa a las aplicaciones gráficas y cambiado mi percepción del ordenador. Ya no lo siento como algo totalmente lejano a mí, sino que empiezo a comprender su funcionamiento. No obstante, queda mucho camino por recorrer.

Por otro lado, los atajos en el teclado han agilizado mucho mi trabajo en general.

El acercamiento a HTML también me ha ayudado a ver las páginas web de otra manera. Ahora no solo presto atención a su "cara pública", sino que también puedo mirar su código con Ctr+U y ver si está bien estructurada.

## 100. ¿Quién es Philip Meyer?

Philip Meyer es una figura fundamental en la historia del periodismo de datos. Detectó que las ciencias sociales utilizaban métodos que podrían ser útiles para el periodismo y aprovechó una beca para investigarlo. Una de sus obras fundamentales fue *Detroit Riots*, que analizó las revueltas raciales en esta ciudad. Así, desestimó la teoría Riff-Raff y se impuso la de las aspiraciones cortadas. Por tanto, su aportación es fundamental para el CAR (*Computer Assisted Repporting*), un antecedente del moderno periodismo de datos.

## 101. ¿Quién fue Florence Nightingale?

Fue una enfermera que elaboró un importante trabajo durante la Guerra de Crimea. Analizó los distintos tipos de heridos y enfermos que atendía. Es considerada, junto a otros personajes como John Snow (elaboró un mapa de Londres para localizar el origen de un brote de cólera), como un antecedente del periodismo de datos.
