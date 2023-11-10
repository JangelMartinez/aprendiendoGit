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

    git add directorio\*    (windows)
    git add directorio/*    (linux)

Con el nombre de directorio le indicamos que queremos añadir todos los cambios de ese directorio al "stage".

    git add -p archivo

Con la opción "-p" y el nombre de archivo, puedes seleccionar que parte modificado del archivo indicado puedes añadirlo al "stage". Si se confirma con el "commit", solo pasará a la nueva versión del fichero la parte seleccionada por el usuario.

    git add -A

Con la opción "-A" agrega todos los archivos sin seguimiento (y no omitidos), así como los que han cambiado, a los archivos que ya están bajo control de Git.

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

    git comit -m "mensaje" archivo

Poniendo el nombre del archivo al final hace que se almacene provisionalente y se confirme si Git ya lo tiene en el índice (solo comprueba la existencia de un archivo).

Una vez confirmado los cambios, se creará una versión nueva de dichos cambios, pudiendo volver a la versión anterior en caso de ser necesario.

Los cambios confirmados, desaparecerán del "git status", donde solo aparecerán los cambios que no se habian añadido a la zona "stage" en caso de haberlos. En caso contrario, aparecerá vacío.

### El commit perfecto ###
Para realizar el commit perfecto hay que tener en cuenta lo siguiente:

1. El asunto (subject). La explicación debe ser corta para dar a entender de que va.
2. El cuerpo (body), donde se explica más detalladamente los cambios que se han hecho.

Para rellenar el cuerpo y dar una buena explicación se debe contestar a las siguientes preguntas.

- ¿ Qué hay de diferente ahora y no habia antes?
- ¿ Qué razón ha producido el cambio?
- ¿ Hay que tener cuidado con algo?
- ¿ Hay algo especialmente destacable?

Para realizar este commit perfecto, se debe de realizar con "git commit" ya que abre el editor para poder escribir lo que quieras.

Cuando se abre el editor escriba el asunto principal, dé dos satos de línea (return) y escriba los detalles pertientes que respondan a las preguntas antes descritas.

## git log ##

    git log

Este comando es el que permite ver información de las confirmaciones realizadas anteriores. Ayudando a realizar un seguimiento de lo que se ha realizado en el repositorio o proyecto.

En esta información se puede ver el mensaje del "commit" que se realizó, la persona que lo realizó y a que fecha y hora se hizo.

    git log --oneline

Con la opción "--online" te da la información de cada confirmación en un línea por lo que cuando hay muchos puede ser una gran alternativa

    git log -n2

Con la opción "-n2" te muestra la confirmación indicada donde 1 es para la última confirmación, 2 para la anterior y así sucesivamente.

## git help ##

    git --help

Como se ha comentado anteriormente, se puede utilizar este comando para ver todas las opciones que tiene Git.

Si deseas ver la ayuda de cualquier comando en concreto, también lo puedes hacer escribiendo el comando y poniendo el "--help" al final.

    git add --help
    git commit --help
    ...

## git diff ##

    git diff

El comando general, te indica todas las diferencias que hay en todo el proyecto en este momento con lo confirmado anteriormente.

    git diff archivo
    git diff ruta_archivo

Este comando te indica la diferencias que hay en el archivo indicado.

    git diff HEAD

Con la opción "HEAD" te indica las difrencias que hay en la última confirmación (commit).

## git tag ##
A parte de confirmar los cambios, se pueden añadir etiquetas a esas confirmaciones para indicarle algún aspecto que quieras controlar y despues visualizar. Por ejemplo, puedes indicar las versiones de cada confirmación.

    git tag

El comando general te visualiza todas las etiquetas que tienes en el proyecto en orden alfabetico.

    git tag -l 'patrón'

De esta forma te lista las etiquetas que concuerden con el patrón indicado entre comillas.

    git tag -a my_tag -m 'message'

Este comando te crea una etiqueta anotada y le indicas un mensaje a esa etiqueta. Si no se le incorpora el parámetro "-m" con su mensaje, se abrirá el editor para que lo escribas.

    git tag -a my_tag checksum_commit

Si se te ha olvidado poner alguna etiqueta en alguna confirmación o te has dado cuenta que quieres poner etiquetas en un proyecto ya avanzado, utilizando este comando te permite poner una etiqueta a una confirmación con el checksum correspondiente.

No hace falta porner todo el checksum, con parte de él es suficiente. Por ejemplo, parte del comienzo.

Para ver los checksum de las confirmaciones puedes utilizar "git log" o "git log oneline".

***
***NOTA***

Las etiquetas no se suben al repositorio remoto por lo que hay que forzarlas para subir.

Puedes ver la opción en el tema 3_Colaboración - 2_ramas
***

## git checkout ##
El comando git checkout sirve para varias cosas, entre ellas cambiar de rama de trabajo (eso se ve en el tema 3_Colaboración - 2_ramas) pero en local te puede servir para cambiar entre confirmaciones. Por ejemplo cambiar de una etiqueta a otra.

        get checkout my_tag

Este comando, dentro de la misma rama, te pasa de una confirmación a otra que tenga el nombre de la etiqueta indicada.

## git stash ##
Si estás a mitad de un trabajo y necesitas cambiar de rama o hacer modificaciones en otro archivo y no quieres confirmar los cambios que tienes a mitad, ejecutas el siguiente comando:

    git stash

Este comando deja en pausa los cambios que estabas realizando y los guarda para poder volver despues a ellos y seguir trabajando.

Lo puedes comprobar realizando un "git status" antes de hacer el "stash" y despues de hacerlo. Comprobaras que antes de hacerlo tienes cambios pendientes y cuando ejecutas el comando "git stash", al volver a ejecutar "git status" ya no tienes nada por confirmar.

Puedes crear tantos "stash" como quieras. Para listarlos se utilizará:

    git stash list

Para volver a un stash guardado:

    git stash apply

De esta forma, pondrá en marcha el "stash" guardado en último lugar.

Si deseas recuperar uno en concreto:

    git stash apply nombre_stash (Ej: stash#{2})

Tanto con "git stash apply" como con "git stash apply nombre_stash" recuperaras la información que estabas modificando anteriormente para seguir trabajando en él.

Si además quieres recuperar los archivos modificados despues del "stash" deberás de ejecutarlo con la opción "--index"

    git stash apply --index

Si deseas borrar un "stash" guardado:

    git stash drop nombre_stash

Si deseas más información al respecto puedes ir a la página oficial de [Git](https://git-scm.com/)


