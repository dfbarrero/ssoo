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

![GNU logo](figs/gnu-logo.png)

El movimiento del software libre fue creado por Richard Stallman a principios de los años setenta. Por aquél entonces Stallman trabajaba en el Laboratorio de Inteligencia Artificial del MIT, y lo abandonó para fundar la \emph{Free Software Foundation} (FSF) y el proyecto GNU (*Gnu is not Unix*), en el que quería implementar un sistema Unix completo, esto es, un SO Unix libre, junto con todas las aplicaciones necesarias para el usuario, también libres. GNU, en vez de empezar creando un SO libre, empezó a implementar todo el ecosistema de aplicaciones de desarrollo: editores de texto (emacs), compiladores (gcc), depuradores (gdb), y un largo etcétera.

Actualmente, el software libre ha evolucionado para generar una serie de corrientes que amplían el concepto de libertad dentro un contexto ecnológico para abordar otros ámbitos distintos del software. Tal vez el más conocido sea el movimiento de la cultura libre, que defiende un acceso
libre a recursos culturales, y cuyo máximo exponente es la Wikipedia, por todos conocida. Además, hay notables intentos para ampliar la filosofía del software libre a creaciones sujetas a propiedad intelectual, como son textos, documentación o imágenes. En este ámbito es conocido *Creative Commons*, un conjunto de licencias que permite al autor introducir distintas restricciones en la utilización de sus obras.

## Linux

Linux es un SO de tipo Unix, desarrollado inicialmente por el finlandés Linus Torvals. En sus orígenes, Linux nació como un divertimento de Linus, que quería probar las funciones avanzadas de su recién estrenado 386. Llegado un momento en el que el núcleo de Linux era mínimamente publicable, Linus decidió publicar su código en Internet bajo una licencia libre a principios de los 90. A partir de entonces, distintos voluntarios distribuidos por todo el mundo empezaron a contribuir con código y Linux experimentó una rápida evolución, marcando lo que sería la evolución del software libre hasta la actualidad: redes de desarrolladores colaborando a través de Internet, al contrario del modelo centralizado de GNU alrededor de la FSF. Si bien hoy en día este modelo de desarrollo (a veces nombrado *modelo de bazar*) está coexistiendo con otros modelos más centralizados, fundamentalmente debido a la cada vez mayor presencia de grandes empresas en torno a Linux y el software libre, y a la creación de grandes fundaciones en torno a los proyectos más significativos, como Firefox o Gnome.

![TUX, la mascona de Linux](figs/tux.png)

Un elemento fundamental de Linux que suele generar confusión es que cuando  habla de Linux, estrictamente hablando, se habla únicamente del SO. Es decir, Linux es un SO, y por lo tanto no tiene aplicaciones que, en definitiva, es lo que el usuario necesita. Precisamente cuando Linux nació, el proyecto GNU maduró lo suficiente como para tener una amplia gama de aplicaciones de alta calidad operativas, desde compiladores (gcc), a editores de texto (vi, emacs), herramientas de desarrollo (make, gdb) y un largo etcétera. La unión de dichas herramientas con Linux dio lugar a lo que se conoce como GNU/Linux, un sistema perfectamente funcional basado en software libre, tal y como el proyecto GNU pretendía conseguir.

Actualmente Linux es un SO muy extenso, fundamentalmente en entornos de servidores, pero también en equipos de escritorio y sistemas empotrados. Linux soporta un amplio abanico de arquitecturas y ámbitos de aplicación, desde servidores de altas prestaciones (el ordenador más potente del mundo corre bajo Linux), hasta la telefonía móvil con Android (un SO basado en Linux). Además, las colaboraciones en el desarrollo se han venido profesionalizando al contar con el respaldo de gigantes de la industria como IBM o Intel.

Linux es utilizado en un amplio rango de aplicaciones:

- Informática de usuario, contando con un amplio rango de entornos gráficos (GNOME, KDE) y herramientas (OpenOffice, Firefox).
- Servidores. Es donde Linux tiene la mayor cuota de mercado. Linux se suele utilizar con aplicaciones como Apache (servidor web), BIND (servidor DNS) o Sendmail (servidor de correo electrónico). 
- Sistemas empotrados. Linux se ha portado a plataformas utilizadas habitualmente en sistemas empotrados, y por lo tanto es posible encontrar coches que utilizan Linux o incluso satélites espaciales.
- Dispositivos inteligentes. Un sector con un fuerte crecimiento en la actualidad son los dispositivos inteligentes, como los teléfonos inteligentes. En este contexto, SSOO pesados son adaptados para poderse utilizar con este tipo de dispositivos. Como ejemplo encontramos Android, un SO desarrollado por Google y que está basado en Linux.

