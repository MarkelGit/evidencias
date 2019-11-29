# Instalacion de APACHE2, MYSQL, PHP Y PHPMYADMIN.
Estos son los pasos a seguir:

Para poder empezar con la instalación primero debemos actualizar los paquetes.

![](awsImages/aws-update.png)

  - [Instalar Apache2](#instalar-apache2)

## Instalar Apache2

### 1. En nuestro servidor
Para conocer los **datos de acceso SSH** del servidor en GUEBS debes accede al **panel de control** de GUEBS Haz click ahí:
   
![](images/doc10/doc10-panel-de-control-guebs.png)

Copia los datos de conexión:

![](images/doc10/doc10-panel-de-contro-datos-de-acceso-ssh.png)

Si no recuerdas la contraseña del usuario SSH puedes poner una nueva pulsando en `Definir contraseña`

Abre un programa de **terminal** de linea de comandos que permita ejecutar el comando SSH. (OpenSSH client, Windows PowerShell o [MINGW](https://www.google.com/search?q=MINGW)) y ejecuta el comando SSH:

    ssh <usuario>@<ip> -p <puerto>

Te pedirá la contraseña.

Una vez conectado al servidor genera las llaves publica y privada mediante el comando `ssh-keygen`. Ponle un **nombre al archivo** pero y no escribas nada cuando te pida la `passphrase`, solamente pulsa Enter.

![](images/doc10/doc10-conectarse-al-servidor-por-ssh.png)

Esto habrá generado un par de claves publica-privada en el directorio actual. Escribiendo `ls -l` podrás visualizar una lista de los archivos.

![](images/doc10/doc10-claves-publica-y-privada.png)

Ejecuta el comando **`cat`** seguido del nombre del archivo de la clave pública para mostrar su contenido, o abre el archivo con un editor como `nano`. Copia el contenido para llevarlo a [GitHub](https://github.com).
