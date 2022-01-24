# Editar el Archivo Config

## _¿Qué es el Archivo config.txt?_

Cuando compramos un ordenador normal, estamos acostumbrados a configurar algunas cosas desde la BIOS del mismo. Esta BIOS es un pequeño programa que nos permite modificar diversos parámetros para controlar la velocidad del procesador, de la memoria RAM o de la gestión de los periféricos. Pero esto no lo tenemos en la Raspberry Pi. En su lugar tenemos un archivo de texto llamado config.txt donde tenemos un montón de variables para poder configurar varias cosas de nuestra Raspberry Pi, incluido el comportamiento del hardware.

Este archivo config.txt se encuentra en la partición boot de nuestra tarjeta microSD junto con un montón de archivos que forman parte del firmware de la Raspberry Pi.

## _Cómo Editar el Archivo config.txt_

Si el sistema operativo que tenemos en la Raspberry Pi está basado en Raspbian, podemos modificar fácilmente el archivo config.txt usando el editor de archivos nano. Esto lo podemos hacer con el siguiente comando en la terminal.

```sh
sudo nano /boot/config.txt
```

Al principio del comando hemos puesto sudo, ya que este archivo es un archivo protegido y necesitamos permisos especiales para poder editarlo. Si no ponemos sudo podremos abrirlo, pero no editarlo ya que no tendremos esos permisos especiales.

También podemos editar ese archivo con cualquier editor de textos que tengamos en nuestro entorno gráfico, como puede ser Leafpad. Aun así, recuerda iniciar el programa como administrador, ya que, si no solo podrás abrir el archivo, pero no modificarlo. El archivo se encuentra dentro de la carpeta boot del directorio raíz del sistema operativo.

Si queremos modificar el archivo config.txt en otros sistemas basados en JeOS, como puede ser LibreELEC, primero tenemos que montar la partición boot para poder acceder a ella. Esto lo hacemos ejecutando el siguiente comando en la terminal.

```sh
mount -o remount,rw /flash
```

Ahora que ya podemos escribir en la partición boot, ya podemos abrir el archivo config.txt con nano y empezar a editarlo. En LibreELEC la partición boot se llama flash, por lo que el comando para modificar config.txt cambia un poco.

```sh
nano /flash/config.txt
```

Si no tenemos cerca la Raspberry Pi, siempre podemos realizar una conexión remota desde otro ordenador para poder editar el archivo config.txt. Los cambios que realicemos no se aplicarán hasta que no reiniciemos la Raspberry Pi. Si todos los cambios que hemos hecho son correctos, la Raspberry Pi se reiniciara correctamente y podremos seguir usándola sin problemas.

Como última opción podemos poner la tarjeta microSD en otro ordenador y editar el archivo config.txt de la partición desde el mismo. Si usamos Windows recomiendo usar el editor de textos Notepad++, ya que el formato txt de Linux no es completamente igual que el de Windows y si no tienes la última versión de Windows 10, es posible que los saltos de línea no se vean correctamente.

## _Cosas a Tener en Cuenta Antes de Modificar el Archivo config.txt_

## Copias de Seguridad

Es posible que modificando alguna línea del archivo config.txt rompamos algo de forma que algo que antes funcionaba ya no funcione, o peor aún, que nada funcione. Si nos pasa esto y tenemos una copia de seguridad del archivo anterior, podemos restaurarla volviendo a lo que teníamos antes sin muchos problemas.

Para crear una copia de seguridad podemos copiar el archivo config.txt donde nos apetezca, aunque mi consejo es que creemos una copia junto al original en la partición boot. Para ello, vamos a usar el siguiente comando en la terminal antes de cualquier modificación de config.txt.

```sh
sudo cp -f /boot/config.txt /boot/config.txt.bak
```

Con esto lo que haremos será crear un archivo llamando config.txt.bak antes de realizar cualquier cambio en el archivo original. Si, por lo que sea, la Raspberry Pi no inicia o si inicia, no lo hace correctamente, podemos borrar el archivo config.txt y renombrar el archivo config.txt.bak a config.txt para recuperar la configuración anterior y que todo vuelva a funcionar como antes.

## Comentarios

También podemos introducir comentarios en config.txt poniendo una # almohadilla delante de lo que queremos comentar en esa línea. Todo lo que este escrito después de la almohadilla será ignorado por la Raspberry Pi. Esto nos puede ser útil para dejar los parámetros originales del archivo config.txt y saber lo que hemos modificado, además de poder explicar por qué lo hemos modificado o añadido.

