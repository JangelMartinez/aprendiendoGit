# Comandos iniciales para empezar a trabajar #
Entre el 95-98% de las veces vas a utilizar los comandos básicos de Git. Estos comandos son con los que vas a gestionar el flujo de trabajo de Git en nuestra carpeta de trabajo o repositorio.

## git status ##

    git status

Este comando es el que nos indica si está habiltiado Git en nuestro proyecto y nos irá indicando los cambios producidos en nuestro repositorio local.

Si está vacío y no da error, significa que estamos trabajando con Git pero no hay ningún cambio en el proyecto.

Si los archivos que aparecen están en color rojo, significa que estamos trabajando con Git y hay cambios en el repositorio que aún no se han añadido al "stage".

Si los archivos que aparecen están en color verde, significa que estamos trabajando con Git y los cambios que se han producido están en el "stage" a la espera de confirmarlos con un "commit" para crear una versión nueva.

También puede haber una mezcla de colores rojos y verdes, lo que significará que hay unos ficheros que no se han añadido al "stage" (rojo) y otros si que están añadidos al "stage" (verde) a la espera de la confirmación.

Hay que tener en cuenta que cuando se haga el "commit" solo pasaran a formar parte de la nueva versión los que estaban en color verde. En cambio, los que están en color rojo permanecerán esperando a pasarlos al "stage" y despues confirmarlos.

Una vez hecho el commit, si utilizais el comando "git status" verificaras que los archivos que estaban en verde han desaparecido ya que para el sistema ya no son archivos modificados, sino que son ya una versión nueva.

## git add ##

    git add

Este comando es el que añade los cambios seleccionados a la zona "stage" y finalmente serán confirmados con el "commit".

Hay diversas opciones de añadir al "stage" los cambios:

    git add .

Con el punto le indicamos que queremos añadir todos los cambios que hay en el "status" al "stage".

    git add archivo

Con el nombre de archivo le indicamos que queremos añadir ese archivo especifico al "stage".

    git add directorio/*    (windows)
    git add directorio\*    (linux)

Con el nombre de directorio le indicamos que queremos añadir todos los cambios de ese directorio al "stage".

    git add -a archivo

Con la opción "-a" y el nombre de archivo, puedes seleccionar que parte modificado del archivo indicado puedes añadirlo al "stage". Si se confirma con el "commit", solo pasará a la nueva versión del fichero la parte seleccionada por el usuario.

## git commit ##

    git commit

Este comando es el que confirma los cambios realizados y que están en la zona "stage". Para realizar este comando es necesario incorporar un mensaje indicando que es lo que ha cambiado y el motivo (fixbug, hotfix, new feature, etc..)

Se puede utilizar de varias formas:

    git commit

Se abre un fichero donde se le debe añadir un mensaje explicativo de los cambios realizados. Una vez guardado el fichero se da por confirmado los cambios.

    git commit -m "mensaje"

Con la opción "-m" se le indica que se le incorpora un mensaje. El mensaje siempre tiene que ir entre comillas dobles. Esto hace que se confirme los cambios con el mensaje introducido entre comillas sin necesidad de abrir un fichero y guardarlo como anteriormente.

    git commit -a -m "mensaje"

Con la opción "-a" le indicamos que lo añada anteriormente al "stage" todos los ficheros que hay en el "status" para confirmarlos con el mensaje insertado.

Normalmente, esta opción, se utiliza cuando no se ha utilizado anteriormente el "git add".

Una vez confirmado los cambios, se creará una versión nueva de dichos cambios, pudiendo volver a la versión anterior en caso de ser necesario.

Los cambios confirmados, desaparecerán del "git status", donde solo aparecerán los cambios que no se habian añadido a la zona "stage" en caso de haberlos. En caso contrario, aparecerá vacío.

## git log ##

    git log

Este comando es el que permite ver información de las confirmaciones realizadas anteriores. Ayudando a realizar un seguimiento de lo que se ha realizado en el repositorio o proyecto.

En esta información se puede ver el mensaje del "commit" que se realizó, la persona que lo realizó y a que fecha y hora se hizo.

## git help ##

    git --help

Como se ha comentado anteriormente, se puede utilizar este comando para ver todas las opciones que tiene Git.

Si deseas ver la ayuda de cualquier comando en concreto, también lo puedes hacer escribiendo el comando y poniendo el "--help" al final.

    git add --help
    git commit --help
    ...

