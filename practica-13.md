# Práctica 13

<span style="font-size: 300%;">PROSTORAGE</span>

<span style="font-size: 300%;">ONLINE</span>

<span style="font-size: 42px;">Despliegue Zabbix en Wilson</span>

[![image.png](https://rrcloud.com.es:6875/uploads/images/gallery/2025-10/scaled-1680-/Ne2image.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2025-10/Ne2image.png)

## 1. Objetivo y resumen

El objetivo es montar un servidor Zabbix en una máquina wilson y monitorizar una máquina cliente

### 1.1. Requisitos

Vamos a necesitar dos máquinas debian en el cual una va a ser donde tengamos instalado nuestro zabbix server y en la otra actuará de cliente

### 1.2. Torres con tareas implicadas

Si la tarea requiere de acciones por parte de otras torres tecnológicas deberá especificarse y detallar por y para qué.

## 2. Documentación de las tareas

En primer lugar vamos a descargar e instalar los repositorios de zabbix

[![Captura de pantalla 2026-06-11 111452.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-111452.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-111452.png)

[![Captura de pantalla 2026-06-11 111519.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-111519.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-111519.png)

[![Captura de pantalla 2026-06-11 111540.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-111540.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-111540.png)

A continuación, vamos a instalar el servidor, el frontend y el agente de zabbix con el siguiente comando: "apt install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf zabbix-sql-scripts zabbix-agent"

Luego una vez instalado, pasaremos a la instalación de MariaDB

[![Captura de pantalla 2026-06-11 112306.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-112306.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-112306.png)

Crearemos la base de datos inicial añadiendo los siguientes puntos:

[![Captura de pantalla 2026-06-11 112634.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-112634.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-112634.png)

Luego, en el servidor Zabbix, importaremos el esquema y los datos iniciales

[![Captura de pantalla 2026-06-11 112928.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-112928.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-112928.png)

Después, desactivaremos la opción log\_bin\_trust\_function\_creators después de importar el esquema de la base de datos.

[![Captura de pantalla 2026-06-11 113149.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113149.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113149.png)

Configuraremos la bases de datos para el servidor zabbix con el siguiente comando: "nano /etc/zabbix/zabbix\_server.conf" y cambiamos donde pone DBPassword

[![Captura de pantalla 2026-06-11 113412.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113412.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113412.png)

Iniciaremos los procesos del servidor y del agente zabbix

[![Captura de pantalla 2026-06-11 113512.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113512.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113512.png)

A continuación, accedemos a la web y realizamos el proceso de instalación

[![Captura de pantalla 2026-06-11 113637.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113637.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113637.png)

[![Captura de pantalla 2026-06-11 113833.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113833.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113833.png)

[![Captura de pantalla 2026-06-11 113901.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-113901.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-113901.png)

[![Captura de pantalla 2026-06-11 114057.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-114057.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-114057.png)

[![Captura de pantalla 2026-06-11 114125.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-114125.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-114125.png)

[![Captura de pantalla 2026-06-11 114431.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-114431.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-114431.png)

Vamos a instalar un cliente de prueba, es decir, en otra máquina debian, instalar el CLIENTE de zabbix y conectarlo con el servidor desplegado.

[![Captura de pantalla 2026-06-11 120931.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-120931.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-120931.png)

Instalamos el agente

[![Captura de pantalla 2026-06-11 121033.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-121033.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-121033.png)

Configuramos el agente para que vea al servidor. Editamos con el siguiente comando: "sudo nano /etc/zabbix/zabbix\_agentd.conf" y modificamos las líneas que ponen "Server y ServerActive" añadiéndole la IP de la máquina servidor que es la 192.168.100.95. Modificamos también la línea donde pone "Hostname" y le vamos a poner "Debian-Cliente-01"

[![Captura de pantalla 2026-06-11 121245.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-121245.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-121245.png)

[![Captura de pantalla 2026-06-11 121353.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-121353.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-121353.png)

Volvemos a reiniciar el equipo

[![Captura de pantalla 2026-06-11 121444.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-121444.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-121444.png)

Por último, dentro del panel de admin de zabbix, vamos a dar de alta el equipo cliente como vemos en la imagen:

[![Captura de pantalla 2026-06-11 122847.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-122847.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-122847.png)

Y ya estaría conectado el servidor con el cliente

[![Captura de pantalla 2026-06-11 123101.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-123101.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-123101.png)

Dentro del panel de admin de zabbix vamos a configurar un panel de métricas: se requiere monitorizar el uso de CPU y memoria

En primer lugar vamos a crear un nuevo tablero

[![Captura de pantalla 2026-06-11 171709.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-171709.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-171709.png)

Dentro de ese tablero vamos a agregar un nuevo widget que le vamos a llamar "Uso CPU"

[![Captura de pantalla 2026-06-11 173839.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-173839.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-173839.png)

Hacemos lo mismo pero ahora otro widget llamado "memoria"

[![Captura de pantalla 2026-06-11 174428.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-174428.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-174428.png)

Por último, ya tendríamos nuestra monitorización creada

[![Captura de pantalla 2026-06-11 174437.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-174437.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-174437.png)

A continuación, vamos a generar una series de alertas para probar el monitoreo en zabbix

lo primero que vamos a hacer es poner la CPU a tope

[![Captura de pantalla 2026-06-11 184713.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-184713.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-184713.png)

[![Captura de pantalla 2026-06-11 185151.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-185151.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-185151.png)

Despues vamos a parar zabbix

[![Captura de pantalla 2026-06-11 190417.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-190417.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-190417.png)

[![Captura de pantalla 2026-06-11 190438.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-190438.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-190438.png)

[![Captura de pantalla 2026-06-11 190718.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-190718.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-190718.png)

Por último, vamos a cargar la memoria

[![Captura de pantalla 2026-06-11 191902.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-191902.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-191902.png)

[![Captura de pantalla 2026-06-11 191841.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-191841.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-191841.png)

Vamos a configurar que el alertado llegue a un grupo de telegram que se va a llamar Prostorage alertas

[![Captura de pantalla 2026-06-11 193217.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-193217.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-193217.png)

[![Captura de pantalla 2026-06-11 194005.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-194005.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-194005.png)

Luego entramos en tipos de medios y activamos la opción de Telegram

[![Captura de pantalla 2026-06-11 195729.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-195729.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-195729.png)

En api token añadimos la clave que nos ha dado en botfather

[![Captura de pantalla 2026-06-11 195949.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-195949.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-195949.png)

entramos en usuarios y seleccionamos la opción que pone admin

[![Captura de pantalla 2026-06-11 200151.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-200151.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-200151.png)

Le damos a la pestaña medios y le damos a la opción agregar

[![Captura de pantalla 2026-06-11 200159.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-200159.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-200159.png)

configuramos y en enviar a añadimos el ID del grupo que hemos creado

[![Captura de pantalla 2026-06-11 200440.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-200440.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-200440.png)

[![Captura de pantalla 2026-06-11 200522.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-11-200522.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-11-200522.png)

Por último, en Alertas-Acciones clicamos en la opcion report problems to Zabbix

[![Captura de pantalla 2026-06-12 102909.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-12-102909.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-12-102909.png)

Seleccionamos la pestaña operaciones y clicamos el mensaje personalizado

[![Captura de pantalla 2026-06-12 103115.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-12-103115.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-12-103115.png)

[![Captura de pantalla 2026-06-12 103652.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-12-103652.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-12-103652.png)

Hacemos una prueba de apago del servidor zabbix y ya nos llegan las alertas al grupo de telegram

[![Captura de pantalla 2026-06-12 105636.png](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/scaled-1680-/captura-de-pantalla-2026-06-12-105636.png)](https://rrcloud.com.es:6875/uploads/images/gallery/2026-06/captura-de-pantalla-2026-06-12-105636.png)

## 3. Roll back

En caso de tratarse, por ejemplo, de una actualización de software, detallar las posibilidades de contingencia y marcha atrás que se han estudiado