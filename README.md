# twic-dl

Script en Bash para descargar base de datos PGN desde [The week in Chess](https://theweekinchess.com/).

## Descripción
El script está escrito en Bash, que se conecta a la página [The week in chess](https://theweekinchess.com), todas las bases de datos públicada hasta el momento.

Junto con el script viene un archivo llamado 'last', que contiene la ultima base de datos que se descargó, la primer base de datos publicada en la página es la 920, por lo que viene por default en el archivo 'last'. 

El script determina cual es la última base de datos publicada y descarga desde la 920 hasta la actual, en todo caso que se quiera descargar desde una base de datos específica, edita el archivo 'last'.

El script crea una carpeta `/tmp`, donde se descargan los archivos .zip de las bases de datos, también crea una carpeta pgn, donde se descomprimen los archivos `.zip`. al final del proceso junta todos los arhivos PGN decomprimidos en una base de datos global. Al final de proceso se elimina la carpeta `/tmp` y opcionalmente la carpeta `/pgn` (mediante la opcion `-d | --delete`).

## Dependencias

Librerias necearias para ejecutar el script:

* curl
* unzip

## Modo de uso

Para ver el modo de uso de script usa el comando:

```
twic-dl --help

Usage: twic-dl [ -d | --delete]
               [ -h | --help] dest

        dest                 Carpeta de destino
        -h, --help           Mostrar la ayuda del comando
        -d, --delete         Eliminar los archivos PGN descargados
```

## Ejemplos

Decargar los archivos PGN en la carpeta home del usuario:
```
twic-dl ~
```

Descargar los archivos PGN en la carpeta home del usuario, pero borrando estos archivos el final del proceso 
```
twic-dl -d ~
```

## Autor

**Javier Reta** - *reivaj79mx@gmail.com*

>Basado en el script de **imcgeoch** - [twic_update](https://github.com/imcgeoch/twic_update) 
