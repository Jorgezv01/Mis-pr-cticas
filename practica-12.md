# Práctica 12

<span style="font-size: 300%;">PROSTORAGE</span>

<span style="font-size: 300%;">ONLINE</span>

<span style="font-size: 300%;">Servidor Docker en wilson</span>

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2025-10/scaled-1680-/Ne2image.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2025-10/Ne2image.png)

## 1. Objetivo y resumen

Vamos a desplegar un servidor Docker en Wilson y configurar un apache guacamole

### 1.1. Requisitos

Requisitos necesarios para llevar a cabo la tarea: recursos de storage, necesidades de red, máquinas virtuales, instalación previa herramientas… etc

### 1.2. Torres con tareas implicadas

Vamos a necesitar el proxmox en wilson y una máquina desplegada

## 2. Documentación de las tareas

Vamos a desplegar un servidor Docker desde plantilla

[![Captura de pantalla 2026-06-04 132207.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-04-132207.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-04-132207.png)

A continuación, vamos a instalar los prerequisitos con el siguiente comando :"sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release"

[![Captura de pantalla 2026-06-04 140451.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-04-140451.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-04-140451.png)

Y para terminar la instalación, metemos el siguiente comando: "curl -fsSL https://get.docker.com -o get-docker.sh  
sudo sh get-docker.sh"

[![Captura de pantalla 2026-06-04 140539.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-04-140539.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-04-140539.png)

El siguiente paso es instalar un contenedor de apache guacamole. Vamos a crear un directorio para organizar los archivos de configuración de Guacamole con el siguiente comando: "mkdir -p ~/guacamole &amp; <span class="hljs-built_in">cd</span> ~/guacamole"

[![Captura de pantalla 2026-06-05 073800.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-073800.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-073800.png)

Una vez dentro, vamos a crear un archivo con el siguiente comando: "nano docker-compose.yml" y escribimos el siguiente contenido:

[![Captura de pantalla 2026-06-05 073943.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-073943.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-073943.png)

A continuación, levantamos el servicio: "docker compose up -d"

[![Captura de pantalla 2026-06-05 074054.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-074054.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-074054.png)

metemos la dirección IP de nuestro servidor y nos tiene que aparecer la siguiente página

[![Captura de pantalla 2026-06-05 074215.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-074215.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-074215.png)

configuramos la carpeta para poder acceder añadiéndole un usuario y una contraseña y ponemos también la ip del equipo al que queremos acceder que en este caso es la maquina nuestra con el siguiente comando: "nano user-mapping.xml"

[![Captura de pantalla 2026-06-05 081027.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-081027.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-081027.png)

[![Captura de pantalla 2026-06-05 075408.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-075408.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-075408.png)

[![Captura de pantalla 2026-06-05 075910.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-075910.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-075910.png)

A continuación, vamos a configurar apache guacamole para que se pueda acceder a algunas máquinas de producción desde su interfaz WEB.Entramos en el panel de administración de apache guacamole y nos vamos a configuración

[![Captura de pantalla 2026-06-05 103936.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-103936.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-103936.png)

[![Captura de pantalla 2026-06-05 104238.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-104238.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-104238.png)

[![Captura de pantalla 2026-06-05 104228.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-104228.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-104228.png)

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/qEKimage.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/qEKimage.png)

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/3Vjimage.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/3Vjimage.png)

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/DGjimage.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/DGjimage.png)

[![Captura de pantalla 2026-06-05 124858.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-124858.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-124858.png)

[![Captura de pantalla 2026-06-05 124914.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-124914.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-124914.png)

[![Captura de pantalla 2026-06-05 124927.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-05-124927.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-05-124927.png)

A continuación, vamos a desplegar máquina con una ISO win7 starter y permitir el control de dicha máquina desde apache guacamole

[![Captura de pantalla 2026-06-08 094545.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-094545.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-094545.png)

[![Captura de pantalla 2026-06-08 100036.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-100036.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-100036.png)

[![Captura de pantalla 2026-06-08 100419.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-100419.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-100419.png)

[![Captura de pantalla 2026-06-08 100529.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-100529.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-100529.png)

[![Captura de pantalla 2026-06-08 100830.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-100830.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-100830.png)

[![Captura de pantalla 2026-06-08 100958.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-100958.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-100958.png)

[![Captura de pantalla 2026-06-08 101120.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-101120.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-101120.png)

[![Captura de pantalla 2026-06-08 101138.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-101138.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-101138.png)

[![Captura de pantalla 2026-06-08 101214.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-101214.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-101214.png)

[![Captura de pantalla 2026-06-08 101617.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-101617.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-101617.png)

Nos iremos al panel de admin de Apache guacamole para configurar el acceso a la máquina

[![Captura de pantalla 2026-06-08 112353.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-112353.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-112353.png)

Como se ve en la imagen ya tenemos acceso a la máquina Win7 desde apache guacamole

[![Captura de pantalla 2026-06-08 125007.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-125007.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-125007.png)

[![Captura de pantalla 2026-06-08 125048.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-125048.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-125048.png)

El siguiente paso es desplegar un container UPTIMEKUMA. Comenzamos con la instalación en la máquina de docker

[![Captura de pantalla 2026-06-08 130209.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130209.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130209.png)

comprobamos que ya esta instalado en el equipo

[![Captura de pantalla 2026-06-08 130218.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130218.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130218.png)

Accedemos a la web y crearemos una cuenta

[![Captura de pantalla 2026-06-08 130135.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130135.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130135.png)

una vez creada accederemos y todo listo

[![Captura de pantalla 2026-06-08 130305.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130305.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130305.png)

[![Captura de pantalla 2026-06-08 130333.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130333.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130333.png)

Por último, desplegaremos un container de nextcloud en la misma máquina

[![Captura de pantalla 2026-06-08 130546.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-130546.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-130546.png)

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/vXKimage.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/vXKimage.png)

Accedemos a su web y crearemos un usuario

[![Captura de pantalla 2026-06-08 132043.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-132043.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-132043.png)

[![Captura de pantalla 2026-06-08 132159.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-08-132159.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-08-132159.png)

## 3.Roll back

En caso de tratarse, por ejemplo, de una actualización de software, detallar las posibilidades de contingencia y marcha atrás que se han estudiado