# Inicialización de un proyecto nuevo con git #
Antes de inicializar un proyecto nuevo con git, hay que buscar y/o crear una ruta donde se va a trabajar.

Sea en windows, linux o mac, se debe de pensar en la ruta en la que quieras trabajar y crear dicha ruta:

Por ejemplo:

    windows - c:\aplicaciones
    linux o mac - user#~/aplicaciones 

Dentro de dicha ruta, iras creando carpetas por cada proyecto:

Por ejemplo:

    windows - c:\aplicaciones\proyecto1
    linux o mac - user#~/aplicaciones/proyecto1

Se tendra que acceder a la carpeta creada del proyecto en el que trabajaras e inicializarás git en el proyecto con el siguiente comando:

    git init

o

    git init -y

Dicho comando creará una carpeta oculta llamada .git donde se encuentran varias carpetas y archivos de configuración de git para ese proyecto en concreto.

    |-.git
        |-- config  (fichero)
        |-- description (fichero)
        |-- HEAD (fichero)
        |-- branches (directorio)
        |-- hooks (directorio)
        |-- info (directorio)
        |-- objects (directorio)
        |-- refs (directorio)

Dentro de la carpeta .git, en el fichero config, está la configuración local del proyecto. En este fichero tendrá por defecto algunos valores predefinidos. Otros, en cambio, si no existen los cogerá del archivo de configuración global como el nombre, email y rama configurada por defecto.

Otra opción para inicializar git con una rama determinada, es:

    git init --initial-branch=main

De esta forma, inicializas un proyecto con git y que tenga la rama inicial "main" en vez de "master" que viene por defecto.

En caso de querer cambiar dichos valores para ese proyecto en cuestión, se podrá configurar localmente con los siguientes comandos.

    NOTA: Dichos comandos solo funcionarán cuando estés en la ruta de un proyecto configurado con git.

## git config --list --local ##
Visualizas la configuración local git del proyecto. 

## git config --local user.name "nombre" ##
Comando para cambiar el nombre del usuario en la configuración local.

El nombre siempre tiene que estar entre comillas.

    git config --local user.name "jamsdev"

## git config --local user.email "email" ##
Comando para cambiar el email del usuario en la configuración local.

El email siempre tiene que estar entre comillas.

    git config --local user.email "email@email.com"

## Otros comandos ##

Como hemos comentado hay muchas más opciones de configuración y puedes verlas con el comando:

    git config


