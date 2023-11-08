# Configuración global de git #
Antes de inicializar git en cualquier proyecto, hay que realizar la configuración global de git para que esos datos se recojan en cualquier proyecto nuevo.

Los parámetros más relevantes de la configuración global son:
- Nombre
- Email
- Configuración de rama principal

Ahora vermos varios comandos de git para saber que configuración hay en ese momento y como cambiar dicha configuración a la que nosotros querramos.

También se puede cambiar la configuración local de cada proyecto aunque no se suele hacer a no ser que se quiera realizar alguna configuración en particular.

## git config ##
Comando para visualizar las opciones que puedes configurar

## git config --list --global ##
Visualizas la configuración global de git

## git config --global user.name "nombre" ##
Comando para cambiar el nombre del usuario en la configuración global.

El nombre siempre tiene que estar entre comillas.

    git config --global user.name "jamsdev"

## git config --global user.email "email" ##
Comando para cambiar el email del usuario en la configuración global.

El email siempre tiene que estar entre comillas.

    git config --globla user.email "email@email.com"

## git config --global init.defaultBranch nombre_rama ##
Comando para cambiar la rama por defecto (Master) por otra con otro nombre. Algunos nombres que se utilizan son "master", "main" o "developer".

En github se utiliza la rama principal "main" por lo que si queremos podemos utilizar este comando para que siempre nos salga la rama principal como "main" en vez de como "master".

    git config --global init.defaultBranch main




