# Que es Git y como funciona #
Git es un software sistema de control de versiones. Aunque no es el único software que realiza dicha función, si que es el más conocido y más usuado por sus potentes opciones y es capaza de manejar proyectos pequeños como grandes.

Otros software de control de versiones son:

- CVS
- Apache Subversion
- Mercurial
- Monotone

También existen control de versiones en sitios que utilizamos comúnmente en la nube como en los servicios de almacenamiento "Google Drive" o "Dropbox". Estos servicios van guardan copias de versiones de nuestros ficheros que vamos cambiando o editando in-situ.

## Que es un sistema de control de versiones ##

Un sistema de control de versiones es una herramienta de software que monitoriza y gestiona cambios en un sistema de archivos. Con lo cual ayuda, principalmente, a los equipos de desarrollo de software a gestionar su código fuente a lo largo del tiempo.

Si trabajas solo, te ayuda a tener controlado el software permitiendo revertir y deshacer cambios de una versión a otra y realizar copias externas. Pero sobre todo, es muy importante cuando trabajas en equipo ya que te ayuda a corregir o resolver conflictos en caso de que dos personas hayan estado trabajando en el mismo fichero y hayan modificado código fuente entre si.

Además de hacer una gestión local de los archivos con sus versiones correspondientes según los cambios que haces, como hemos comentado antes, también te ayuda a hacer copias externas mediante comandos para poderlos tener en la nube en caso de tener algún problema en tu pc. 

Los sitios donde puedes tener las copias son, por ejemplo, [Github](https://github.com/), [GitLab](https://about.gitlab.com/) o [gitbucket](https://bitbucket.org/) que suelen ser los más utilizados. Aunque hay también otros menos conocidos.

## Flujo de trabajo de Git ##
Inicializado Git en la carpeta en la que vas a trabajar, el software va a observar continuamente los cambios que vas haciendo en dicha carpeta. Es decir, cada vez que creas, modificas o eliminas carpetas o ficheros (sea de texto, imagenes, etc ...) dentro de dicha carpeta, el sistema lo gestionará y tendrá en cuenta que ficheros están creados nuevos, modificados o eliminados. 

Estos ficheros podremos verlos mediante el comando "git status". La información que nos saldrá en un principio estará de color rojo que indica que son archivos que han sufrido cambios recientemente.

Una vez realizado todos cambios pertienentes que queramos (creación, modificación o eliminación), podremos añadirlos a un espacio virtual que asigna Git llamado "staging" o "stage" mediante un comando llamado "git add". Con este comando podremos añadir uno, varios o todos los archivos que el sistema Git a gestionado anteriormente.

Si volvemos a ejectura el comando "git status" comprobarás que los archivos añadidos al espacio "stage" tendrán un color verde para indicarte que están preparados para pasar al repositorio y crear una nueva versión. Si no has insertado todos los ficheros en el "stage" también podrás visualizar ficheros en color rojo indicando que no pasaran al repositorio aunque ejecutes el comando correspondiente.

Cuando ya se hayan añadido todos los ficheros que queramos en el "stage" procederemos a pasarlos al repositorio para realizar una nueva versión. Para eso utilizaremos el comando "git commit" lo cual creará la nueva versión de los distintos cambios y eliminandolos del "stage" ya que estos cambios se han convertido en una versión oficial desde la cual volverás a trabajar.

Al ejecutar "git status" otra vez, podrás ver los ficheros en rojo que no habias añadido al "stage" o en su defecto, no aparecerá nada ya que, como he dicho antes, los cambios han pasado a ser oficiales.

Hasta aquí es el flujo de trabajo de git en local, pero hay un siguiente paso que siempre se suele hacer que es añadirlo a un servidor remoto para tener una copia externa. Esto se realiza mediante el comando "git push". Cuando se utiliza este comando, verificará todos los cambios oficiales que has realizado anteriormente con "git commit" y los subirá al servidor con el que estés trabajando.

    NOTA: Hay que tener en cuenta que tanto "git add", "git commit" y "git push" disponen de parámetros obligados y otros opcionales para poder ejectuarlos.