## Distribuciones

Un concepto que suele generar confusión es el de distribución. Como se ha comentado anteriormente, Linux es un SO, y sólo un SO. Por lo tanto, Linux por sí mismo es inútil para el usuario, necesita además un conjunto de aplicaciones, un programa de instalación y soporte como actualizaciones de software. Normalmente todos estos elementos son empaquetados en lo que se denomina una distribución. Así pues, distribución es el conjunto formado por Linux, distintas aplicaciones, y un programa de instalación.

Distribuciones hay muchas, y aunque todas utilizan Linux, son diferentes entre sí porque incluyen distintos programas y, por lo general, están enfocadas a distintos tipos de usuario. A continuación se enumeran las distribuciones más conocidas:

- **Ubuntu** Posiblemente la distribución más popular en estos momentos. Está basada en Debian, pero utiliza software más actualizado y con un proceso de instalación más amigable. Es conocida por su acabado cuidado, y por tener un buen equilibrio entre facilidad de uso y potencia.
- **Debian** Está mantenida por un grupo de voluntarios y se base estrictamente en los principios del software libre, de tal manera que no se incluye en la distribución ningún programa que no se ajuste perfectamente a los parámetros del software libre. Tiene ciclos de liberación muy largos, y por lo tanto el software suele estar algo desactualizado. Por el contrario, es la distribución más testeada, y por lo tanto estable, lo que la hace especialmente indicada para servidores. Se la considera una distribución poco amigable y sus seguidores suelen ser usuarios avanzados.
- **Red~Hat** Red Hat es una empresa que por mucho tiempo tenía la distribución de Linux más popular, hasta que decidió dedicarse exclusivamente al entorno empresarial, por lo que dejó de mantener la distribución de Red Hat para dedicarse en exclusiva a la Red Hat Enterprise Linux.
- **Fedora** Cuando Red Hat dejó de mantener su distribución no empresarial un grupo de voluntarios decidió seguir manteniendo la distribución de Red Hat, que se pasó a llamar Fedora.
- **SUSE** Distribución alemana pensada para usuarios no expertos, por lo general cuenta con una presentación muy cuidada y fácil manejo. Actualmente está enfocada al sector empresarial.

### Ejercicios

1.- Buscar la diferencia entre software libre, software propietario y dominio público en Internet.
2.- ¿Es Linux el único SO libre? En caso negativo, buscar ejemplos de SSOO libres.
3.- ¿Es el software libre necesariamente gratis? Utilizar Internet en caso de ser necesario.
4.- Enumerar al menos cinco distribuciones.
5.- Seleccionar las tres principales distribuciones y describir a quién está dirigida la distribución y en qué contextos es recomendable utilizarla.
6.- Seleccionar cinco tareas comunes que se realicen en el ordenador, como navegar en Internet, chatear, o editar textos, y buscar un programa libre con el que se pueda hacer cada tarea.
7.- ¿Todos los programas libres están hechos para un entorno Unix?
8.- ¿Qué diferencia existe entre Unix y Linux?


## Introducción a la práctica

Actualmente Linux ofrece un entorno gráfico muy potente, atractivo, y fácil de utilizar, con un gran número de aplicaciones que satisfacen un amplio espectro de necesidades. En torno a Linux hay una leyenda negra que afirma que es un sistema complejo, difícil de utilizar, y en gran medida se debe a la consola; y precisamente el objetivo de la práctica es introducir el manejo de la consola.

La consola es un terminal en modo texto con la que se accedía a los SSOO antes de la aparición de los entornos gráficos.

Actualmente el uso de la consola no es necesario para manejar un SO a  nivel de usuario, pero sigue siendo necesario su conocimiento para un  profesional de la informática y para fines didácticos. Es necesario aprender el manejo de la consola porque los entornos gráficos abstraen muchos elementos del SO para simplificar su uso, lo cual es muy adecuado
para un usuario, pero un profesional debe conocer lo que hay por debajo.
Por otra parte, estos conceptos son los que se estudian en la asignatura,
y, por lo tanto, manejar la consola supone un complemento necesario
a las clases teóricas. Los entornos gráficos son una extraordinaria ayuda para los usuarios, carecen de importantes limitaciones cuando se pretende extraer el máximo rendimiento al SO. En el caso de Unix la consola es especialmente potente, mucho más que el entorno gráfico, lo cual es especialmente importante en la administración de sistemas. Por último, una vez que se supera la fase de aprendizaje (y probablemente también superado el trauma de enfrentarse a la consola por primera vez), el manejo de la consola resulta mucho más cómoda que el entorno gráfico; el teclado es más rápido que el ratón.

