##Acentos y UTF-8

Por defecto, LaTeX sólo usa ASCII y, si se quieren poner acentos, debe hacerse del siguiente modo:

'a 'e 'i 'o 'u


del mismo modo, por ejemplo, la letra ñ se pondría del siguiente modo:

\~n


La fórmula es similar para otros caracteres fuera del ASCII, como se puede ver en los siguientes ejemplos:

\"o \^u \AE \=e \.o \c c


Para poder usar tildes, Ñs y otros caracteres no-ASCII directamente, hay que cargar el juego de caracteres correspondiente con inputenc. Es recomendable el uso de UTF-8, que se cargaría de este modo (en la cabecera de nuestro documento, claro).

\usepackage[utf8]{inputenc}


Otro paquete interesante a ese respecto es babel, que permitirá a LaTeX el manejo de las peculiaridades del español, como las reglas de separación de sílabas a final de línea o el manejo de signos de puntuación.

\usepackage[spanish]{babel}


De este modo, muestro documento ya empieza a parecerse a esto:

\documentclass[a4paper,11pt]{article} \usepackage[spanish]{babel} 

\usepackage[utf8]{inputenc}

\begin{document}

Por fin ya podemos usar eñes, acentos, diéresis y esa tonterías.

\end{document}


Existen otros comandos para agregar caracteres especiales como, por ejemplo:

\ldots


Esto colocará tres puntos suspensivos.

## Partes de un documento: más entornos


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

##