## Filtros de Configuración

| Filtro | Modelos aplicables |
| ------ | ------ |
| [all]	| Todos los modelos |
| [pi1]	| Modelo A, Modelo B, Compute Module |
| [pi2]	| Modelo 2B (Con procesador BCM2836 o BCM2837) |
| [pi3]	| Modelo 3B, Modelo 3B+, Modelo 3A+, Compute Module 3 |
| [pi3+] | Modelo 3A+, Modelo 3B+ |
| [pi4]	| Modelo 4B |
| [pi0]	| Modelo Zero, Modelo Zero W, Modelo Zero WH |
| [pi0w] | Modelo Zero W, Modelo Zero WH |

## _Parámetros del archivo config.txt_

## Memoria

Los parámetros de este apartado sirven para distribuir la memoria RAM de la Raspberry Pi entre los procesos del procesador y la tarjeta gráfica. Dependiendo de la memoria RAM con la que contemos en la Raspberry Pi podemos darle desde 16MB hasta el total de la memoria RAM menos 64MB. En el caso de la Raspberry Pi 4, aunque contamos con placas con 2GB y 4GB, el máximo que podemos usar para la tarjeta gráfica es de 944MB.

De todas formas, a partir de 512MB de memoria de vídeo no notaremos ninguna mejora, por lo que no es necesario pasar de esos 512MB.

```sh
gpu_mem=128
# Asigna 128MB de memoria RAM para la tarjeta gráfica, podemos cambiar ese 128 por el
# número que queramos desde 16 hasta 944. Se recomienda hacerlo en múltiplos de 16

gpu_mem_256=64
# Asigna 64MB de RAM a la tarjeta gráfica si la Raspberry Pi tiene 256MB de memoria RAM.
# Si existe el parámetro gpu_mem, se ignorará

gpu_mem_512=128
# Asigna 128MB de RAM a la tarjeta gráfica si la Raspberry Pi tiene 512MB de memoria RAM.
# Si existe el parámetro gpu_mem, se ignorará

gpu_mem_1024=256
# Asigna 256MB de RAM a la tarjeta gráfica si la Raspberry Pi tiene 1024MB de memoria RAM.
# Si existe el parámetro gpu_mem, se ignorará
```

## Licencias de Codecs de Vídeo

Con una Raspberry Pi anterior a la Raspberry Pi 4 podríamos optar por adquirir una licencia para decodificar diferentes formatos de vídeo con la tarjeta gráfica y así obtener un mejor rendimiento. Esto lo activábamos comprando una licencia en la Raspberry Pi Swag, la cual estaba asociada a nuestra Raspberry Pi.

A partir de la Raspberry Pi 4 la CPU se encarga de hacer la decodificación de los vídeos, por lo que no es necesaria dicha licencia para poder verlos, por lo que no es necesario añadir nada al archivo config.txt para reproducir toda nuestra colección de vídeos con VLC.

En el caso de tener una de estas licencias, podemos añadirlas de la siguiente manera en el archivo config.txt, pero recuerda que esa licencia estará asociada a una Raspberry Pi, por lo que tendremos que adquirir varias licencias para usar en el caso de que tengamos más de una Raspberry Pi.

```sh
decode_MPG2=0x12345678
# Sirve para decodificar archivos en formato MPEG2.
# 0x12345678 representa la clave de nuestra Raspberry Pi

decode_WVC1=0x12345678
# Sirve para decodificar archivos en formato VC1.
# 0x12345678 representa la clave de nuestra Raspberry Pi
```

## Vídeo / Pantalla

Quizás una de las secciones más amplias del archivo config.txt, ya que cada uno usa la Raspberry Pi enchufada en algún aparato diferente, y tenemos que hacer que funcione en todos, sin excepción. Desde televisores antiguos conectando la Raspberry Pi con una conexión RCA hasta usando el puerto GPIO, tenemos muchas posibilidades. Aquí voy a explicaros las que más uso yo, aun así, si no encontráis lo que buscáis, siempre podéis mirar en la documentación de la Fundación Raspberry Pi.

Para empezar, vamos a ver las opciones que tenemos disponibles a la hora de conectar una Raspberry Pi a una televisión mediante un cable RCA. Este cable se conecta al minijack de la Raspberry Pi y es muy útil para televisores antiguos que no tienen HDMI.

