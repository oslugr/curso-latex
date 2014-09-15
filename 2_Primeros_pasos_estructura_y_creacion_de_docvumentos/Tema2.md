##El estado mental correcto.

Como ya hemos apuntado, los editores para LaTeX no sen comporta igual que otros editores de texto de tipo WYSIWYG, sino que más bien funciona como un lenguaje de programación, en el que se crea un archivo fuente que hay que compilar.

LaTeX se mueve como pez en el agua en el entorno de las publicaciones científicas. La mayor parte de las primeras revistas del mundo exigen que los trabajos sean enviados en este formato. Esto es muy conveniente dada la separación natural que LaTeX impone entre información y presentación: El autor pone lo primero, y la revista se encargará de dar lo segundo.

Por ello, al aproximarse a LaTeX desde otros editores hay que tener en mente que su idea fundamental es que el autor se olvide completamente de cosas como la presentación o el formato, y pueda centrarse exclusivamente en el contenido. Al principio, esto puede resultar muy extraño al usuario novel ("Yo quiero tal tipo de letra con tal formato en tal posición"), pero es algo a lo que se acostumbra pronto y se aprende a valorar.

Por ejemplo: En cualquier editor WYSIWYG, el titulo de una sección no suele ser más que una línea de texto con una tipografía mayor y en negrita.

En LaTeX, sin embargo, el titulo de una sección no tiene una presentación definida, sino que es una estructura lógica que el compilador puede usar par automatizar tareas como la creación de referencias y notas a pie de página o la construcción de índices.

Como ya has visto en el capítulo anterior de este curso, cualquier editor de texto plano sirve para escribir LaTeX, pero existen herramientas como Texmaker que facilitan la tarea simplificando y automatizando parte del trabajo.

##Editor de LaTeX Texmaker

##Estructura básica de un documento

Todo archivo de LaTeX comienza con una declaración del tipo de documento:

\documentclass{tipo}

Existen multitud de tipos, como "book" para libros, "letter" para cartas, "slides" para transparencias o "article" para artículos. Los tipos se pueden definir (si bien de manera bastante compleja) por medio de módulos externos. El tipo que se elija influirá en la posterior estructura y presentación del documento.

\documentclass, como otros comandos, permite además que se le apliquen algunos modificadores opcionales, como el tamaño base del texto o el tamaño del papel que se usará. Esto se hace colocándolos entre corchetes [] (antes de las llaves{}) y separados por comas del siguiente modo:

\documentclass[a4paper,11pt]{article}

Con esto estamos creando un artículo para una revista y definiendo el tamaño de letra a 11pt (los tamaños válidos son 10, 11 y 12 puntos) y el papel a formato a4

Una vez definido el tipo, ya podemos comenzar el documento en sí.

Todo el contenido del documento (párrafos, imágenes, tablas...) irá colocado entre los comandos \begin{document} y \end{document}, que son los que definen el principio y el final del documento,

De este modo, nuestro artículo inicial tomaría el siguiente aspecto:

\documentclass[a4paper,11pt]{article}

\begin{document}

\end{document}


Que es un documento de LaTeX en principio perfectamente válido, pero en blanco.

El "Preámbulo" es todo aquello que hay antes de \begin{document} (pero siempre después de \documentclass), y es donde vamos a ubicar una serie de informaciones y comandos que describen o modifican el documento en conjunto.

Cuando, a lo largo del curso, hablemos de ubicar algo en la cabecera o "Preámbulo", nos referiremos a este sitio.

##Creando contenido