### Entorno del laboratorio

El laboratorio está formado por un PC que va a actuar como servidor centralizado donde trabajará cada alumno, y
un conjunto de ordenadores personales conectados entre sí a través de una red de área local formada
por los ordenadores del laboratorio L4, L5 y L6. El servidor dispone
de su propia versión de Unix ya instalada. A cada grupo de laboratorio
se le asignará un nombre de usuario para conectarse a dicho servidor.
Los puestos de trabajo tienen instalado como SO local
Windows o Linux, sin embargo para las prácticas se utilizará
Linux.

Para simplificar la gestión de los equipos del laboratorio se ejecutará
Linux dentro de una máquina virtual. Una máquina virtual consiste
en un programa que simula ser un ordenador físico sobre el cuál puede
ejecutarse cualquier programa, por ejemplo, un SO. Dentro de un entorno
virtual se opera exactamente igual que si se estuviera trabajando
sobre el hardware físico, pero se facilita mucho la gestión, por ejemplo,
reponer un sistema virtualizado dañado es tan sencillo como copiar un archivo,
mientras que reponer un sistema real implica toda la reinstalación
del SO. Otra ventaja es que una máquina virtual es copiable, es decir,
la máquina virtual del laboratorio se puede copiar en una memoria USB
y luego utilizarse en casa. Por último, una ventaja no menor, es que
con una máquina virtual se puede instalar Linux en cualquier ordenador
sin necesidad de reparticionar el disco duro, con los riesgos que tiene
dicha operación.

Para acceder a la máquina virtual hace falta seguir el siguiente proceso.
Primero se arranca la máquina siguiendo las instrucciones proporcionadas
por el profesor de la asignatura. Posteriormente se realiza el *login*
al sistema, con el usuario y contraseña que se indiquen en clase.
En este momento se está dentro de un sistema Linux no virtualizado
(el *host*), por lo que es necesario arrancar la máquina virtual,
cuyo icono aparece en el escritorio. A partir de entonces se abre
una ventana en la que aparece todo el proceso de arranque de Linux,
todo lo que se haga dentro de la ventana será igual a estar delante
de una máquina física con Linux. Una vez haya arrancado es necesario
volver a introducir los datos del *login*, y a partir de entonces se
está en el entorno virtual en donde se realizarán las prácticas con
seguridad.

La totalidad de las prácticas se realizarán dentro del terminal, haciendo
caso omiso al entorno gráfico que, en principio, resulta trivial de
utilizar y por lo tanto no se explicará. Existen varias formas de
acceder al terminal, la más sencilla es ir al menú y seleccionar
la aplicación *Terminal* o *Consola*.

### Cambio de contraseña

Una de las primeras labores a realizar si todavía no tiene contraseña
es introducir una. Para introducir o modificar una contraseña se utiliza
la orden *passwd*. **A efectos de todas las prácticas de la asignatura
NO deberá CAMBIAR EL PASSWORD sin previamente consultar con los
profesores del laboratorio.**

Antes de cambiar la contraseña, passwd pide la contraseña actual como
medida de seguridad. A continuación, se pide la nueva contraseña y,
si ésta es válida, se vuelve a pedir para confirmar que el usuario
no se confundió al teclearla, puesto que los caracteres no aparecen
en pantalla. Sólo entonces se cambia la contraseña. Es conveniente
cambiar la clave de acceso periódicamente por razones de seguridad.

Una recomendación básica aplicable a cualquier situación es que a
la hora de elegir contraseña esté formada por 6 caracteres
como mínimo, y al menos uno de los caracteres sea numérico o un carácter especial. Con esto conseguimos dificultar mucho los ataques de fuerza bruta y los ataques de diccionario. Ejemplos de contraseñas recomendadas: asadc0, g0tr2is, !as\#ws. Ejemplos de contraseñas no recomendadas: hola, inicio, asf1, fernando.

Es importante resaltar que **Unix distingue entre mayúsculas y minúsculas**, por lo que las contraseñas: *Tracy123*, *tracy123*, *trAcy123* y *TraCY123* son distintas.

Un ejemplo de cambio de contraseña puede ser el siguiente.

~~~
$ passwd

Changin password for so25

Old password: (contraseña~actual)

New password: (nueva~contraseña)

Re enter new password: (teclear de nuevo la nueva)

