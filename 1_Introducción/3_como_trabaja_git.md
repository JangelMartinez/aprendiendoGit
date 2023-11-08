# Como trabaja git #
Git solo realiza la comprobación (seguimiento) de los archivos, nunca de los directorios, por lo que si estos directorios están vacíos, no detectará los cambios. Es decir, si creamos un directorio nuevo y ejecutamos el comando "git status", Git no encontrará ningún cambio.

Si queremos que se agreguen los directorios nuevos, normalmente se procede creando un fichero llamado ".git-keep" en la carpeta que queremos realizar el seguimiento.

Una vez que ya insertes archivos en dicho directorio, se puede borrar el fichero ".git-keep" creado anteriormente.

## Flujo de trabajo de Git ##
Inicializado Git en la carpeta en la que vas a trabajar, el software va a observar continuamente los cambios que vas haciendo en dicha carpeta. Es decir, cada vez que creas, modificas o eliminas carpetas o ficheros (sea de texto, imagenes, etc ...) dentro de dicha carpeta, el sistema lo gestionará y tendrá en cuenta que ficheros están creados nuevos, modificados o eliminados. 

Estos ficheros podremos verlos mediante el comando "git status". La información que nos saldrá en un principio estará de color rojo que indica que son archivos que han sufrido cambios recientemente.

Una vez realizado todos cambios pertienentes que queramos (creación, modificación o eliminación), podremos añadirlos a un espacio virtual que asigna Git llamado "staging" o "stage" mediante un comando llamado "git add". Con este comando podremos añadir uno, varios o todos los archivos que el sistema Git a gestionado anteriormente.

Si volvemos a ejectura el comando "git status" comprobarás que los archivos añadidos al espacio "stage" tendrán un color verde para indicarte que están preparados para pasar al repositorio y crear una nueva versión. Si no has insertado todos los ficheros en el "stage" también podrás visualizar ficheros en color rojo indicando que no pasaran al repositorio aunque ejecutes el comando correspondiente.

Cuando ya se hayan añadido todos los ficheros que queramos en el "stage" procederemos a pasarlos al repositorio para realizar una nueva versión. Para eso utilizaremos el comando "git commit" lo cual creará la nueva versión de los distintos cambios y eliminandolos del "stage" ya que estos cambios se han convertido en una versión oficial desde la cual volverás a trabajar.

Al ejecutar "git status" otra vez, podrás ver los ficheros en rojo que no habias añadido al "stage" o en su defecto, no aparecerá nada ya que, como he dicho antes, los cambios han pasado a ser oficiales.

Hasta aquí es el flujo de trabajo de git en local, pero hay un siguiente paso que siempre se suele hacer que es añadirlo a un servidor remoto para tener una copia externa. Esto se realiza mediante el comando "git push". Cuando se utiliza este comando, verificará todos los cambios oficiales que has realizado anteriormente con "git commit" y los subirá al servidor con el que estés trabajando.

***
***NOTA:*** 

*Hay que tener en cuenta que tanto "git add", "git commit" y "git push" disponen de parámetros obligados y otros opcionales para poder ejectuarlos.*

***


