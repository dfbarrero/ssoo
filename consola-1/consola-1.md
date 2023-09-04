# La consola de Linux (I)

## Competencias asociadas a la práctica
- Comprender qué es el software libre así como las diferencias respecto al software propietario.
- Asimilar la importancia de manejar adecuadamente la consola de Unix.
- Diferenciar los conceptos de sistema operativo y distribución.
- Saber utilizar órdenes útiles en Unix como: *clear*, *date*, *echo* y *who*.
- Tener capacidad de buscar información a través del sistema de ayuda de Unix y a través de Internet.
- Saber utilizar órdenes de búsqueda de información en Unix: *man*, *whatis*, *apropos* e *info*.
- Saber utilizar los caracteres comodines en las órdenes de Unix.
- Comprender la estructura de directorios de un sistema Unix.
- Comprender la diferencia entre directorio de conexión, directorio actual y directorio raíz.
- Saber utilizar los directorios ``.'' (punto) y ``..'' (punto-punto) para moverse por el sistema de archivos de Unix.
- Saber utilizar la trayectoria absoluta y relativa para nombrar archivos en las órdenes de Unix. 
- Ser capaz de moverse con soltura por la estructura de directorios de un sistema Unix.
- Ser capaz de realizar las tareas comunes en la gestión de archivos, como crear, borrar copiar y mover archivos (y directorios, como tipo especial de archivos en Unix).
- Ser capaz de visualizar el contenido de archivos de tipo texto utilizando órdenes de Unix: *cat*, *head* y *more*.
- Ser capaz de comprender la diferencia entre enlace fuerte y enlace débil y su importancia a la hora de compartir información.
- Ser capaz de manejar enlaces fuertes y enlaces débiles en la consola de Unix utilizando la orden *ln*.
- Ser capaz de gestionar adecuadamente los permisos y propietarios de los archivos en un sistema Unix con las órdenes *chmod*, *chown*, *umask* y *chgrp*.
- Ser capaz de realizar tareas comunes en el manejo de un SO como instalar o desinstalar paquetes a través de la consola: órdenes *apt-get* y *apt-cache*.
- Ser capaz de realizar tareas comunes para archivar infomación a través de la consola: empaquetar archivos con la orden *tar*, o comprimir/descomprimir archivos con las órdenes *gzip* y *gunzip*, respectivamente.


## Introducción

El estudio de los Sistemas Operativos (SSOO) tradicionalmente se ha centrado en SSOO de tipo Unix. Los sistemas Unix son un conjunto de SSOO cuyos orígenes se remontan a la Universidad de Berkeley en los años 60, y han ejercido una gran influencia en el desarrollo de la informática hasta la actualidad.  En esencia, Unix es un sistema operativo (SO) creado en los años 60 por Ken Thompson y Dennis Ritchie que ha tenido una gran importancia en la historia y presente de la informática.  Actualmente existen diversos SSOO creados bajo la inspiración de UNIX, de los que se dicen que son SSOO tipo Unix. Tal vez el SO tipo  Unix más conocido y extendido en la actualidad es Linux, sin embargo hay muchos más: Solaris, AIX, FreeBSD, NetBSD, etc.

El motivo fundamental de utilizar Unix es que se plasman en él de una manera muy clara diversos conceptos básicos que en otros SSOO quedan ocultos por las capas de abstracción. Por lo tanto, existe casi una unanimidad en las asignaturas de SSOO de todas las universidades para utilizar Unix como base. Hay que tener en cuenta que Unix ha marcado la evolución de la informática en muy distintos ámbitos. Por ejemplo, Unix revolucionó el mundo de los SSOO al ser el primer SO programado en un lenguaje de alto nivel, C, que de hecho se diseñó con la tarea específica de implementar SSOO.  La práctica totalidad de lenguajes de programación utilizados en la actualidad han derivado directamente de C (C++, Java, C\#), o bien han estado muy influidos por él (PHP).

Otro área en donde Unix ha desempeñado un papel fundamental es en Internet, cuyo germen surgió a finales de los años 60 y se alineó con Unix desde sus inicios. Unix sirvió de plataforma para desarrollar toda la infraestructura de Internet, e Internet, a su vez, sirvió para que Unix se desarrollara como un SO orientado al trabajo en red. Finalmente, y desde una perspectiva más práctica, los sistemas Unix son los más extendidos en grandes sistemas, fundamentalmente servidores, por lo que existe además un gran interés práctico. Hay un mercado laboral importante para administradores de Unix.

La práctica está orientada para servir como primer contacto con un sistema Unix, en nuestro caso Linux. Se pretende mostrar el funcionamiento básico de Unix, y facilitar los conocimientos elementales para poder trabajar bajo esta plataforma.

Linux es un SO que tiene una historia y un contexto social bastante particular que ha impregnado su evolución. Conocer este contexto es fundamental para entender por qué Linux es lo que es. A continuación, se hace una breve introducción a todas estas cuestiones de carácter más filosófico e histórico que técnico.


## Software libre

Linux es el producto más conocido de un movimiento mucho más amplio conocido como software libre. El software libre es aquel software que está sujeto a un tipo de licencia que, lejos de restringir la libertad del usuario, está diseñada para preservar dicha libertad. En este contexto, se entiende que la libertad del usuario está constituida por cuatro libertades fundamentales: (1) libertad para ejecutar, (2) libertad para distribuir, (3) libertad para estudiar el programa (ver el código fuente), y finalmente (4) libertad para modificar el programa. Por lo tanto se considera que es software libre todo aquél software que el usuario puede utilizar sin ningún tipo de restricción, copiarlo y distribuirlo, cuyo código fuente está disponible para ser estudiado, y que además se puede utilizar para modificar el programa o utilizar parte de ese código en terceras aplicaciones. La restricción fundamental que se introduce es que todo programa que utilice código libre, debe ser a su vez libre.


