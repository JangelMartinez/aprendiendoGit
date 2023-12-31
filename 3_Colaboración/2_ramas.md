# Ramas Git #
Las ramas en git ayudan a realizar cambios en una característica existente, arreglar bugs o hotfix o crear una nueva característica.

Cuando se crea un rama, recoge todo el código existente hasta ese momento y puedes cambiar ese código sin que la rama principal se vea afectada. Es decir, es como crear un nuevo proyecto desde un código principal.

Una vez terminado el código en la rama nueva en la que se está trabajando, y haberlo verificado, se puede añadir a la rama principal, para que tenga las características nuevas programadas. De esta forma, nos libramos de que la rama principal tenga problemas al ir sobreescribiendose.

Los comandos principales para trabajar con ramas y actualizarlas son: "git branch", "git checkout" y "git merge"

## git branch ##

    git branch nombre_rama

Creas una rama nueva a partir de la rama en la que estás en ese momento. El código será el mismo.

    git branch --set-upstream-to origin/serverfix

o
    
    git branch -u origin/serverfix

Este comando ayuda a asignar una rama local a una remota. También se utiliza para cambiar la rama a la que haces seguimiento.

    git branch -m name_branch

Este comando te cambia el nombre de la rama donde estes.

En github, por ejemplo, la rama por defecto es "main" en cambio la rama por defecto de git es "master". Ejecutando "git branch -m main", la rama "master" local se convierte en la rama "main" para que así cuadre la rama local con la remota.

## git checkout ##

    git checkout nombre_rama

Este comando activa la rama insertada. No te dejará activar la rama si tienes cambios sin confirmar. Cuando cambias de rama, a no ser que hagas un "merge" no dispondras de los cambios efectuados en la rama anterior en caso de haber hecho cambios.

    git checkout -b nombre_rama

Este comando crea y activa la rama indicada.

    get checkout my_tag

Este comando, dentro de la misma rama, te pasa de una confirmación a otra que tenga el nombre de la etiqueta indicada.

## git merge ##

    git merge my-feature

Este comando indica que quieres juntar la rama "my-feature" a la rama en la que estás en este momento.

    git merge --ff-only my-feature

La opción "--ff-only" sirve para realizar una combinación de avance rápido. Aunque no es necesaria, es una buena práctica porque se produce un error si main ha cambiado.