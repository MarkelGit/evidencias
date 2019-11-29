# Instalacion de APACHE2, MYSQL, PHP Y PHPMYADMIN.
Para poder empezar con la instalación primero debemos actualizar los paquetes.

![](awsImages/aws-update.png)

Una vez actualizado podemos comenzar con las siguientes instalaciones:

  - [Instalar Apache2](#instalar-apache2)
  - [Instalar MySQL](#instalar-mysql)
  - [Instalar PHP](#instalar-php)
  - [Instalar phpmyadmin](#instalar-phpmyadmin)

## Instalar Apache2

Comenzaremos con el comando para instalar Apache2:

    sudo apt install apache2
   
![](awsImages/aws-instalar-apache2.png)

Para comprobar que funciona correctamente primero accederemos al **wizard de AWS** para comprobar que HTTP y HTTPS están habilitados:

![](awsImages/aws-puertos-wizard.png)

Una vez aquí clickaremos en `Edit`:

![](awsImages/aws-puertos-habilitados.png)

Para acabar, con `Add rule` añadiremos una regla nueva donde seleccionaremos **HTTP** en la sección de tipo. Repite este paso para añdir **HTTPS**:

![](awsImages/aws-configurar-puertos.png)

Ahora ya podemos comprobar si la instalación del Apache2 se ha hecho de manera correcta, para ello escribe lo siguiente en tu navegador:

    http://ip_de_tu_servidor o http://dns_de_tu_servidor
    
![](awsImages/aws-apache2-comprobacion.png)

Pudes encontrar tu ip o dns en esta sección una vez que la máquina está encendida:

![](awsImages/aws-conexion.png)

## Instalar MySQL

Una vez mas, empezaremos con el comando de instalación, en este caso para MySQL:

    sudo apt-get install mysql-server mysql-client
    
![](awsImages/aws-instalar-mysql.png)

Con este comando instalaremos tanto el servidor como el cliente de MySQL.

Al finalizar la instalación ejecutaremos el siguiente comando:

    sudo mysql_secure_installation
    
![](awsImages/aws-mysql-secure.png)

Con este comando borraremos algunos parametros peligrosos y aseguraremos el acceso ala base de datos.

Después te pedirá que completes unos pasos. Hazlo de la siguiente manera:

![](awsImages/aws-secure-password-condition.png)

![](awsImages/aws-secure-permissions.png)

![](awsImages/aws-secure-finish.png)

## Instalar PHP

Ahora toca instalar **PHP**, para ello comenzaremos con el comando de instalación de nuevo:

    sudo apt install php libapache2-mod-php php-mysql

![](awsImages/aws-instalar-php.png)

Si tus archivos van a ser de tipo **.php** es recomendable que modifiques el archivo **dir.conf** para dar prioridad a dicho tipo de archivos.

Para conseguir esto ejecutaremos el siguiente comando:

    sudo nano /etc/apache2/mods-enabled/dir.conf
    
![](awsImages/aws-configurar-dirconf.png)

Con esto te saldra algo como esto:

![](awsImages/aws-original-dirconf.png)

Cambiaremos de sitio el archivo **index.php** colocándolo en primer lugar y lo guardaremos con `Ctrl+o` y saldremos con `Ctrl+x`:

![](awsImages/aws-edited-dirconf.png)

Seguidamente reiniciaremos el servicio de Apache2 para que los cambios se efectuen:

    sudo systemctl restart apache2

![](awsImages/aws-restart-apache2.png)

Una vez reiniciado comprobaremos el estado del servicio con este otro comando:

    sudo systemctl status apache2

![](awsImages/aws-apache2-status.png)

Ahora comprobaremos que estos cambios son eficaces. Para esto, crearemos un archivo de tipo **.php**, el mas útil de ellos es `info.php`:

    sudo nano /var/www/html/info.php
    
![](awsImages/aws-infophp.png)
 
Esto creará una página en blanco donde escribiremos el siguiente código:
 
![](awsImages/aws-edit-infophp.png)

Cuando acabes guarda el archivo con `Ctrl+o` y sal de el con `Ctrl+x`.

Ahora podremos ver ese archivo en nuestro navegador escribiendo lo siguiente:

    http://ip_de_tu_servidor/info.php o http://dns_de_tu_servidor/info.php

![](awsImages/aws-infophp-comprobacion.png)

## Instalar phpmyadmin

Por último, instalaremos phpmyadmin para tener la interfaz gráfica de la base de datos y que nos resulte mas sencillo guardar los datos.

Primero ejecutaremos el comando de instalación:

    sudo apt-get install phpmyadmin php-mbstring php-gettext

![](awsImages/aws-instalar-phpmyadmin.png)

Esto nos hará algunas preguntas que debemos rellenar:

### ¡Aviso! En el primer mensaje debemos seleccionar Apache2 pero aunque parezca que ya está seleccionado no lo está. Para seleccionarlo pulsa `espacio` una vez que estés sobre Apache2 y le saldrá un puntito. Ahora que si está seleccionado presiona`Tab` y despué `Enter`.

![](awsImages/aws-phpmyadmin-server.png)

Escoge **yes** en este otro mensaje:

![](awsImages/aws-configurar-phpmyadmin.png)

Ahora debería de pedirte que introduzcas una contraseña. La contraseña es probable que tenga que contener al menos una mayuscula, un caracter especial y algún numero. Además muy posiblemente tenga que tener mas de 8 caracteres.

![](awsImages/aws-phpmyadmin-password.png)

Como siguiente paso debes confirmar esa contraseña:

![](awsImages/aws-phpmyadmin-password-confirmation.png)

También es posible que te salga alguno de los siguiente mensajes, responde de esta manera:

![](awsImages/aws-phpmyadmin-username.png)

![](awsImages/aws-phpmyadmin-name.png)

![](awsImages/aws-phpmyadmin-username-set.png)

![](awsImages/aws-conexion-phpmyadmin.png)
