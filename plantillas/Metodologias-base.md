# Memoria final del curso (2021)

## Trabajo con la terminal

Para crear esta página web, ha sido necesario un trabajo previo en la terminal para ordenar la estructura de directorios o carpetas.

En primer lugar, dentro del repositorio propio clonado durante el curso, he creado un nuevo directorio llamado **docs** para alojar los archivos .html del contenido de la web. Por tanto, dos comandos indispensables han sido mkdir para crear directorios y cd para pasar de unos a otros. Dentro de este repositorio he creado también una carpeta llamada **img** para guardar las imágenes y poder referirme a ellas.

### Otras instalaciones necesarias

Utilizando el comando apt-cyg install:

- **Python3** para saber el puerto donde se sirve la web (python3 -m http.server). Se comprueba que se lanza en el 8000 (127.0.0.1:8000)
- **Zip** para crear el archivo comprimido
- **Unzip** para descomprimir archivos

## Pandoc

Pandoc es un conversor de documentos que utilizaré para convertir la sintaxis markdown en html.

Una vez descargado desde [pandoc.org](https://pandoc.org/), cierro la terminal y vuelvo a abrirla. Hecho esto, funciona como un comando. No ha sido necesario añadir la variable al PATH.

Para convertir los archivos .md a html, escribo en la terminal:

pandoc nombre-archivo.md -o nombre-archivo

De esta forma, creo una serie de "bases" traducidas a html que utilizaré más adelante. También he seguido este proceso con el contenido del [index.html](index.html) y esta misma memoria. Tras crear con nano un archivo .md, he utilizado pandoc para pasar a html. Con el comando mv, estas bases traducidas se han movido y agrupado en la carpeta plantillas.

## Bootstrap

Desde esta biblioteca, se descargan las plantillas de ejemplo que ofrece. Se descarga un archivo comprimido zip con el comando curl y el enlace y con el comando unzip extraemos una carpeta que contiene el tema que vamos a usar: sticky footer navbar.

En docs, creo una carpeta llamada css con las hojas de estilo en cascada. Más adelante, será necesario cambiar la ruta en el html para que se aplique el estilo.

También es necesario crear una carpeta (js) para un archivo JavaScript y, de la misma manera, habrá que cambiar la ruta en el html.

## Trabajo con html

En el archivo index.html he realizado algunos cambios básicos para personalizar la web, tales como cambiar el nombre o los enlaces del menú superior. Todos los pasos concretos están comentados en el código, pero también los enumero a continuación:

- Cambio el lenguaje a español
- Cambio las rutas anteriormente mencionadas
- Cambio del nombre de la página
- Cambio el nombre del menú, añado otros apartados y cambio los enlaces
- Cambio la autoría
- Cambio el contenido del pie o *footer*
- Borro a partir del nivel 1 (<h1>) para sustituirlo por el contenido que he redactado para el index.

Hecho esto, duplico (cp) el archivo dos veces hasta tener tres index.html. Hecho esto, en uno de ellos borro todo, salvo la cabecera. Con el otro hago lo mismo, pero conservo el pie. Estos dos nuevos archivos, con sus nuevos nombres, servirán para combinar con las bases creadas con pandoc. Con el comando cat, concateno los tres archivos hasta tener un html para cada práctica de la siguiente manera:

cat Cabecera.html Archivo-base Pie.html > Práctica.html

El archivo resultante debe coincidir con la ruta que he puesto en el menú superior.

Una vez hecho esto, compruebo los errores. La ruta de las imágenes ha cambiado, por lo que debo corregirla para indicar que están en la nueva carpeta img dentro de docs. Además, ahora que ya no trabajo en markdown, puedo utilizar el código que datawrapper ofrece para incrustar las imágenes en html y conservar los elementos interactivos. Por ese motivo, se ha añadido en la cuarta práctica sobre las actuaciones de los bomberos un apartado para estos códigos.

## Página en Github

Para lanzar la página desde Github, voy al apartado de configuración o *settings* del repositorio. A continuación, pulso en *pages* e indico que se construya desde la carpeta docs y desde *root* (la rama *main* se mantiene). Se publica la página web: paula255.github.io/periodismo-datos/.

## Crear un archivo comprimido .zip

Finalmente, una vez se ha terminado todo el trabajo, utilizo el comando zip para crear un archivo comprimido de todo el repositorio del curso. Lo guardo en la carpeta src de docs, junto a los proyectos de OpenRefine y los csv resultantes de cada práctica de elaboración de infografía.