Para empezar, vamos a hablar de la Raspberry Pi 4. Por defecto esta viene con la salida RCA desactivada debido al funcionamiento que tiene esta. Al activarla, debido a la sincronización de algunos de los relojes de la Raspberry Pi 4, el rendimiento de esta baja. Aun así, si queremos activarla, podemos hacerlo con el siguiente parámetro.

```sh
enable_tvout=1
```

Ahora que todo está funcionando, vamos a ver diferentes parámetros y los valores que podemos darle para configurar la salida RCA para nuestro televisor.

```sh
sdtv_mode=18
# Configura el tipo de señal que vamos a mandarle a la televisión. Cambiando el número
# podemos elegir que tipo de señal vamos a mandar a la televisión.
# 0 para NTSC
# 1 para la versión japonesa de NTSC
# 2 para PAL
# 3 para la versión brasileña de PAL
# 16 para NTSC progresivo
# 18 para PAL progresivo

sdtv_aspect=3
# Cambia la relación de aspecto o proporción de la imagen. Cambiando el número podemos
# elegir la propoción que vamos a usar en la televisión.
# 1 para 4:3
# 2 para 14:9
# 3 para 16:9
```

Ahora que hemos visto los parámetros más importantes de la salida RCA, vamos a ver unos cuantos parámetros de la salida HDMI. Como he comentado antes, hay un montón de parámetros que quizás te puedan hacer falta, pero como suele pasar muy rara vez, voy a comentar los que más se usan y si no encuentras lo que buscas, puedes mirar en la documentación de la Fundación Raspberry Pi.

```sh
hdmi_safe=1
# Configura la salida HDMI a unos valores seguros que suelen funcionar casi siempre. Si no 
# tienes imagen en tu monitor o televisión con una Raspberry Pi, puedes usar este
# parámetro para probar una configuración segura que debería funcionar.

config_hdmi_boost=5
# Sirve para configurar la potencia de la señal que manda el puerto HDMI por el cable.
# Cuanto más largo es el cable y de peor calidad es, más potencia de señal necesita. Si es
# demasiada potencia también puede haber problemas, por lo que solo es recomendado
# cambiarla cuando no lleva bien la imagen y hay interferencias. Los valores van de 0 a 11

hdmi_group=0
# Define el grupo al que pertenece el aparato al que vamos a enchufar la Raspberry Pi por
# HDMI
# 0 para detección automática
# 1 para el grupo CEA, normalmente usado por televisiones
# 2 para el grupo DMT, normalmente usado por monitores

hdmi_mode=0
# Define la resolución y frecuencia de refresco de la imagen. Dependiendo del valor
# de hdmi_group el hdmi_mode fija una resolución y frecuencia de refresco diferente.
# Puedes consultar los valores en
# https://www.raspberrypi.org/documentation/configuration/config-txt/video.md
```

Para terminar, vamos a hablar del overscan. Esto se inventó en las señales analógicas de televisión, poniendo un marco negro alrededor de la imagen, que se ajustaba de forma invisible para los usuarios de forma que no lo veíamos. En la era digital este marco ya no es necesario, pero algunos televisores lo eliminan de forma automática, redimensionando la imagen y perdiendo parte de la imagen por el camino.

Cuando instalamos un sistema operativo en la Raspberry Pi, este overscan viene por defecto habilitado para que se muestre el marco negro en la pantalla. Si lo vemos, podemos deshabilitarlo desde el archivo config.txt. Además, también podemos ajustar cuantos pixeles se usan por cada lado del borde de la pantalla, si nuestra televisión realiza un overscan diferente al estándar.

```sh
disable_overscan=1
# Deshabilita el marco que se crea por el overscan producido por algunos televisores.
# Por defecto esta línea esta comentada

overscan_left=24
overscan_right=24
overscan_top=24
overscan_bottom=24
# Con el número de estos parámetros indicamos de cuantos pixeles tiene que ser el marco de
# cada lateral de la televisión. Estos parámetros se usan si la televisión no aplica un
# overscan estándar.
# overscan_left indica de cuantos pixeles tiene que ser el marco de la izquierda.
# overscan_right indica de cuantos pixeles tiene que ser el marco de la derecha.
# overscan_top indica de cuantos pixeles tiene que ser el marco superior.
# overscan_bottom indica de cuantos pixeles tiene que ser el marco inferior.
```

## Audio

Para configurar aspectos del sonido podemos usar un par de parámetros que tenemos disponibles. De todas formas, la mayoría de las veces, si tenemos problemas con el sonido, estos problemas son a causa de los drivers y tenemos que solucionarlos de otra forma.

