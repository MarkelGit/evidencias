# Instalacion de APACHE2, MYSQL, PHP Y PHPMYADMIN.
Para poder empezar con la instalación primero debemos actualizar los paquetes.

![](awsImages1/aws-update.png)

Una vez actualizado podemos comenzar con las siguientes instalaciones:

  - [Instalar Apache2](#instalar-apache2)
  - [Instalar MySQL](#instalar-mysql)
  - [Instalar PHP](#instalar-php)
  - [Instalar phpmyadmin](#instalar-phpmyadmin)

## Instalar Apache2

Comenzaremos con el comando para instalar Apache2:

    sudo apt install apache2
   
![](awsImages1/aws-instalar-apache2.png)

Para comprobar que funciona correctamente primero accederemos al **wizard de AWS** para comprobar que HTTP y HTTPS están habilitados:

![](awsImages1/aws-puertos-wizard.png)

Una vez aquí clickaremos en `Edit`:

![](awsImage1s1/aws-puertos-habilitados.png)

Para acabar, con `Add rule` añadiremos una regla nueva donde seleccionaremos **HTTP** en la sección de tipo. Repite este paso para añadir **HTTPS**:

![](awsImages1/aws-configurar-puertos.png)

Ahora ya podemos comprobar si la instalación del Apache2 se ha hecho de manera correcta, para ello escribe lo siguiente en tu navegador:

    http://ip_de_tu_servidor o http://dns_de_tu_servidor
    
![](awsImages1/aws-apache2-comprobacion.png)

Pudes encontrar tu ip o dns en esta sección una vez que la máquina está encendida:

![](awsImages1/aws-conexion.png)

## Instalar MySQL

Una vez mas, empezaremos con el comando de instalación, en este caso para MySQL:

    sudo apt-get install mysql-server mysql-client
    
![](awsImages1/aws-instalar-mysql.png)

Con este comando instalaremos tanto el servidor como el cliente de MySQL.

Al finalizar la instalación ejecutaremos el siguiente comando:

    sudo mysql_secure_installation
    
![](awsImages1/aws-mysql-secure.png)

Con este comando borraremos algunos parametros peligrosos y aseguraremos el acceso ala base de datos.

Después te pedirá que completes unos pasos. Hazlo de la siguiente manera:

![](awsImages1/aws-secure-password-condition.png)

![](awsImages1/aws-secure-permissions.png)

![](awsImages1/aws-secure-finish.png)

Si quisieras comprobar tu versión de **MySQL** puedes hacerlo con esté comando:

    mysql --version
    
![](awsImages1/aws-mysql-version.png)

## Instalar PHP

Ahora toca instalar **PHP**, para ello comenzaremos con el comando de instalación de nuevo:

    sudo apt install php libapache2-mod-php php-mysql

![](awsImages1/aws-instalar-php.png)

Si tus archivos van a ser de tipo **.php** es recomendable que modifiques el archivo **dir.conf** para dar prioridad a dicho tipo de archivos.

Para conseguir esto ejecutaremos el siguiente comando:

    sudo nano /etc/apache2/mods-enabled/dir.conf
    
![](awsImages1/aws-configurar-dirconf.png)

Con esto te saldra algo como esto:

![](awsImages1/aws-original-dirconf.png)

Cambiaremos de sitio el archivo **index.php** colocándolo en primer lugar y lo guardaremos con `Ctrl+o` y saldremos con `Ctrl+x`:

![](awsImages1/aws-edited-dirconf.png)

Seguidamente reiniciaremos el servicio de Apache2 para que los cambios se efectuen:

    sudo systemctl restart apache2

![](awsImages1/aws-restart-apache2.png)

Una vez reiniciado comprobaremos el estado del servicio con este otro comando:

    sudo systemctl status apache2

![](awsImages1/aws-apache2-status.png)

Ahora comprobaremos que estos cambios son eficaces. Para esto, crearemos un archivo de tipo **.php**, el mas útil de ellos es `info.php`:

    sudo nano /var/www/html/info.php
    
![](awsImages1/aws-infophp.png)
 
Esto creará una página en blanco donde escribiremos el siguiente código:
 
![](awsImages1/aws-edit-infophp.png)

Cuando acabes guarda el archivo con `Ctrl+o` y sal de el con `Ctrl+x`.

Ahora podremos ver ese archivo en nuestro navegador escribiendo lo siguiente:

    http://ip_de_tu_servidor/info.php o http://dns_de_tu_servidor/info.php

![](awsImages1/aws-infophp-comprobacion.png)

## Instalar phpmyadmin

Por último, instalaremos phpmyadmin para tener la interfaz gráfica de la base de datos y que nos resulte mas sencillo guardar los datos.

Primero ejecutaremos el comando de instalación:

    sudo apt-get install phpmyadmin php-mbstring php-gettext

![](awsImages1/aws-instalar-phpmyadmin.png)

Esto nos hará algunas preguntas que debemos rellenar:

### ¡Aviso! En el primer mensaje debemos seleccionar Apache2 pero aunque parezca que ya está seleccionado no lo está. Para seleccionarlo pulsa `espacio` una vez que estés sobre Apache2 y le saldrá un puntito. Ahora que si está seleccionado presiona `Tab` y después `Enter`.

![](awsImages1/aws-phpmyadmin-server.png)

Escoge **yes** en este otro mensaje:

![](awsImages1/aws-configurar-phpmyadmin.png)

Ahora debería de pedirte que introduzcas una contraseña. La contraseña es probable que tenga que contener al menos una mayuscula, un caracter especial y algún numero. Además muy posiblemente tenga que tener mas de 8 caracteres.

![](awsImages1/aws-phpmyadmin-password.png)

Como siguiente paso debes confirmar esa contraseña:

![](awsImages1/aws-phpmyadmin-password-confirmation.png)

También es posible que te salga alguno de los siguiente mensajes, responde de esta manera:

![](awsImages1/aws-phpmyadmin-username.png)

Este el nombre de usuario para tu **base de datos**.

![](awsImages1/aws-phpmyadmin-name.png)

Este es el nombre de usuario de **phpmyadmin**.

![](awsImages1/aws-phpmyadmin-username-set.png)

Aquí seleccionamos lo recomendado que es **Unix socket**.

![](awsImages1/aws-conexion-phpmyadmin.png)

Ahora habilitaremos explícitamente las conexiones **PHP** con el siguiente comando:

    sudo phpenmod mbstring

![](awsImages1/aws-phpmyadmin-mbstring.png)

Para guardar los cambios reiniciaremos el servicio de apache:

    sudo systemctl restart apache2
    
Ahora podemos entrar a phpmyadmin desde el navegador de esta manera:

    http://ip_de_tu_servidor/phpmyadmin o http://dns_de_tu_servidor/phpmyadmin
    
Tendremos que iniciar sesión con el **nombre de usuario de phpmyadmin** y contraseña configuradas anteriormente:

![](awsImages1/aws-phpmyadmin-inicio.png)

Ya estamos dentro y podemos editar nuestros datos:

![](awsImages1/aws-phpmyadmin-bbdd.png)
