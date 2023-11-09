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



## git remote ##

    git remote

o

    git remote -v

Con estos comandos puedes ver si hay algún repositorio remoto dentro de nuestro proyecto.

    git remote add name_alias url_remote

Con este comando añades la "url_remote" al nombre"name_alias" para que cada vez que hagas "git push" o "git fetch" no le tengas que indicar la url completa, solo con indicarle el "name_alias" ya hará referencia a la url.