```sh
disable_audio_dither=1
# Por defecto esta opción viene deshabilitada. Se recomienda habilitarla cuando se escucha
# un leve ruido de fondo cuando usamos la entrada de minijack para el sonido.

hdmi_drive=2
# Sirve para forzar el formato de salida de la salida HDMI.
# 1 usa el formato DVI (sin sonido)
# 2 usa el formato HDMI (con sonido)
```

## Overclocking

En este apartado vamos a ver los parámetros que podemos usar en el archivo config.txt para mejorar el rendimiento de la Raspberry Pi. El problema de esto es que, si ponemos valores demasiado elevados en los parámetros conseguiremos que el funcionamiento de la Raspberry Pi sea inestable, causando cuelgues aleatorios. Una forma de evitar esos cuelgues es con una buena refrigeración, haciendo que baje la temperatura del procesador y sacando toda la potencia a la Raspberry Pi.

Dependiendo de la Raspberry Pi que tengamos, podemos aplicar unos valores máximos u otros a los parámetros de overclock. Si estos valores no son correctos, la Raspberry Pi no arrancará. En este caso también os pondré solo los parámetros más usados, aunque podéis consultarlos todos en la sección de overclocking de la Fundación Raspberry Pi.

```sh
over_voltage=6
# Indica el voltaje al que trabajará el procesador. Por defecto es en la Raspberry
# Pi 4, lo que significa 1,35V y 0 en las demás Raspberry Pi, lo que equivale
# a 1,2V. Cada valor más que le pongamos subirá el voltaje 0,25V.

force_turbo=1
# Poniendo 1 en este parámetro, forzamos a que los núcleos del procesador estén
# funcionando siempre a máxima velocidad, independientemente de la carga de 
# trabajo que tengan. Por defecto su valor es 0.

arm_freq=2147
# Define la frecuencia máxima a la que puede trabajar el procesador. Dependiendo
# de la Raspberry Pi, esta frecuencia es diferente.
#
# Modelo de Raspberry Pi   Freq. base   Freq. máxima
# Raspberry Pi Zero           1000          ????
# Raspberry Pi 1               700           900
# Raspberry Pi 2B              900          1000
# Raspberry Pi 3B             1200          1400
# Raspberry Pi 3B+/3A+        1400          1550
# Raspberry Pi 4B             1500          2147
#
# También depende de la propia Raspberry Pi y de la refrigeración que tengamos puesta
# en ella. Hay Raspberry Pi que pueden alcanzar valores más altos que los indicados
# y otras en las que tenemos que usar valores más bajos.

gpu_freq=700
# Este parámetro define la velocidad máxima a la que funcionará nuestra tarjeta
# grafica. En este caso también dependemos del modelo de Raspberry Pi que tengamos
# para definir ese valor.
#
# Modelo de Raspberry Pi   Freq. base   Freq. máxima
# Raspberry Pi Zero            250            500
# Raspberry Pi 1               200            400
# Raspberry Pi 2B              200            500
# Raspberry Pi 3B              250            500
# Raspberry Pi 3B+/3A+         250            500
# Raspberry Pi 4B              400            700
#
# Aquí también dependemos de la Raspberry Pi que nos haya tocado y la refrigeración
# que le hayamos puesto. Cuanto mejor sea la Raspberry Pi y mejor refrigeración 
# tengamos, mayores valores podemos ponerle al parámetro.
```

## Varios

Evidentemente, hay muchos más parámetros de los que estamos viendo en este articulo. Para terminar os voy a dejar un parámetro para poder ocultar los avisos de temperatura y falta de voltaje, aunque no recomiendo hacer eso por seguridad y porque si no hacemos caso de esos avisos podemos cargarnos nuestra Raspberry Pi.

```sh
avoid_warnings=1
# Con este parámetro ocultamos los avisos de bajo voltaje en la Raspberry Pi.
# 1 sirve para ocultar los avisos.
# 2 sirve para ocultar los avisos, y además para usar frecuencias de reloj
# altas si son necesarias.
```

Para corregir el audio por HDMI hay que descomentar la siguiente línea.

```sh
hdmi_drive=2
```

Y descomentando la siguiente línea se permite que la Raspberry envía señal HDMI aunque no tenga un Monitor/TV conectado, permitiendo que siempre inicie.

```sh
hdmi_force_hotplug=1 
```