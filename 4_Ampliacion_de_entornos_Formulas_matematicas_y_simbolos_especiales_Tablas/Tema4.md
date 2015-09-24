##  Tipos de documento: estilos

Al redactar un documento en LaTeX, encontramos cuatro estilos básicos que podemos darle a nuestro texto.

    Articulo (article) Es un documento que esta dividido en secciones. Generalmente se utiliza para informes cortos. Una gran cantidad de los documentos que se realizan en LaTeX utilizan este estilo.
    Reporte (report) Es un documento que además de secciones esta dividido en capítulos y puede contener apéndices. Por otro lado, el titulo se imprime en una hoja aparte de manera predeterminada. Se utiliza para documentos de mayor longitud, como por ejemplo una tesis. Este documento utiliza el estilo de reporte.
    Libro (book) Al igual que el reporte, esta dividido en capítulos, puede contener apéndices, etc. Los valores predeterminados se ajustan a los de un libro, por ejemplo, utiliza las hojas a doble cara. Ademas, los capítulos empiezan en paginas impares.
    Carta (letter) Se utiliza para escribir cartas comunes. Tiene marcas especiales para el destinatario, el remitente, el comienzo, el final, la firma, etc.

##Partes de un documento: más entornos


    Alineación (flushleft, flushright y center)

Los entornos flushleft y flushright generan párrafos alineados a la izquierda o a la derecha respectivamente.
El entorno center genera texto centrado.

Ejemplos:

    flushleft

\begin{flushleft}

Este texto está alineado a la izquierda. \LaTeX{} lo deja tal cual. No intenta justificarlo.

\end{flushleft}


Alineación a la izquierda

    flushright

\begin{flushright}

Este texto está alineado a la derecha.\

\LaTeX{} nos pone el texto de derecha a izquierda.

\end{flushright}


Alineación a la derecha

    center

\begin{center}

Estamos en el centro\del centro centrado.

\end{center}


Alineación central

    Citas (quote, quotation y verse)

        El entorno quote es útil para citas, frases importantes y ejemplos.

        \begin{quote}

        Poder disfrutar de los recuerdos de la vida es vivir dos veces.\Marco Valerio Marcial.\ Poeta satírico latino.

        \end{quote}

        Quote
        El entorno quotation es útil para citas largas que se extienden varios párrafos, porque sangra la primera línea de cada párrafo.

Francisco de Quevedo A Lope de Vega
\begin{flushleft}
\begin{quotation}
Las fuerzas, Peregrino celebrado,
afrentará del tiempo y del olvido
el libro que, por tuyo, ha merecido
ser del uno y del otro respetado.\

Con lazos de oro y yedra acompañado,
el laurel con tu frente está corrido
de ver que tus escritos han podido
hacer cortos los premios que te ha dado.\

La invidia su verdugo y su tormento
hace del nombre que cantando cobras,
y con tu gloria su martirio crece.\

Mas yo disculpo tal atrevimiento,
si con lo que ella muerde de tus obras
la boca, lengua y dientes enriquece.
\end{quotation}
\end{flushleft}

Quotation

        El entorno verse es útil para poemas donde son importantes los saltos de línea. Los renglones se separan mediante \ al final de línea y las estrofas mediante un renglón vacío.

Francisco de Quevedo A Lope de Vega

\begin{verse}

Las fuerzas, Peregrino celebrado,\

afrentará del tiempo y del olvido\

el libro que, por tuyo, ha merecido\

ser del uno y del otro respetado.\

Con lazos de oro y yedra acompañado,\

el laurel con tu frente está corrido\

de ver que tus escritos han podido\

hacer cortos los premios que te ha dado.\

La invidia su verdugo y su tormento\

hace del nombre que cantando cobras,\

y con tu gloria su martirio crece.\

Mas yo disculpo tal atrevimiento,\

si con lo que ella muerde de tus obras\

la boca, lengua y dientes enriquece.\

\end{verse}


Verse

      

    Resumen (abstract)

En publicaciones científicas es habitual empezar con un resumen que da al lector una idea rápida de lo que puede esperar.
LaTeX proporciona el entorno abstract con este propósito.
Normalmente abstract se usa para documentos compuestos con la clase article.