$~(la~contraseña~ha~sido~cambiada)
~~~


### Procedimiento de desconexión

Al igual que es necesario seguir una secuencia determinada para poder
acceder al sistema, también es necesario indicar cuándo se da por
finalizada una sesión de trabajo. De esta forma se libera el terminal
para que pueda ser empleado por otro usuario y se evita que otros
usuarios puedan acceder a nuestra información, dañarla o destruirla.
La desconexión se consigue sin más que teclear la orden *exit*, o bien
pulsando simultáneamente las teclas *Ctrl+d*, a lo que el sistema responde
con el mensaje

~~~
logout
~~~

indicando que da por finalizada la conexión. Si lo que queremos es
apagar el sistema, deberemos introducir la orden

~~~
shutdown~-h~now
~~~

o bien apagarlo mediante el entorno gráfico.


### Ejercicios

- Realizar un *login* al equipo del laboratorio.
- Si se dispone de equipo propio, instalar una distribución de Linux en dicho equipo o en una máquina virtual.


## Manejo básico de la consola

### Intérprete de órdenes (la consola)

Existen diversos mecanismos para que un usuario se comunique con el SO.
Por lo general, los usuarios interaccionan con procesos, y los procesos
se comunican con el SO por medio de algo denominado *llamadas
al sistema*. A veces es necesario una comunicación más directa con
el SO, de manera que el usuario pueda realizar operaciones más básicas,
como mover un archivo. Los SO modernos suelen utilizar interfaces
gráficas, sin embargo también posibilitan una interfaz más rudimentaria,
basada en texto, llamado intérprete de órdenes, consola, *shell*,
o terminal.

En definitiva, un intérprete de órdenes es un programa en modo texto
encargado de hacer de intermediario entre el usuario y el SO. El usuario
introduce órdenes en el intérprete, y éste las interpreta, como bien
dice su nombre, y realiza las acciones oportunas con el SO para ejecutar
dichas órdenes. Análogamente, el intérprete obtiene la salida del
SO y se lo presenta al usuario. Los intérpretes
de órdenes funcionan en modo texto, y es la manera habitual de trabajar,
por ejemplo, en la administración de servidores UNIX, porque ofrecen
una interfaz sencilla y extremadamente potente. El intérprete es la forma
de comunicación más cercana al SO que, sin programar, un usuario puede
utilizar. Por lo tanto, es algo que todo profesional de la informática,
y más concretamente un ingeniero, debe conocer.

Un intérprete de órdenes es un programa normal y corriente. De hecho,
existen varios intérpretes disponibles: *tch*, *sh*, o *csh*,
por ejemplo. Con diferencia, el intérprete más extendido es *bash*
(*Bourne Again SHell*), que es el que se utiliza en el laboratorio.
Por ejemplo, para ver la version de *bash* que se está ejecutando se
puede introducir la siguiente orden:

~~~
bash --version
~~~

y se obtendrá una salida similar al siguiente texto

~~~
simpson@evergreen:~$ bash --version
GNU bash, version 5.1.16(1)-release (x86_64-pc-linux-gnu)
Copyright (C) 2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
~~~

La línea en la cual se introducen las órdenes se conoce como **prompt**,
y es importante porque muestra información útil para el usuario: en
primer lugar el nombre del usuario, *simpson* en este caso, y el
nombre de la máquina (*evergreen*). A continuación, aparece el
directorio de trabajo (~), que se explicará posteriormente.

Con el ejemplo anterior se puede apreciar la forma general de una
orden en Unix. La estructura general de cualquier orden en Unix es:

~~~
nombre [modificadores] [parámetros]
~~~

siendo *nombre* el nombre del programa u orden a ejecutar, y suele ir seguido
por una serie de modificadores con sus respectivos parámetros. Lo
más común es que todas las órdenes admitan modificadores que suelen
comenzar con el signo - (menos) y por una única letra, o bien -- (dos
guiones) seguidos de una palabra, que es más fácil de memorizar, pero
más largo de escribir. Por lo general, todo modificador se puede poner
tanto en formato reducido como en formato nemotécnico. El propósito
de los modificadores es caracterizar, alterar o configurar el funcionamiento de una orden.

Estos modificadores pueden ir seguidos sin necesidad de colocar espacios
en blanco entre ellos. Por ejemplo, la orden *ls* muestra el contenido
de un directorio:

~~~
homer@evergreen:~$ ls nombres.txt
~~~

sin embargo podemos obtener más detalles de los contenidos del directorio
con el modificador *-l*:

