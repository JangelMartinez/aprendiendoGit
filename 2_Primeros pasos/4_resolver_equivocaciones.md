# Resolver equivocaciones #
Git ofrece una alternativa que te permite realizar cambios en el historial o volver atrás para recuperar un archivo borrado por ejemplo.

## Rectificación de una confirmación --amend ##

    git commit --amend --no-edit

La opción "--amend" permite cambiar el historial, editar un mensaje de confirmación, agregar archivos que se habian dejado fuera de la confirmación por accidente o quitar archivos que se habian agregado por equivocación.

La opción "--no-edit" le indica a Git que realice el cambio sin cambiar el mensaje de confirmación.

## Recuperación de un archivo eliminado "git checkout" y "git reset" ##

    git checkout -- archivo

Este comando recuperaria un archivo eliminado.

Un ejemplo seria:

    git checkout -- index.html

En caso de que el archivo se haya eliminado con "git rm index.html" el comando "git checkout -- index.html" no funcionaria y habría que utilizar el comando "git reset".

    git reset HEAD index.html
    git checkout -- index.html

Git reset revierte la eliminación del archivo del almacenamiento provisional de Git agregandolo otra vez al indice.

Git checkout restauraria el fichero del indice.

## Reversión de una confirmación "git reset" y "git revert" ##

    git revert HEAD

o 

    git reset --hard HEAD^

Cualquiera de los dos comando anteriores sirven para revertir una confirmación.
