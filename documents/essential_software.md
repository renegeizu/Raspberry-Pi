# Mejores Programas para Raspberry Pi

## _Editar Imágenes en el RPi_

## GIMP, el Editor de Fotos OpenSopuce

Interfaz principal GIMPGIMP es el Photoshop de los sistemas Linux. Este es uno de los programas de edición fotográfica más completos que podemos encontrar. Un software totalmente gratuito y de código abierto que, por supuesto, no podía faltar en el micro-ordenador. Es cierto que es un programa bastante pesado y que, dada la potencia del Raspberry Pi, puede que tengamos algunos problemas para poder usarlo con soltura. Pero funcionar funciona, y satisfacerá todas las necesidades de edición y retoque que podamos tener.

Este programa suele venir instalado en Raspberry Pi OS, pero, en caso de no tenerlo, podemos instalarlo con el siguiente comando:

```sh
sudo apt install gimp
```

## MyPaint, Software para Pintar

Si lo que estamos buscando es un software especializado en pintura artística, entonces una alternativa mucho más enfocada a esta finalidad que GIMP es MyPaint. Este programa, gratuito y de código abierto, está mucho más cerca de Corel Painter o Krita que de Photoshop. En él podemos encontrar una gran cantidad de pinceles, ajustes y opciones de personalización de capas para poder dar rienda suelta a nuestra imaginación.

Podemos instalar este programa gratis ejecutando en la consola:

```sh
sudo apt install mypaint
```

## Digikam, para Editar Fotos RAM

Si lo que estamos buscando es un software que nos permita organizar todas nuestras fotografías, y además retocar y mejorar todo tipo de fotos en formato RAW, entonces una de las opciones que podemos elegir es Digikam. Este software nos permitirá administrar grandes bibliotecas de fotos, y procesar todo tipo de imágenes para mejorar su acabado y optimizarlas. Eso sí, aunque puede funcionar en arquitecturas ARM, si queremos usarlo en el Raspberry Pi es necesario que nuestro modelo tenga, al menos 4 GB de memoria RAM. De lo contrario, tendremos problemas.

Podemos instalar este software ejecutando el siguiente comando en terminal:

```sh
sudo apt install digikam
```

## _Convierte el Raspberry Pi en un Reproductor Multimedia_

## VLC, el Reproductor Multimedia por Defecto

VLC Media Player es, sin duda, uno de los mejores reproductores de vídeo que podemos encontrar, literalmente, para cualquier sistema operativo. Entre sus principales puntos fuertes cabe destacar que se trata de un software gratuito y de código abierto, y que es capaz de reproducir cualquier formato sin necesidad de instalar y configurar codecs. Si vamos a usar el Raspberry Pi para ver vídeos, sin duda es un programa must-have que no debe faltar en nuestra distro.

Para instalar este reproductor, debemos ejecutar el siguiente comando en una consola:

```sh
sudo apt install vlc
```

## QMMP, un Reproductor de Música Especializado

Aunque VLC puede reproducir también música, la verdad es que, en este sentido, está algo limitado en cuanto a usabilidad. Por ello, es mejor contar con otro reproductor de música más especializado, como es el caso de QMMP. Este software es compatible con los principales formatos de audio (MP3, FLAC, Ogg FLAC, Ogg Vorbis, WAV, etc) y cuenta con un ecualizador para ajustar el tipo de reproducción y con efectos visuales muy curiosos para ver mientras escuchamos música.

Podemos instalar este programa con el comando:

```sh
sudo apt install qmmp
```

## Kodi, un Centro Multimedia Completo

La verdad es que Kodi no necesita presentación. Este es el programa más conocido para convertir cualquier ordenador o dispositivo en un completo centro multimedia desde el que vamos a poder centralizar todos los archivos multimedia (vídeos, música, fotos, etc) en un solo lugar. Además, nos permite reproductor contenido en streaming desde Internet y es compatible con plugins que nos permiten darle una mayor utilidad al software.

Podemos instalar Kodi desde los repositorios oficiales ejecutando:

```sh
sudo apt install kodi
```

## _Jugar en el Raspberry Pi_

## DosBox, para Juegos Retro de MS-DOS

Si lo nuestro son los juegos de los años 80 y principios de los 90, gracias a DosBox vamos a poder revivir todos aquellos momentos. Este software nos permite emular un sistema MS-DOS completo sobre el cual vamos a poder ejecutar cualquier tipo de programa o juego de aquel entonces.

Podemos instalar este software con el comando:

```sh
sudo apt install dosbox
```

## RetroArch, un Completo Centro de Emuladores

Y si lo que nos gustan son los juegos de consolas retro, también podemos usar RetroArch para convertir nuestro Raspberry Pi en una retro-consola. Este software nos va a permitir emular, sin complicaciones, todo tipo de juegos de consola, desde las clásicas, como la NES, SNES o la Game Boy, hasta algunas más avanzadas, como la GameCube, e incluso la PlayStation 1.

La mejor forma de instalar este software en el Raspberry Pi es a través de snapd con los siguientes comandos:

```sh
sudo apt install snapd 
sudo reboot 
sudo snap install retroarch
```

## Steam Link, los Juegos de PC en Cualquier Lugar

