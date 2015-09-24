##Creación de bases de datos para BibTeX


La forma mas cómoda de trabajar con bibliografías, es crearnos nuestra base de datos, con la ventaja de que así evitamos tener que crear una para cada vez que la necesitemos.

Si usamos Linux es interesante instalar algunos añadidos mas a LaTeX: sudo apt-get install texlive-bibtex-extra

Con este método las referencias son escritas una sola vez y almacenadas en la base de datos que tenemos.

Pero como toda base de datos que se precie, tenemos que usar un formato que esta ya especificado, vamos a conocerlo.
@BOOK{osl:03a, 	
AUTHOR 	="Oficina de Software Libre",
TITLE 	={Liberación de Software},
EDITION 	="primera"
PUBLISHER 	="Editorial UGR",
ADDRESS 	={Granada, GR},
YEAR 	=2010 }










Vamos a analizar esta estructura:

La primera palabra, que esta prefijada por @, determina el tipo de entrada, la cual variara según el tipo de publicación que se trate: si es un libro, articulo, ...

El resto de la información esta escrita entre llaves, comenzando por una etiqueta (estas etiquetas son las que usaremos para referenciarlos con el comando \cite.

La información esta introducida en campos, y estos van separado por comas.

Dentro de cada campo la información puede ser incluida entre llaves o entre comillas dobles, si son solo números no es necesario usar los delimitadores.

Los tipos de referencias, los campos requeridos y los opcionales son:

Tipos de referencias
	Campos requeridos
	Campos opcionales
@article Artículos en revistas
	autor, title, journal, year.
	volume, number, pages, month, note
@book Libros con editorial conocida 	author or editor, title, publisher, year
	volume or number, series, address, edition, month, note
@booklet Libros sin conocimiento de la editorial que lo publique
	title
	author, howpublished, address, month, year, note
@conference Artículo en un recopilatorio de una conferencia
	author, title, booktitle, year
	editor, volume or number, series, pages, address, month, organisation, publisher, note
@inbook Entrada para una parte de un libro
	author or editor, title, chapter and/or pages, publisher, year
	volume or number, series, type, address, edition, month, note
@incollection Entrada para una parte de un libro con título propio
	author, title, booktitle, publisher, year
	editor, volume or number, series, type, chapter, pages, address, edition, month, note
@inproceedings Artículo en las publicaciones de un congreso
	author, title, booktitle, year
	editor, volume or number, series, pages, address, month, organisation, publisher, note
@manual Entrada para documentación de tipo técnico
	title
	author, organisation, address, edition, month, year, note.
@masterthesis Entrada para proyecto, tesina o master
	author, title, school, year
	type, address, month, note
@misc Documento que no se ajusta a ninguno de los demás tipos
	none
	author, title, howpublished, month, year, note
@phdthesis Tesis doctoral
	author, title, school, year
	type, address, month, note
@proceedings Recopilatorio de artículos de una conferencia o congreso
	title, year
	editor, volume or number, series, address, month, organisation, publisher, note
@unpublished Documento no publicado con titulo y autor
	author, title, note
	month, year

Para mas información: http://www.ctan.org/tex-archive/biblio/bibtex/contrib/

##Gestión de base de datos

La creación y mantenimiento de una base de datos .bib puede resultar muy simple si usamos algunos programas diseñados para manejar este tipo de archivos de forma sencilla.
Multiplataforma:

JabRef: Una interfaz libre y portable escrita en Java para administrar referencias en formato BibTeX.

JabRef

Para mas información y descarga: http://jabref.sourceforge.net/help/Contents.php

Tutorial de uso de JabRef http://www.cs.rpi.edu/~tayloj/JABREF.TUTORIAL/
También disponemos de un vídeo tutorial de uso de JabRef:

MAC
BibDesk: Un aplicación para Mac OS X para administrar referencias.

Bibdesk
Fuente de la imagen: http://osx.iusethis.com/screenshot/osx/bibdesk.png


Para mas información y descarga: http://bibdesk.sourceforge.net/

##Estilos en BibTeX

BiBTeX se acompaña de cuatro estilos llamados:

    plain
    abbrv
    alpha
    unsrt

Vamos a conocer cada uno de ellos.


plain
	

    La lista bibliográfica final se ordena alfabéticamente atendiendo a la autoría, y si hubiera más de una obra del mismo autor, se toma en cuenta al año de las mismas y después el título. Si sigue habiendo igualdad tras aplicar los criterios anteriores, el último criterio es el del orden en el que fueron citadas y, para obras citadas simultáneamente mediante “\nocite{*}”, el orden que tengan en la base de datos.
    Las obras incluidas en la lista son numeradas consecutivamente y el número asignado a cada una de ellas, entre corchetes, se convierte en la etiqueta identificativa de la misma que será impresa en el lugar en el que se encuentren los comandos “\cite” existentes en el cuerpo del documento.
    Los datos de los campos se incluyen completos.
    Para ciertos campos se añaden determinadas palabras o abreviaturas en inglés. Por ejemplo, tras el contenido del campo «edition» se añade la palabra “edition”, y hay tipos de registro en los que el nombre del campo (en inglés) forma parte de la referencia.

bbrv 	
Es idéntico al estilo «plain» salvo en el hecho de que para ciertos datos se usan abreviaturas y así el nombre de pila de los autores es sustituido por sus iniciales y el nombre de ciertas revistas (que están predefinidas en el estilo y que se refieren a la informática) es sustituido por su abreviatura.
Para la mayor parte de los usuarios, que no usan las revistas predefinidas en el estilo, la única diferencia con «plain» es que del nombre propio del autor sólo se usan las iniciales.
alpha 	Se distingue del estilo «plain» exclusivamente en el hecho de que la etiqueta de identificación de cada obra en la lista no es un número, sino un texto generado automáticamente a partir de la autoría de la referencia, el año de publicación y, en ocasiones, el inicio del título.
Asimismo la lista bibliográfica se ordena alfabéticamente según las etiquetas asignadas, y el comando “\cite” imprime, en el lugar en el que se encuentre, la etiqueta asignada a la obra citada.
unsrt 	
Es igual al estilo «plain» salvo en el hecho de que en él la lista bibliográfica no se ordena alfabéticamente, sino según el orden en el que las distintas obras que aparecen en ella fueron citadas por primera vez.
En este caso, para las obras incluidas en la lista de referencias mediante un comando “\nocite” se considerará que fueron citadas en el lugar en el que se encuentre tal comando. Y para el comando “\nocite{*}”, se usará el orden en el que las referencias se encuentren en el fichero «.bib», pero sólo para las referencias que no hubieran sido citadas antes de “\nocite{*}”.


##Inserción en un documento

Partimos que ya tenemos generado nuestra recopilación de citas.

En el lugar del documento principal en el que queramos que aparezca la lista con las referencias bibliográficas, debemos insertar las siguientes dos órdenes de LaTeX:

\bibliography{MiBiblio}
\bibliographystyle{MiEstilo}

Los comandos a utilizar para introducir una cita son:

    El comando “\cite[DatosAdicionales]{clave}” produce un doble efecto. En primer lugar, la referencia bibliográfica identificada en la base de datos mediante la clave recibida como parámetro, se incluirá en la lista bibliográfica. En segundo lugar, en el punto del documento donde se encontrara el comando, se imprimirá la etiqueta asignada a tal referencia en la lista de referencias junto con los datos adicionales que eventualmente hayamos incluido en el argumento opcional del comando.
    El comando “\nocite{clave}” produce el primero de los efectos indicados, pero no el segundo, es decir: la obra identificada por la clave será incluida en la lista bibliográfica final, y en ella se le asignará asimismo una etiqueta (como a todas las obras de la lista), pero en el lugar del documento en el que se encuentra el comando “\nocite” no se imprimirá nada.

Ambos comandos pueden recibir, como parámetro, las claves de varias referencias distintas, separadas mediante comas. Y en el caso concreto de “\nocite”, si se escribe “\nocite{*}” el efecto será incluir en la lista bibliográfica final todas las referencias bibliográficas incluidas en la base de datos.

Vamos a generar la lista de referencias bibliográficas:

Una vez que nuestro documento (llamémosle «HolaMundo.tex») está preparado, en los términos que se acaban de exponer, debemos seguir los siguientes pasos:

    Compilar con LaTeX nuestro documento «.tex». Ello hará que se genere un fichero de extensión «.aux», en el que se incluirá información sobre la base de datos a usar, el fichero de estilo a usar, y las referencias bibliográficas que hay que incluir en la lista de referencias.
    Ejecutar, desde la línea de comandos, la orden «bibtex HolaMundo». Ello hará que BiBTeX lea el fichero «.aux», generado por la anterior compilación del documento, extrayendo de él la información que necesita para trabajar: qué base de datos debe usar, qué estilo, y qué referencias hay que buscar en la base.
    Y así, tras extraer de la base de datos los registros precisos, y formatearlos de acuerdo con el estilo indicado, BiBTeX genera un fichero de extensión «.bbl» en el que se contienen los comandos de LaTeX necesarios para escribir la lista de referencias bibliográficas que hay que insertar en el documento principal.
    BiBTeX genera también un fichero adicional, de extensión «.blg» que es un fichero «.log»
    Compilar de nuevo el documento principal con LaTeX. En esta segunda compilación, al leer la orden “\bibliography”, se insertará en su lugar el contenido del fichero «.bbl» generado en el paso anterior. Asimismo la nueva compilación reescribe el fichero «.aux», añadiendo a la información que ya existía en él la generada ahora, que es más completa pues incluye los datos de la lista bibliográfica final que se acaba de insertar en el documento.
    Esta última información es usada en una nueva compilación con LaTeX para escribir correctamente los rótulos que hay que colocar en lugar de los comandos “\cite”. Y eventualmente puede ser necesaria una nueva compilación: cuando alguno de los campos de la base de datos contenga algún comando de LaTeX que implique el uso de referencias cruzadas. En particular, el comando “\cite”.

##Bibliografía sobre BibTeX 


    http://www.latex-project.org/
    Ataz López, Joaquín: Creación de ficheros LaTeX con GNU Emacs, 2004. URL http://www.ctan.org/tex-archive/info/spanish/guia-atx/
    Ataz López, Joaquín: Una introducción rápida a GNU Emacs, 2004. URL http://es.tldp.org/Tutoriales/doc-tutorial-emacs/
    Cascales Salinas, Bernardo, Lucas Saorín, Pascual, Mira Ros, José Manuel, Pallarés Ruiz, Antonio y Sánchez-Pedreño Guillén, Salvador: LaTeX, una imprenta en sus manos. Aula Documental de Investigación, 2000.
    Cascales Salinas, Bernardo, Lucas Saorín, Pascual, Mira Ros, José Manuel, Pallarés Ruiz, Antonio y Sánchez-Pedreño Guillén, Salvador: El libro de LaTeX. Pearson-Prentice Hall, 2003.
    Knuth, Donald E.: The TEX Book. Addison-Wesley, 1986.
    Kopka, Helmut y Daly, Patrick W.: Guide to LaTeX. Addison-Wesley, 4a edón., 2004.
    Lamport, Leslie: LaTeX: A document preparation system. Addison-Wesley, 1986.
    Markey, Nicolas: Tame the BeaST, 2005. URL http://www.ctan.org/tex-archive/info/bibtex/tamethebeast/
    Mira Ros, José Manuel: «Bibliografía flexible: el sistema flexbib». En TeXemplares, no 6, págs. 8–26, 2004. URL http://www.cervantex.es/cervantex/files/cervantex/texemplares6.pdf
    Patashnik, Oren: BibTeXing, February 1988. URL http://www.ctan.org/tex-archive/biblio/bibtex/contrib/doc/btxdoc.pdf
    Patashnik, Oren: Designing BibTeX Styles, February 1988. URL http://www.ctan.org/tex-archive/biblio/bibtex/contrib/doc/btxhak.pdf
    Seidel, Luis: Bases de datos bibliográficas, LaTeX y el idioma español, March 1998. URL ftp://tex.unirioja.es/pub/tex/doc/bibliogr.pdf