\begin{abstract}

Este es un curso, con un temario que me permitira crear, compilar e imprimir lo que yo quiera usando \LaTeX{}

\end{abstrac


abstract


    Citas literales (verbatim)

El texto encerrado entre \begin{verbatim} y \end{verbatim} se escribirá directamente, como escrito a máquina, con todos los saltos de línea y espacios, sin ejecutar ninguna orden LaTeX.

\begin{verbatim*}

Si usamos la versión con asterisco

del

entorno verbatim

este nos

destaca los espacios

del texto

\end{verbatim*}


Verbatin

## Tipos de letras en fórmulas matemáticas

Vamos a conocer los diferentes tipos de letras que usamos en el entorno matemático.

\mathnormal{Normal}
	

Normal

\mathrm{Rematada}
	Rematada

\mathit{Cursiva}
	Cursiva

\mathbf{Negrita}
	Negrita

\mathsf{sans-serif\:font}
	San serif
\mathtt{De\:maquina} 	Maquina

\mathcal{R\:Z\:Q}
	7

\mathbb{R\:Z\:Q}
	8

\mathfrak{R\:Z\:Q}
	9

Recordamos que \: es insertar un espacio pequeño en el entorno matemático.

## Símbolos encima de otros

Comandos del paquete amsmath:

Recordamos que tendremos que añadir al inicio de nuestro documento.

\usepackage{amsmath}

    \overset{algo encima de}{algo}

Vamos a colocar texto encima de unas flechas.

$\overset{OSL}{\Longleftarrow\Longrightarrow}$

Simbolo sobre simbolo

    \underset{algo debajo de}{algo}

Vamos a colocar texto debajo de unas flechas.

$\underset{OSL}{\Longleftarrow\Longrightarrow}$

Simbolo debajo de simbolo

    \xrightarrow[algo debajo]{algo encima}

Produce una flecha que apunta a la derecha y tiene algo encima y algo debajo, siendo éste último un argumento opcional. La longitud de la flecha se adapta automáticamente.

$\xrightarrow[OSL]{LSO}$

Algo debajo, algo encima

    \xleftarrow[algo debajo]{algo encima}

Produce una flecha que apunta a la izquierda y tiene algo encima y algo debajo, siendo éste último un argumento opcional. La longitud de la flecha se adapta automáticamente.

$\xleftarrow[LSO]{OSL}$

Algo debajo, algo encima

##Enfatizado

Las palabras se enfatizan componiéndolas con una cursiva. LaTeX nos proporciona la orden:

\emph{texto}

Ejemplo

\emph{Si queremos enfatizar un fragmento de texto ya enfatizado, entonces \LaTeX usa el modo \emph{normal} para enfatizar.}


Enfatizar


##El uso de las llaves

Si en vez de una linea deseamos abarcar expresiones con llaves horizontales, usaremos \underbrace y \overbrace.

    \underbrace

$ \underbrace {Hola Mundo} $ genera


\underbrace

    \overbrace

$ \overbrace {Hola Mundo} $ genera


\overbrace

## Paquete amsfonts

El paquete amsfonts proporciona un conjunto de modelos de letra (tipos de caracteres) que suelen ser utilizados para representar o identificar ciertos conjuntos.

Lo cargaríamos en el preámbulo del documento con la orden:

\usepackage{amsfonts}.

Ejemplos:

    Podríamos escribir el conjunto de los números reales de una forma usual con el comando $\mathbb{R}$, que produciría ℝ.

    También podríamos escribir letras góticas, usadas en Algebra, al dar nombre a los ideales con $\mathfrak{I}$ obtendríamos ℑ.

##Modo “display”

En un documento podemos encontrarnos fórmulas escritas en modo matemático dentro de texto (esto es, entre $ simple), $ \sum $, ∑, o bien podemos hallar la fórmula en modo matemático extendido (esto es, entre $ $), $ $ \sum $ $, ∑

El aspecto de la integral cambia según se esté en modo matemático dentro de texto o en modo matemático extendido; es evidente que el tamaño es distinto.
¿Cómo conseguiremos entonces una fórmula expandida dentro de un texto?

Para lograr que la expresión en el modo matemático dentro de texto sea igual a la del modo matemático extendido, tenemos la instrucción \displaystyle.

$\displaystyle \sum $, ∑ 

##Símbolos especiales

Vamos a conocer como usar símbolos especiales:

    Guiones.

Un guión puesto en la forma usual (-) puede resultar corto. Si queremos conseguir guiones más largos, en LaTeX podemos poner hasta tres guiones seguidos.

Para ello tenemos cuatro tipos diferentes de guión.

    Segmentación silábica o escritura de palabras compuestas (-)

Lo generamos escribiendo -
Si queremos que LaTeX corte una palabra al final de una línea en otro lugar que nos convenga, podemos usar el comando \- donde le indicamos a LaTeX que en ese punto de la palabra puede realizarse la división silábica.

    Intervalos numéricos (–)

Para hacer uso de intervalos numéricos usaremos --

    Alternativa a los paréntesis (—).

Si no queremos usar los parentesis, escribiremos ---

    Signo negativo en Matemáticas (−).

Y para las matemáticas, el tipico $-$

    Comillas

Para usar las comillas se puede utilizar la tecla del acento grave del teclado (`), dos veces, y para cerrar comillas usaremos el apóstrofo (’) del teclado, también dos veces

``casa'' genera “casa”

    Dejar espacios

Si necesitamos dejar un pequeño espacio, usaremos el teclado o también podemos hacerlo escribiendo la orden \, .
Si lo que necesitamos que el espacio sea mayor, aparte de poder escribir varias veces la orden anterior o bien usamos \hspace{Longitud}, donde {Longitud} sera donde pondremos la medida del espacio que queremos dejar.

    Símbolo del euro

Solo podemos usarlo en modo texto, no funciona en modo matemático. Para usaremos la instrucción \euro, siempre y cuando tengamos en el preámbulo del documento el paquete \usepackage{eurosym}; y el resultado sería: €. 

##Comandos propios

Para usar la fecha de hoy en cualquier idioma, lo obtenemos con el comando \today.

Si queremos crear un comando propio, el procedimiento es el siguiente:

\newcommand{\nombre}{definición}

\newcommand{\einstein}{E=mc^2}

siempre que escribamos \einstein nos escribirá:

E = mc2

Una pagina curiosa, para localizar símbolos en LaTeX.

http://detexify.kirelabs.org/classify.html

##Más tablas y cajas



La instrucción \multicolumn nos permite modificar dentro del entorno tabular la estructura inicial de columnas; con el podemos textos que ocupan mas de una columna.


La estructura del comando es la siguiente:


\multicolumn{Número}{Posición}{Texto}


donde:

    Número indica el número de columnas al que afecta el Texto.
    Posición indica la justificación del texto; debe contener una de las letras l, r o c y también puede contener caracteres como |.
    Texto es el contenido de la columna múltiple.

y


\usepackage{multirow}. Nos permite construir tablas en que el texto ocupa varias filas:


\multirow{nrow}{width}{contenido}


    nrow: numero de filas a agrupar
    width: Ancho de la columna

Para ver cómo funcionan estos comandos, habrá que crear antes una tabla:


\begin{center}

\begin{tabular}{|c|c|c|}
\hline \multicolumn{2}{|c|}{Celda 11 y 12} & Celda 13 \

\hline Celda 21 & \multirow{2}{*}{Celdas 22 y 32} & Celda 23\\cline{1-1}

\cline{3-3}Celda 31 & & Celda 33 \

\hline

\end{tabular}

\end{center}


y vemos como queda nuestra tabla:

Celda 11 y 21
	

Celda 31

Celda 21
	

Celda 22 y Celda 32
	

Celda 23

Celda 31
	

Celda 33

¿Si quisiéramos que el texto ocupe más de una línea dentro de la celda, o añadir varias líneas dentro de una sola celda?

Para esto tenemos tres maneras diferentes para hacerlo.

    Podemos introducir una tabla dentro de la misma tabla.
    Tenemos el entorno minipage, el cual crea una pequeña página en la casilla. La forma de usarlo es:

\begin{minipage}[Posición]{Anchura}
Objeto, palabras, listas, ...
\end{minipage}

Y cada parámetro de configuración es:

Posición: es optativo y con el elegimos la posición que queremos que ocupe el texto dentro de la caja vertical que nos abre el entorno.

Anchura este es un argumento obligatorio que nos indica la anchura de este entorno.

    Y por ultimo, tenemos \parbox. Como en el caso anterior, se construye una caja cuyo contenido se compone en modo párrafo.

Su sintaxis es de la forma \parbox[Posición]{Anchura}{Objeto}, donde Posición, Anchura, actúan de las misma manera que en el entorno minipage.

##Inserción de gráficos.



Lo primero que tenemos que hacer es añadir lo siguiente en el instrucción en el preámbulo (antes de \begin{document} de nuestro documento para poder trabajar con gráficos.

    Si compilamos el documento con pdflatex tenemos que usar figuras en formato .png o .jpg e incluir el siguiente paquete:\usepackage[pdftex]{graphicx}
    Si usamos LaTeX para compilar el documento tenemos que usar figuras en formato .eps (encapsulated postscript) o en formato .ps (postscript). Hay que usar el paquete:\usepackage[dvips]{graphicx}

Con esta linea ya podemos añadir nuestros gráficos, imágenes en nuestro documento, en la parte que corresponda.

La estructura típica seria esta:

\begin{figure}
\includegraphics{foto}
\caption{Foto}
\label{fig:XXXX}
\end{figure}

Vamos a analizar cada uno de ellos.

\begin{figure}[]

Parámetros que podemos usar:

Especifico
	Efecto

h
	Coloca la imagen aquí, es decir, aproximadamente en el mismo punto que se produce en el texto original (sin embargo, no exactamente en el lugar)
t
	Coloca la imagen en la parte superior de la página
b
	Coloca la imagen en la parte inferior de la página.
!
	Coloca en el lugar exacto que queremos.
H
	Lo coloca en el lugar preciso en el código LaTeX. Requiere el paquete flot, por ejemplo, \usepackage {float}; Es algo equivalente a h!

\includegraphics{foto}

Parámetros que podemos usar:

Especifico
	Efecto 	Ejemplo
width 	Definimos el ancho de nuestro gráfico
	
\includegraphics[width=60mm]{foto.png}
height 	Definimos el alto de nuestro gráfico 	
\includegraphics[heigt=60mm]{foto.png}
scale 	Definimos la escala de nuestro gráfico 	
\includegraphics[scale=.75]{foto.png}
angle 	Definimos la rotación de nuestro gráfico 	
\includegraphics[angle=45,width=39mm]{foto.png}

\caption{Foto}

Define un "pie de foto" para la imagen. LaTeX añadirá un número correlativo.

Si usamos \listoffigures, nos genera un índice de imágenes, en el punto que lo situemos.

\label{fig:XXXX}

Con \label y \ref, puede crear una referencia al flotante dentro del texto.

\end{figure}

Cerramos el entorno de imágenes.


Un ejemplo con casi todos los parámetros.

La figura \ref{blanco} es un ejemplo de blanco liso.
\begin{figure}[!hbp]
\includegraphics[angle=37,width=25mm]{blanco.png}
\caption{Imagen en blanco, rotada 37 grados.}
\label{blanco}
\end{figure}

##Bibliografía



Francisco J. Blancas Peral, María Cortada García, Eugenio M. Fedriani Martel, Alfredo García Hernández-Díaz, Irene García Selfa, Paula González Rodríguez,Sandra González Salas, Ma del Pilar Moreno Navarro, Raquel Rafael Arenas, Ma Isabel Sanz Domínguez, Ángel F. Tenorio Villalón, María M. Vega Quirós, Guía rápida para el nuevo usuario de LaTeX. http://www.eumed.net/cursecon/libreria/2004/emfm/latex.pdf
Walter Mora F., Alex Borbón A. Escuela de Matemática Instituto Tecnológico de Costa Rica.Edición de Textos Científicos; Composición, diseño Editorial, Gráficos,, Inkscape, Tikz y Presentaciones Beamer 