Es cierto que no vamos a poder ejecutar juegos triple A en este micro-ordenador, tanto por las limitaciones del hardware, como por no poder instalar Windows. Sin embargo, lo que sí vamos a poder hacer es instalar Steam Link de manera que podamos conectarlo a la tele y usarlo como un dispositivo de streaming para jugar a los juegos de nuestro ordenador de forma remota y sin problemas.

Podemos instalar esta app ejecutando:

```sh
sudo apt install steamlink
```

## _Programas para Descargar Archivos_

## Deluge, Cliente Torrent muy Ligero y Sencillo

Deluge es un cliente de descargas torrent que nos va a permitir descargar fácilmente todo tipo de archivos de Internet a través de las redes P2P. Gracias a este programa vamos a poder convertir el micro-ordenador en un completo servidor de archivos desde el que podremos bajar todo tipo de datos de Internet, e incluso usarlo para poder acceder a nuestros archivos de forma remota y segura.

Podemos instalar este programa ejecutando:

```sh
sudo apt install deluged deluge-console python-mako deluge-web
```

## Transmission, Otro Excelente Cliente Torrent

Transmission es una alternativa a Deluge. A grandes rasgos, ambos programas sirven para lo mismo: para bajar archivos de la red torrent. Y, en cuanto a funciones y rendimiento, son muy parecidos. Así, cada usuario puede elegir el que más les guste, el que mejor se adapte a sus necesidades.

Podemos instalar Transmission fácilmente instalando:

```sh
sudo apt install transmission
```

## _Edita Audio y Vídeo en la Raspberry Pi_

## Audacity, Edita Audio como un Profesional

Sin duda es uno de los mejores programas de edición de audio que podemos encontrar y que poco tienen que envidiar las aplicaciones más profesionales y de pago, ya que éste puede ser considerado como un estudio de grabación casero. Con esta aplicación es posible cortar, copiar, empalmar o mezclar todo tipo de sonido de forma conjunta. Además, incluye numerosos efectos como cambiar la velocidad o el tono de una grabación.

Es posible instalar Audacity mediante el siguiente código:

```sh
sudo apt install audacity 
```

## Kdenlive, Editor de Vídeos No-Lineal

Esta aplicación es un elemento fundamental para editar vídeos no lineales, ofreciendo un mayor control y precisión a la hora de elaborar proyectos que los editores convencionales y que también podemos instalar en nuestra Rasberry Pi. Cuenta con soporte para todos los formatos FFmeg, como son AVI, MOV, MPEG, FLV y XviD. Esto nos permite manejarlos sin necesidad de convertir o re-codificar nuestros vídeos o fragmentos.

Podemos instalar Kdenlive con el siguiente código:

```sh
sudo apt install kdenlive
```

## OpenShot, Editor de Vídeos para Novatos

Si Kdenlive es demasiado avanzado para nosotros, OpenShot es un editor de vídeo mucho más simple y completo enfocado a usuarios con poca experiencia y conocimientos en la materia. Esta herramienta nos permite añadir efectos y transiciones. Además, cuenta con opciones de multipista para el audio.

Es posible instalar OpenShot con el siguiente código:

```sh
sudo apt install openshot 
```

## _Otros Programas y Herramientas Imprescindibles_

## LibreOffice, para Abrir y Crear Todo Tipo de Documentos

Por supuesto, otro software que no podía faltar en nuestra distro es una suite ofimática. LibreOffice es una de las mejores alternativas que podemos encontrar a Office para sistemas Linux. Esta suite nos trae todo lo necesario para poder trabajar: un procesador de textos, una hoja de cálculo y un software para hacer presentaciones de diapositivas. Todo ello, por supuesto, manteniendo toda la compatibilidad con el software de Microsoft.

Podemos instalar LibreOffice en el Raspberry Pi con:

```sh
sudo apt install libreoffice
```

## Protege las Conexiones con OpenVPN

Si vamos a tener el Raspberry Pi conectado a Internet, o tenemos pensado conectarnos a él de forma remota, y queremos hacerlo de forma segura, un software al que podemos recurrir es a OpenVPN. Este programa, totalmente gratuito y OpenSource, nos permite establecer una conexión privada virtual entre el micro-ordenador y un servidor VPN conectado a la red de manera que la conexión viaje de punto a punto de forma segura y cifrada.

Podemos instalar este software fácilmente con el comando:

```sh
sudo apt install openvpn
```

## Synaptic Package Manager: Gestiona Mejor los Paquetes de Linux

Los usuarios que llevan tiempo ya en Linux consideran Synaptic uno de los programas esenciales para cualquier distro. Este software nos va a permitir ver todos los paquetes que tenemos instalados en la distro, conocer las dependencias de cualquiera de ellos, quitar paquetes o añadir nuevos a nuestra distribución. Todo ello sin comandos, desde una interfaz muy clara y sencilla de utilizar. Sin duda, es una de las herramientas esenciales para simplificar el trabajo con paquetes y programas de Linux, algo que, desde siempre, ha sido relativamente complicado.

Podemos instalar este software fácilmente ejecutando el siguiente comando en el terminal:

```sh
sudo apt install synaptic
```