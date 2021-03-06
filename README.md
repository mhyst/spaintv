# tv
Script de bash para ver streaming de los canales de televisión de España.

## Diatriba previa

No es que quiera promocionar la televisión. De hecho lo mejor que puede hacerse es ignorarla y optar por otras ocupaciones en el tiempo libre. Cuando era joven veía la tele más de tres o cuatro horas al día, lo cual no es nada recomendable y deja el cerebro en un estado cuasi comatoso. Cuando decidí que no necesitaba la televisión en mi vida, tampoco me supuso un gran sacrificio. Es cuestión de costumbres más que una necesidad. Y las costumbres se pueden modificar. Naturalmente, cuando yo era pequeño había menos oferta de televisión, pero más calidad y abismalmente menos publicidad. Hoy la televisión tiene más publicidad que programación y dentro de la programación hay publicidad también. Es enteramente insoportable. No contentos con eso, pretenden que veamos más publicidad en la web por el mero hecho de querer acceder al streaming de un canal en el que ya hay publicidad de por sí. Y en ese afán recaudatorio, en el que por el mero hecho de ansiar ganar dinero se ha dejado atrás la decencia, la honradez, la vergüenza... y por supuesto la calidad de la programación; nos ponen mil trabas para poder ver unos minutos si acaso de la mierda que rezuma de sus emisiones. Puesto que ellos no dan facilidades para el libre acceso al streaming, he decidido hacerlo yo. 

## Objetivo

Ver la televisión de España en streaming en tu reproductor favorito. Así de simple. Por desgracia no se pueden ver todos los canales disponibles en antena, ya que no ha sido posible sustraer la url de streaming más que de unos cuantos. De todas formas, tanto los nombres de los canales como las urls de streaming se encuentran en el archivo de texto '/home/$USER/.local/tv.mhyst/tv.conf'. Este archivo puede ser editado para añadir o quitar canales al gusto de cada uno. Por supuesto, se pueden añadir canales de otros países o canales que vayan apareciendo. Yo iré manteniendo este archivo conforme vea que las URLs dejen de funcionar, no obstante, si alguien encuentra nuevos canales o se da cuenta de que uno no funciona antes que yo, puede hacer un pull request.

## Instalación

Para instalar el script simplemente habrá que copiar los archivos a una carpeta, modificar la variable PLAYER para indicar qué reproductor queremos utilizar para ver la tele; y copiar los archivos 'tv' y 'tvupdate' a /usr/local/bin o a cualquier carpeta que se encuentre añadida al PATH. La primera vez que ejecute el script se descargará el archivo de configuración automáticamente. 

## Novedades

- 13/07/2019: Nuevo script de actualización de canales 'tvupdate'. Este script se descarga el archivo de configuración de este repositorio, actualiza los canales y añade canales nuevos. El script respeta el orden en que se hayan puesto los canales y hace una copia de seguridad del original. Puede programarse su ejecución en el crontab de forma que se ejecute una vez al día, una vez a la semana, etc.

## Dependencias

Únicamente se requiere un reproductor.

## Modo de empleo

El script puede llamarse sin argumentos, en cuyo caso se mostrará el menú de canales, en el que una vez indicado el número del canal que queremos se procederá a reproducir. Pueden agregarse argumentos en la llamada que se interpretarán como una cadena de búsqueda de canal. En ese caso se intentará buscar un canal que coincida. Es posible utilizar cadenas de búsquedas parciales. En caso de que más de un canal coincida, se reproducirá el primero en el orden numérico.

Ejemplos:

---

tv

tv paramount

tv 1

tv 24

tv la 2

tvupdate


---

Una vez estemos viendo el streaming de un canal podemos poner la ventana del terminal en primer plano (o usar alt+f2) para cambiar de canal. Se cerrará el reproductor actual antes de reproducir el nuevo canal.

> Nota: Para que esta última característica funcione, si su reproductor no es vlc o mpv, deberá modificar la línea 119 del script y sustituir donde pone vlc o mpv por el comando con el que se invoca su reproductor.

