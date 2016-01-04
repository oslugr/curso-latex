##Procesadores de textos y su historia.

LaTeX no es exactamente un procesador de textos, sino un sistema de preparación de textos enfocado principalmente al área científica.
Los primeros sistemas usados para crear textos fueron los editores; en éstos se trabaja simplemente con caracteres, sin más formato que el que se pueda crear a base de espacios y separación entre los mismos; los [procesadores de texto](http://es.wikipedia.org/wiki/Procesador_de_texto) añaden la posibilidad de formatear el texto de múltiples maneras añadiendo resaltes a las letras, usando diferentes tipos de las mismas y organizando el texto automáticamente en líneas, columnas y otras disposiciones.

El primer procesador de texto del tipo que conocemos hoy en día (tras otros usados en microordenadores y sistemas dedicados) fue el [WordStar](http://es.wikipedia.org/wiki/Wordstar), creado durante la primera mitad de los 80. Sin embargo, no tenía la característica [WYSIWYG](http://es.wikipedia.org/wiki/WYSIWYG) que hoy nos resulta habitual; en el ambiente científico, esta característica no surgió hasta finales de los 80 en el procesador de textos [ChiWriter](http://en.wikipedia.org/wiki/ChiWriter), con el que se han escrito más de una tesis y que tenía la particularidad avanzada de poder trabajar con ecuaciones y [fórmulas matemáticas](http://ecampus.ugr.es/moodle/mod/url/view.php?id=1543).

LaTeX, sin embargo, comenzó en 1976 en la forma de TeX, un sistema para poder imprimir fórmulas y expresiones matemáticas. Era un sistema de macros que se añadían al texto, pero en algunos casos era excesivamente complicado y no fue hasta que en 1984 Leslie Lamport creó una serie de extensiones, que se denominaron LaTeX, cuando se empezó a popularizar.

LaTeX era mucho más fácil de usar que TeX, y se concentraba en la estructura del documento, más que en la apariencia. La forma de usarla era la misma: editando un texto al que se le añadían una serie de órdenes; posteriormente el texto se compilaba y se convertía en un formato imprimible (que en 1984 eran muy diferentes a los actuales) o se enviaba directamente a la impresora.

Desde entonces se han hecho diferentes versiones, pero la más popular hoy en día es la 2, aunque se lleva trabajando [en la 3](http://latex-project.org/latex3.html) desde hace bastantes años. Dado que LaTeX es software libre, generalmente viene en una serie de distribuciones que incluyen el LaTeX (simplemente un sistema de proceso de textos) junto con otros programas necesarios para hacer el ciclo completo, incluyendo la inclusión de [bibliografía](http://ecampus.ugr.es/moodle/mod/page/view.php?id=1574) y su conversión a diferentes formatos.

##Consiguiendo e instalando LaTeX

###Descargar LaTeX

En esta página se ofrecen varios enlaces a versiones de LaTeX para todas las distribuciones. Recordad que LaTeX no es un programa como el LibreOffice Writer, que se lanza e incluye todo lo necesario; una instalación descargará una serie de programas exclusivamente para generar a partir del texto el fichero imprimible; no se puede lanzar un programa desde el menú y empezar a editar en él.

Algunos editores de textos permiten trabajar fácilmente desde ellos con LaTeX, con modos que te ahorran teclear cosas y funciones que permiten compilar directamente desde él. Personalmente prefiero el Emacs, disponible para todos los sistemas operativos, con el modo AuCTex. Para instalar todo junto, en mi caso y como usuario de Linux, simplemente se ejecuta la siguiente orden en un terminal:

sudo apt-get install auctex texlive emacs.

Emacs con este modo tendrá la apariencia que se muestra a continuación

![Emacs](/img/1.png)

En otros sistemas operativos se pueden usar los editores de programador que más se hayan usado, buscando siempre uno que incluya detección de sintaxis y alguna que otra función para facilitar la edición.

Como se puede ver, hay tres botones a la izquierda que sirven para compilar el fichero; las tres penúltimas opciones del menú también están relacionadas con LaTeX.

###Resumiendo

Para usar LaTeX hacen falta dos cosas: una distribución que incluya todos los programas y un editor de textos; si este editor de textos es de programador facilitará la labor de edición de textos.
Para comenzar y al menos tener prácticamente toda la funcionalidad de LaTeX se puede usar LyX, un entorno WYSIWYG que usa internamente LaTeX para representar la información y puede generar el mismo.

##Instalando LaTeX en Windows

El problema principal de Windows es que con LaTeX hay que proveer todo lo necesario para trabajar con él, porque no suele incluir las utilidades habituales en estos casos. Afortunadamente, tratándose de software libre, hay una distribución llamada ProTeXt que tiene todo lo necesario. Sin embargo, hay que descargarse más de un giga para instalarlo; conviene que tengáis más de 3 gigas libres para la instalación completa.
Afortunadamente, este tutorial procedente de Guatemala nos ayuda a instalarlo: esta es la primera parte, la segunda y la tercera. En todo caso, la instalación se divide en tres partes (después de la hora o así que tarda en descargarse)

Descomprimir el paquete: se descomprime en un directorio de nuestra elección (tabién tarda un buen rato)
Buscar el directorio y ejecutar "setup.exe".
Te da la opción de instalar MiKTeX (que sería, en sí, el programa que incluye LaTeX) y un editor, ConTeXt, muy bien adaptado para trabajar con LaTeX. Es conveniente que instales los dos; el primero tardará también un buen rato (media hora), y el segundo sólo un minuto.

Como has visto, todo el proceso puede durar una buena parte de una mañana o una tarde. Aprovecha para leerte el resto del material del curso, o para reflexionar sobre las ventajas de usar sistemas operativos libres.

##Trabajando con LaTeX

###El equivalente del Hola Mundo en LaTeX
LaTeX es un sistema de preparación de documentos y como tal funciona de forma diferente a lo que estamos acostumbrados. Mientras que en los procesadores de textos se trabaja sobre el documento en el formato aproximado en el que saldrá por impresora de forma WYSIWYG, en LaTeX están separadas las fases de edición, visualización y generación del documento en su formato final.
Para comenzar, por tanto, será necesario usar un editor y teclear o copiar/pegar en él un texto similar al siguiente, obtenido del Diablo Cojuelo publicado en el proyecto Gutenberg

```latex
\documentclass{article}
\usepackage[spanish]{babel}
\usepackage[utf8]{inputenc}
\begin{document} Daban en Madrid, por los fines de julio,
las once de la noche en punto, hora menguada para las calles, y,
por faltar la luna, juridición y término redondo de todo requiebro
lechuzo y patarata de la muerte.
\end{document}
```

Editado desde, por ejemplo, Emacs, tendría esta apariencia
![Emacs editando LaTeX](/img/2.png)

Siempre que se use, como se ha indicado, la librería AuCTeX u otra similar; en este caso se trata, simplemente, del denominado modo LaTeX.
Desde este entorno, la creación del documento se hace en varios pasos y de dos formas diferentes, tras guardar el fichero poniéndole la extensión .tex.
Generación de fichero independiente del dispositivo
La configuración por defecto consiste en generar un fichero independiente del dispositivo; es un fichero con la extensión .dvi que, posteriormente, se puede imprimir o convertir a cualquier otro formato de fichero. En este caso, habrá que llevar a cabo dos pasos:

1    Pulsar el botón con el leoncito, que compilará el fichero. Si no hay ningún error, dará un mensaje en la barra de estado que indicará que se ha podido compilar:"LaTeX: successfully formatted {1} page"; en caso contrario, aparecerá un símbolo que indicará que hay errores.
2   Pulsando sobre las gafas que indican "dvi" se abrirá un programa de visualización del fichero independiente del dispositivo que presentará la apariencia más o menos final del mismo. Desde este programa, aparte de poder hacerse zoom, se pueden también exportar o imprimir, pero generalmente se usa como una "previsualización". La apariencia de este programa es la que se muestra a continuación.

![Emacs](/img/3.png)

Estos dos pasos se pueden llevar a cabo también desde la línea de órdenes; es la única forma en la que estarán disponibles en todos los entornos de trabajo. Tras guardar el fichero y situarnos en el directorio donde lo hemos guardado, escribimos

latex prueba.tex

Éste fichero (igual que el comando anterior, sólo que de forma invisible) nos habrá generado uno denominado prueba.dvi. Para visualizarlo, se escribe

xdvi prueba.dvi

o algún otro programa en otro sistema operativo.

En cualquiera de los dos casos, para generar un PDF a partir del DVI hay que recurrir a la línea de órdenes:

dvipdf prueba.dvi


Generación directa de un PDF
En el caso de tener un fichero que no incluya imágenes como este, también existe la opción de generar directamente un PDF. Se puede hacer desde Emacs: se marca Command-> Texing Options -> Generate Pdf (hay una combinación de teclas para esto, como lo hay para todo en Emacs). Como se ve, los iconos de LaTeX y las gafitas de visualización tienen ahora un PDF en rojo:

![PDF](/img/4.png)

Pulsando sobre el icono de LaTeX se compilará y se generará directamente un PDF; ahora lanzando el visualizador se abrirá el visualizador de PDFs, posiblemente Evince, con el resultado.
Como hemos explicado anteriormente, también se puede obtener el mismo resultado desde la línea de órdenes, ejecutando

pdflatex prueba.tex

y, posteriormente, para visualizarlo,

evince prueba.pdf

Explicación del texto
En LaTeX, las órdenes comienzan con \ y consisten generalmente en el nombre de la orden y una serie de argumentos. El argumento va entre llaves y el modificador al mismo entre corchetes y antes de las llaves.
Las tres primeras líneas son órdenes: la primera establece el tipo de documento, y es imprescindible porque modifica el resultado de las otras órdenes. Vamos a usar el tipo más simple, artículo, aunque hay muchos otros tipos; los congresos y revistas, generalmente, tienen el suyo propio.
Las órdenes siguientes:

```latex
\usepackage[spanish]{babel}

\usepackage[utf8]{inputenc}
```

son imprescindibles para trabajar en español. En cualquier caso, se trata de paquetes que añaden funcionalidad al documento; el primero es el paquete Babel para trabajar con diferentes idiomas, y le damos la opción de que se trate de español. Esta orden es tenida en cuenta a la hora de dividir las palabras y usar convenciones como la forma de expresar las fechas. El segundo se refiere al alfabeto que vamos a usar en el fichero; LaTeX usa sólo los caracteres "normales" que no incluyen a las letras castellanas: ñ y ú, por ejemplo; con esta orden le decimos que la codificación del fichero de entrada es utf8, el formato de almacenamiento del mismo más usado por los editores hoy en día. Si tenéis algún problema con esto al compilar; si suprimen los caracteres comentados, probad a cambiar utf8 a latin1 (la codificación que incluye a todos los caracteres del alfabeto español).
Finalmente, tras estas órdenes que se suelen poner al principio del documento pero que no generan ningún tipo de contenido viene un entorno en LaTeX. Los entornos están entre begin y end, y se representan de una forma determinada; en este caso se representarán con el formato que tenga asignado el tipo de documento al principio. Los entornos se cierran en orden contrario al que se abren si están anidados. En este caso, \end{document} será siempre la última orden del documento.
Todo esto se ampliará más en el tema siguiente; el objetivo de esta sección es simplemente que se comprenda qué es lo que se ha hecho y la estructura muy mínima para crear un documento en castellano.

Trabajando con TexMakerX en Windows
TexMaker es un editor libre que funciona en todos los sistemas operativos, pero que forma parte de la distribución ProTeXt que previamente hemos explicado como instalar en Windows. Es un entorno de edición, pero desde el que se pueden llevar a cabo todas las tareas. En el tema siguiente se explica cómo se trabaja con él en más profundidad, pero para que comencéis a usarlos hemos realizado este video.


