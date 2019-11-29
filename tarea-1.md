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

Una vez aquí clickaremos en **Edit**:

![](awsImages/aws-puertos-habilitados.png)

Para acabar, con **Add rule** añadiremos una regla nueva donde seleccionaremos **HTTP** en la sección de tipo. Repite este paso para añdir **HTTPS**:

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
