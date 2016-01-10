##El estado mental correcto.

Como ya hemos apuntado, los editores para LaTeX no sen comporta igual que otros editores de texto de tipo WYSIWYG, sino que más bien funciona como un lenguaje de programación, en el que se crea un archivo fuente que hay que compilar.

LaTeX se mueve como pez en el agua en el entorno de las publicaciones científicas. La mayor parte de las primeras revistas del mundo exigen que los trabajos sean enviados en este formato. Esto es muy conveniente dada la separación natural que LaTeX impone entre información y presentación: El autor pone lo primero, y la revista se encargará de dar lo segundo.

Por ello, al aproximarse a LaTeX desde otros editores hay que tener en mente que su idea fundamental es que el autor se olvide completamente de cosas como la presentación o el formato, y pueda centrarse exclusivamente en el contenido. Al principio, esto puede resultar muy extraño al usuario novel ("Yo quiero tal tipo de letra con tal formato en tal posición"), pero es algo a lo que se acostumbra pronto y se aprende a valorar.

Por ejemplo: En cualquier editor WYSIWYG, el titulo de una sección no suele ser más que una línea de texto con una tipografía mayor y en negrita.

En LaTeX, sin embargo, el titulo de una sección no tiene una presentación definida, sino que es una estructura lógica que el compilador puede usar par automatizar tareas como la creación de referencias y notas a pie de página o la construcción de índices.

Como ya has visto en el capítulo anterior de este curso, cualquier editor de texto plano sirve para escribir LaTeX, pero existen herramientas como Texmaker que facilitan la tarea simplificando y automatizando parte del trabajo.

###Editor de LaTeX Texmaker  
http://www.xm1math.net/texmaker/  

##Estructura básica de un documento

Todo archivo de LaTeX comienza con una declaración del tipo de documento:
```
\documentclass{tipo}
```
Existen multitud de tipos, como "book" para libros, "letter" para cartas, "slides" para transparencias o "article" para artículos. Los tipos se pueden definir (si bien de manera bastante compleja) por medio de módulos externos. El tipo que se elija influirá en la posterior estructura y presentación del documento.
```
\documentclass, como otros comandos, permite además que se le apliquen algunos modificadores opcionales, como el tamaño base del texto o el tamaño del papel que se usará. Esto se hace colocándolos entre corchetes [] (antes de las llaves{}) y separados por comas del siguiente modo:

\documentclass[a4paper,11pt]{article}
```
Con esto estamos creando un artículo para una revista y definiendo el tamaño de letra a 11pt (los tamaños válidos son 10, 11 y 12 puntos) y el papel a formato a4

Una vez definido el tipo, ya podemos comenzar el documento en sí.

Todo el contenido del documento (párrafos, imágenes, tablas...) irá colocado entre los comandos \begin{document} y \end{document}, que son los que definen el principio y el final del documento,

De este modo, nuestro artículo inicial tomaría el siguiente aspecto:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

\end{document}
```

Que es un documento de LaTeX en principio perfectamente válido, pero en blanco.

El "Preámbulo" es todo aquello que hay antes de \begin{document} (pero siempre después de \documentclass), y es donde vamos a ubicar una serie de informaciones y comandos que describen o modifican el documento en conjunto.

Cuando, a lo largo del curso, hablemos de ubicar algo en la cabecera o "Preámbulo", nos referiremos a este sitio.

###Creando contenido

Por lo que hemos visto hasta el momento, podemos deducir que los comando en LaTeX comienzan siempre con una barra inclinada (\), que los argumentos que se aplican a esos comandos van entre llaves ({}) y que los modificadores se colocan entre corchetes ([])

Por ahora, vamos a dedicarnos al cuerpo del documento (el espacio entre \begin{document} y \end{document}) viendo tres elementos básicos que nunca deben faltar:
```
\title{Titulo del documento}

\author{Autor}

\date{Fecha}
```

Probablemente no haga falta, pero diremos que son los elementos donde se definen, respectivamente, el Título, Autor y Fecha de creación del documento.

Nuestro artículo va tomando forma, y podemos ir ubicando los datos de un modo parecido a este:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

\title{Articulo de prueba}

\author{Autor}

\date{Fecha}

\end{document}
```

Si compilas el ejemplo anterior verás que, pese a que le hemos colocado un título (y un autor, etc), este no aparece por ningún lado.

Esto es porque hemos definido los datos, pero no los estamos presentando. Probemos con el siguiente caso:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

\title{Articulo de prueba}

\author{Autor}

\date{Fecha}

\maketitle

