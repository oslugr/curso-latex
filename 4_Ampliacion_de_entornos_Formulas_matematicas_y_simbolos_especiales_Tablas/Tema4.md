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


