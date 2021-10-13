---
title: "Instalación de Debian 11 en el equipo de trabajo"
date: 2021-10-09T13:30:39+03:00
draft: true
---
IES Gonzalo Nazareno
Administración de Sistemas Informáticos en Red
Instalación de Debian 11 en el equipo de trabajo

Autor: Antonio Castro Díaz

1.- Introducción

En está practica desarrollaremos la instalación de Debian 11 en nuestro equipo de trabajo.

Lo primero fue descargar la imagen ISO de Debian 11 de la página oficial para la arquitectura amd64.

Una vez descargada la imagen, bootearemos un USB utilizando el programa Rufus. Cuando tengamos preparado el USB, apagamos el equipo y lo volvemos a iniciar, pero esta vez entrando en la BIOS para entrar en el apartado BOOT para elegir el pendrive como primera opción, para que cuando arranque inicie el instalador de Debian 11.

El siguiente paso será guardar los cambios y salir de la BIOS. Cuando salgamos ya se arrancará el instalador.

2 Instalación

En cuanto se nos muestre el menú del instalador, seleccionaremos la opción de instalación gráfica e iremos eligiendo nuestras preferencias sobre idioma, ubicación y configuración del teclado. Daremos nombre a la máquina, crearemos la contraseña del superusuario y configuraremos el usuario normal.

Cuando acabemos la configuración de los usuarios pasaremos a configurar el Gestor de Volúmenes Lógicos (LVM) que sirve para poder gestionar el almacenamiento de nuestro equipo. En mi caso el equipo que utilizo solo va a tener instalado Debian 11 como sistema operativo, por lo que utilizare todo el disco. Como vamos a utilizar el equipo como servidor, lo haremos manual y crearemos una tabla de particiones al estar el disco vacío. Crearemos un grupo de volúmenes donde iremos añadiendo los volumenes logicos necesarios para la raíz, la swap y las carpetas var, tmp y home.
3 Configuración

Por ultimo,después de la instalación del sistema base, elegiremos el país para la réplica de Debian, el repositorio, etc.. Después, se ejecutará Tasksel y seleccionaremos los programas que instalar. Instalaremos el Entorno de escritorio Debian, las utilidades estandar y el SSH Server del sistema, que utilizaremos a lo largo del curso. Una vez seleccionados, continuaremos e instalaremos los programas.

Cuando finalice, se reiniciara el equipo y volveremos a entrar en la BIOS para dejar la configuración de arranque como la teníamos al principio.

En mi caso, el siguiente paso fue entrar en la pagina https://linux-hardware.org/ y crearemos una prueba con el siguiente comando:

sudo -E hw-probe -all -upload

El cual nos examinará si los drivers de nuestros componentes están funcionando correctamente.

En mi caso, los drivers de la tarjeta gráfica no estaban actualizados, los cuales actualice descargando los drivers desde la pagina oficial de la tarjeta gráfica. Con esto damos por finalizada la instalación.