\end{document}
```

Se diferencia del anterior en la instrucción \maketitle, encargada de construir un título para nuestro documento.

Aquí empezamos a ver la potencia de LaTeX. El mismo programa ha creado un título completo, con fecha y autor y lo ha ubicado en la página. Al ser un artículo, lo ha centrado y colocado en la parte superior, pero esto no tiene porqué ser así siempre, si no que depende del tipo de documento (De hecho, el formato "letter" ni siquiera soporta /maketitle).

Nota interesante: Si usamos \maketitle sin haber especificado una fecha, LaTeX usará por defecto la fecha actual.

Prueba a cambiar el tipo de documento por "book" y verás como el resultado es distinto.

Otra cosa que habrás notado es que la compilación da errores si usas acentos, Ñs o ese tipo de caracteres. Un poco de paciencia: Más adelante veremos cómo arreglar eso.

###Escribiendo

Vamos a poner un poco de texto, para ir viendo algunas otras peculiaridades de LaTeX:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

\title{Articulo de prueba}

\author{Autor}

\date{Fecha}

\maketitle

Algo de contenido que no se muestra como era de esperar

Sin duda pasa algo muy muy raro

% Y esto es tremendamente misterioso

\end{document}
```

De nuevo nos topamos con la idiosincrasia de LaTeX: Todos esos espacios que hemos colocado en las separaciones entre palabra han colapsado a un solo hueco. Recordemos que la filosofía detrás de LaTeX es dedicarnos al contenido y dejarle la presentación y el formato al compilador.

Si se quiere forzar un espacio, este debe de ser precedido de una barra de este modo "\ ". Para acumular varios espacios se debería poner algo así: "\ \ \ \ \".

Los retornos de carro son interpretados también como espacios en blanco, para influir sobre ello hay un comando que puede resultarnos útil y es "\", que introduce un retorno de carro.

Para separar párrafos LaTeX usa una línea en blanco (o, lo que es lo mismo, dos retornos de carro seguidos).

Otra cosa que descubrimos es que el signo % se usa para marcar los comentarios. Todo lo que le siga será ignorado por el compilador

Latex introducirá automáticamente retornos de carro donde sea necesario para ajustar la línea al ancho de página (más adelante veremos que se puede ajustar este comportamiento a las reglas de cada idioma), si quiere forzarse a que respte un espacio y no separe dos palabras en líneas distintas, se debe usar la tilde (~) entre ellas.

### Capítulos y secciones

El elemento fundamental para separar y organizar un texto es el párrafo (que, como vimos, se crea separándolo del resto del texto por una línea en blanco).

Pero como no sólo de párrafos se organiza un texto, existen una serie de comandos para indicar títulos de diferentes niveles de importancia y separar secciones, capítulos etc.

Por orden de importancia, son:
```
\part{Texto del Título de este nivel}
\chapter{Texto del Título de este nivel}
\section{Texto del Título de este nivel}
\subsection{Texto del Título de este nivel}
\subsubsection{Texto del Título de este nivel}
```
Algunos tipos de documento no usan alguno de estos niveles. Por ejemplo, el tipo "article" no usa el nivel chapter.

Para empezar a ver esto, hagamos un ejemplo:
```
\documentclass[a4paper,11pt]{article}

\usepackage[utf8]{inputenc}

\usepackage[spanish]{babel}

\begin{document}

\part{Apartado Principal}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Una sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\subsection{Una subsección dentro de la sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Otra sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Y otra sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\end{document}

```
Como puedes ver al compilar este ejemplo, LaTeX se ha ocupado de colocar la numeración ante los títulos. Esto es mucho más cómodo de lo que parece a primera vista porque, si posteriormente hacemos modificaciones y agregamos secciones, LaTeX recalculará toda la numeración sin problemas (haz la prueba agregando alguna).

El comportamiento exacto de esta herramienta se ve afectado por el uso del paquete babel. Prueba a compilar este mismo ejemplo pero sin usar la línea \usepackage[spanish]{babel} (borrándola o comentándola con %)

Por supuesto, como hemos visto varias veces, el tipo de documento que estamos usando (en este caso article) también afecta a la presentación.

Pero esto no es todo. Otra utilidad de esta forma de estructurar es que LaTeX puede crar automáticamente el índice de contenidos de nuestro documento.

Para ello tenemos el comando \tableofcontents que se usa, simplemente, insertándolo en el lugar donde queramos que aparezca nuestro índice:
```
\documentclass[a4paper,11pt]{article}

\usepackage[utf8]{inputenc}

\usepackage[spanish]{babel}

\begin{document}

\tableofcontents

\part{Apartado Principal}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Una sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\subsection{Una subescción dentro de la sección} Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Otra sección} Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\section{Y otra sección}

Texto de relleno bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla bla

\end{document}
```

