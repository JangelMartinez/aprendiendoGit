# Trabajar en un repositorio vacío #

## Inicializar un directorio vacío ##

    mkdir Shared.git
    cd Shared.git
    git init --bare

Con estos comandos creamos una carpeta llamada Shared.git. Entramos en la carpeta e inicializamos git.

El nombre del directorio creado con la extensión .git es una buena practica para indicar que es un directorio compartido vacío.

    git symbolic-ref HEAD refs/heads/main

Con este comando indicamos que la rama principal va ser main.

***
***NOTA:***

*Este paso no habria que hacerlo en caso de que en la configuración global ya lo has puesto como predeterminado o vayas a utilizar otro nombre de rama diferente a la habitual.*
***

## Clonar el repositorio vacio en una carpeta de trabajo ##

    mkdir proyecto1
    cd proyecto1
    git clone ../Shared.git

Con estos comandos, creas una carpeta de trabajo y una vez dentro clonas la carpeta principal donde va a estar el código compartido.

Dentro de la carpeta se puede configurar el nombre y el email del usuario para cuando se hagan los "commit" se guarde la información correcta. Para eso habría que configurarlo de la siguiente forma:

    git config user.name "nombre"
    git config user.email "email@email.com"

También se tendrá que realizar el comando para cambiar la rama principal.

    git symbolic-ref HEAD refs/heads/main

## Clonar un repositorio remoto ##
Puedes clonar un repositorio remoto siempre y cuando ese repositorio sea público o tengas permisos para hacerlo.

    git clone url

Con este comando, en la ruta (path) de tu sistema local donde lo ejecutes, se creará una carpeta con el nombre del proyecto de la url. 

Además inicializa un directorio .git en su interior con toda la información de ese repositorio y saca una copia de trabajo de la última versión.

Si utilizas el siguiente comando:

    git clone url name_folder

En vez de crear la carpeta con el nombre del proyecto de la url, lo creará en la carpeta con el nombre que le has indicado "name_folder".