~~~
homer@evergreen:~$ ls -l nombres.txt

-rw-rw-r-- 1 homer homer 288371 sep  4 15:18  nombres.txt
~~~

los parámetros se pueden concatenar, por lo tanto la orden *ls -l -a* 
es equivalente a la orden *ls -la*.

La orden *ls* sirve para visualizar los archivos que contiene un directorio. Más adelante en la práctica se verá en detalle el funcionamiento de esta orden.

Los parámetros deben estar separados por espacios en blanco y suministran información adicional a la orden. Ejemplo:

~~~
$ ls -l .profile

$ cat archivo.txt
~~~

Además es importante señalar que Unix casi siempre distingue las mayúsculas de las minúsculas, al contrario que otros sistemas operativos como Windows.

### Atajos

Dado lo mucho que se utiliza el terminal, existe una multitud de trucos
para poder trabajar cómodamente con el terminal, de hecho, una vez
que se conocen, resulta mucho más rápido y cómodo trabajar con el
terminal que con el interfaz gráfico.

Tal vez el atajo más utilizado
es el tabulador, que permite completar órdenes y nombres de archivos.
Por ejemplo, si se escribe 'l' y luego se pulsa el tabulador,
aparecerá una lista de todas las órdenes que empiezan por 'l'. 
Lo mismo se aplica al autocompletado de nombres de archivos. Otro
truco que se utiliza constantemente es el historial de órdenes, al
que se accede utilizando las teclas del cursor arriba y abajo.

Aunque no sean atajos propiamente dichos, es necesario conocer que
existen combinaciones de teclas especiales que tienen funciones útiles.
El más importante es *Crtl+c*, que cancela la ejecución de una
orden. Otro carácter especial muy utilizado es *Crtl+z*, que
detiene temporalmente la ejecución de una orden, devolviendo al usuario
al terminal. Esta cuestión se verá más en detalle en la siguiente
práctica. Se puede retomar la ejecución de la orden ejecutando
*fg*. Se pueden probar estas dos funciones, por ejemplo, mediante
la orden *sleep 10*, que detiene la ejecución del terminal durante
10 segundos.

### Ayuda

Existe un número ingente de órdenes en Linux, y cada orden cuenta con
un gran, a veces grandísimo, número de parámetros. Evidentemente resulta
imposible aprender de memoria toda esta información, además de innecesario.
Linux cuenta con un excelente sistema de ayuda, y, de hecho, es habitual
utilizarlo de manera constante incluso en un ámbito profesional con años de experiencia
en administración. Conocer el sistema de ayuda es imprescindible para poder
trabajar cómodamente con Linux.

En primer lugar, la mejor ayuda que hay en todo lo relacionado con
Linux no está en Linux, sino en Internet. Existe una extensísima cantidad
de documentación de alta calidad, y un buen buscador nos puede facilitar
la información que necesitamos con rapidez. Es necesario acostumbrarse
a utilizar Internet para buscar información.

Casi todas las órdenes admiten el modificador --help y -h (ambos son equivalentes),
que muestran ayuda sobre dicha orden. También existen herramientas específicas
para encontrar información, la más conocida, y utilizada, es la orden \emph{man},
y se usa tal y como se detalla a continuación:

#### man 
~~~
Sintaxis: man <término>
~~~

En Unix es posible obtener información detallada en línea sobre cualquier
aspecto del sistema sin más que teclear *man* y el término sobre el
que queremos obtener información. Esto muestra en pantalla las páginas
del Manual de Referencia de Unix asociadas al término (orden, archivo,
llamada al sistema, etc.). Para moverse en la pantalla de ayuda, se puede
utilizar las teclas de cursor y se sale pulsando la tecla "q".

El manual está dividido en un conjunto de secciones de las cuales las tres primeras son estándar:

* Sección 1 - Ordenes de usuario
* Sección 2 - Llamadas al sistema
* Sección 3 - Biblioteca de funciones estándar de C

Ejemplo de uso:

~~~
$ man man

MAN(1)                                                                                    Manual pager utils                                                                                   MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...
~~~


En el ejemplo, (1) indica el número de sección. Cuando un término
tiene varias entradas en diferentes secciones, *man término* muestra
siempre la información contenida en la primera de ellas. Si se quiere
consultar otras secciones es necesario indicarlo por ejemplo:

~~~
$ man nro\_sección término
~~~

Aparte de las páginas *man*, existen otras órdenes útiles para buscar
información; las dos más importantes son *apropos* e *info*.
Se deja como ejercicio buscar información sobre dichas órdenes utilizando
*man*.