Nota Importante: A menudo no se muestra ningún cambio en la primera compilación, porque LaTeX debe reconstruir el índice del documento cada vez. Simplemente con volver a compilar de nuevo se resuelve esto.

De nuevo, este índice cambiará de modo automático si cambiamos la estructura del documento.

Prueba a compilar este mismo ejemplo varias veces con y sin \usepackage[spanish]{babel} y con distintos tipos de documento, verás que cambia considerablemente el modo de mostrar el índice.

##Entornos

Anteriormente vimos que el cuerpo de un documento LaTeX está contenido entre los comandos \begin{document} y \end{document}.

En realidad, lo que hacen \begin y \end es crear lo que se conoce como un "entorno".

Un entorno es una parte de un documento en la que se definen una serie de propiedades o que se comporta o muestra de un modo determinado.

Por ejemplo, para las citas se suele usar el entorno quote, y para alinear el texto a la derecha se usa flushright, del siguiente modo:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

\title{Articulo de prueba}

\author{Autor}

\date{Fecha}

\maketitle

Esto es un texto normal en el propio body, seguido de algo de relleno sin contenido intelectual real (salvo el meramente textual) para hacer un poco de bulto y que no se vea tan soso ni tan cortito.

\begin{quote}

Y esto es un texto en un entorno de quote, seguido de algo de relleno sin contenido intelectual real (salvo el meramente textual) para hacer un poco de bulto y que no se vea tan soso ni tan cortito.

\end{quote}

\begin{flushright}

Y esto otro es un texto en un entorno flushleft, seguido de algo de relleno sin contenido intelectual real (salvo el meramente textual) para hacer un poco de bulto y que no se vea tan soso ni tan cortito.

\end{flushright}

\end{document}
```

Según el tipo de documento, quote puede cambiar el tipo de letra, la indentación, etc.

De mismo modo que flushright obliga a alinear a la derecha, existe otro entorno flushleft para hacerlo a la izquierda. Igualmente, un poco más adelante en este curso veremos cómo las ecuaciones se representan con los entornos displaymath y equation, o las tablas se crean mediante los entornos table y tabular.

Existen multitud de entornos (más adelante en este curso veremos algunos más) y, además, LaTeX provee de un modo para que puedan crearse nuevos en un documento cada vez que se necesiten.

## Fórmulas matemáticas

Probablemente la razón por la que LaTeX es famoso es su increíble capacidad para representar ecuaciones y fórmulas matemáticas. Supera en este aspecto a la totalidad de sus competidores y, los que se le acercan en potencia lo hacen porque usan intérpretes basados en LaTeX.

Los comandos, símbolos y lenguaje necesarios para ello son demasiados y demasiado complejos, por lo que se escapan de las posibilidades de este curso, pero aquí veremos una pequeña introducción a su uso.

La forma más simple de escribir una fórmula matemática es "en línea", colocando la fórmula en cuestión entre los símbolos $ y $, de este modo:
```
\documentclass[a4paper,11pt]{article}

\begin{document}

La ecuacion mas famosa de la historia de la fisica probaablemente sea la de $E=m*c^2$, de donde se deduce que $c=\sqrt{E/m}$.

\end{document}
```

Nota que LaTeX ha interpretado La fórmula, representándola correctamente.

También pueden escribirse mediante los entornos displaymath, que coloca la ecuación en un párrafo aparte y centrada, o equation, que le asigna un número de orden y por tanto es más adecuado para identificar una ecuación y poder referenciarla luego:

```
\documentclass[a4paper,11pt]{article}

\begin{document}

\begin{displaymath}

\sum_{0\le i\le m\\0<j<n}P(i, j)

\end{displaymath}
```
Hay muchos simbolos y toda un compleja sintaxis para escribir matematicas en LaTeX
```
\begin{equation}

\label{miecuacion}

f(x)=\sqrt{g’(x)dx}+Z

\end{equation}

La ecuacion que se puede ver en \ref{miecuacion} es completamente inventada y no tiene sentido fisico

\end{document}
```

Nota el uso de \label para crear una referencia que luego puede usarse en \ref, de modo que coloque automáticamente el número correspondiente a la ecuación.

Existe una ingente cantidad de comandos y símbolos para escribir fórmulas matemáticas en LaTeX y es, de hecho, prácticamente imposible conocerlos todos. Cualquier programa de edición de LaTeX (como, por ejemplo, Texmaker) dispone de atajos y ayudas para esto.

Más adelante en este mismo curso se verán algunos aspectos más avanzados de las fórmulas matemáticas. 
