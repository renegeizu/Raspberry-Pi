# Actualizar Raspberry Pi

## _Instrucciones para Actualizar con Raspbian_

Para comenzar, ingresa a la consola de comandos como un usuario principal de la placa y procede a introducir la siguiente línea: 

```sh
sudo apt-get –y update
```

Con este comando indicarás la solicitud de repositorios de tu placa, es decir, actualizar el contenido de las ofertas disponibles para ella. En esta línea se añade el “-y” para aplicar un “sí” como respuesta automática al momento de preguntar por actualizaciones.

Una vez que el contenido haya sido renovado, debes volver a introducir el comando de 

```sh
sudo apt-get –y update
```

y dejar que comience a actualizar a la última versión los programas.

La velocidad de este procedimiento dependerá de la calidad de conexión a Internet, por lo que se recomienda tener paciencia.

Al finalizar, escribe 

```sh
uname –r
```

en la consola de comandos para verificar el número de versión de kernel que se encuentra instalado.

A partir de este momento comenzarás a actualizar a la última versión tu placa de Raspberry Pi, lo cual lograrás introduciendo el comando de 

```sh
sudo rpi-update
```

De forma automática se mostrará en la pantalla el acceso a GitHub para estudiar el contenido disponible en el catálogo y así descargar/instalar las últimas versiones.

Cada una de estas cosas será almacenada en tu memoria interna. Al finalizar, solo necesitas reiniciar el pequeño computador para poder aplicar los cambios descargados.

Si lo deseas, puedes volver a introducir el comando de 

```sh
uname –r
```

para verificar la versión de Raspbian que has instalado.

## _Instrucciones para Actualizar con Linux_

Otra opción para mantener tu placa constantemente actualizada es mediante el terminal de Linux, de forma local o conectada directamente al escritorio.

Mediante los siguientes comandos y conectado a Internet, escribe las siguientes líneas:

Cada una debe comenzar por la frase “sudo apt”, seguido de la orden a realizar. En esta misma secuencia deberás ingresarlo.

```sh
sudo apt update
sudo apt dist-upgrade
sudo apt clean
sudo apt reboot
```

Al igual que en el método anterior, deberás reiniciar el dispositivo cuando finalices para aplicar los cambios instalados.