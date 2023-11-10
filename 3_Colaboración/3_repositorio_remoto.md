# Trabajar con un repositorio remoto #

## git fetch ##

    git fetch

Este comando comunica con un repositorio remoto y obtiene toda la información que se encuentra en ese repositorio que no está en el tuyo actual y la almacena en tu repositorio local.

Si has integrado una url remota con "git remote add nombre_alias url_remote", podrás realizar "fetch" de la siguiente forma:

    git fetch name_alias

## git merge ##
Este comando combina el código de una rama/repositorio_remoto con la rama/repositorio_local en la que te encuentras.

    git merge rama_a_combinar

Combinará el código de la rama actual (activa) con la rama que has indicado (rama_a_combinar)

## git pull ##

    git pull

Recibe la información del repositorio remoto al repositorio local.

Cuando realizas un git pull, internamente realiza los comandos "git fetch" y "git merge" automaticamente.

## git push ##

    git push

Envía la información del repositorio local al repositorio remoto cuando está configurado.

    git push url_remote name_branch

o

    git push name_alias name_branch

Envío la información que hay en la rama "name_branch" al repositorio remoto "url_remote" o la ubicación remota del alias "name_alias" indicado

    git push --set-upstream origin my-branch

o

    git push -u origin my-branch

Si no existe la rama en el repositorio remoto, con esta opción "-u" o "--set-upstream", fuerza y configura las ramas para subirlas al respositorio remoto y poder trabajar con ellas en un futuro más facilmente.

Cuando realizas un git push, internamente realiza los comandos "git fetch" y "git merge" automaticamente.

### Subir etiquetas al repositorio remoto ###

Las etiquetas que pones en las confirmaciones del código, no se añaden al repositorio remoto por lo que hay que forzarls en caso de que quieras subirlas.

    git push origin --tags

Con este comando subes todas las etiquetas que no existen en él. Si quieres solo enviar una, puedes hacerlo de la siguiente forma:

    git push origin my_tag


## git remote ##

    git remote

o

    git remote -v

Con estos comandos puedes ver si hay algún repositorio remoto dentro de nuestro proyecto.

    git remote add name_alias url_remote

Con este comando añades la "url_remote" al nombre"name_alias" para que cada vez que hagas "git push" o "git fetch" no le tengas que indicar la url completa, solo con indicarle el "name_alias" ya hará referencia a la url.