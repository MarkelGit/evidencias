# Virtual Hosts

Primero entraremos al wizard para añadir el puerto 21.

![](awsimages5/aws-wizard-amazon.png)

Una vez aquí entrarems en **Inbound** y clickaremos sobre **Edit**.

![](awsimages5/aws-edit-inbound.png)

Clickando sobre **Add Rule** podremos añadir un puerto mas, en este caso elegiremos **Custom TCP** con el puerto 21.

Cuando lo tengamos añadido guardaremos los cambios con **Save**.

![](awsimages5/aws-add-rule.png)

Podremos ver que se ha añadido la nueva norma.

![](awsimages5/aws-tcp-rule.png)

Ahora procederemos a **instalar el servidor ftp en linux**.

Para ello utilizareos este comando:

`sudo apt-get install vsftp`

![](awsimages5/aws-instalar-ftp.png)

Es recomendable hacer una copia del archivo de configuración para tener un archivo limpio en el que trabajar.

`sudo cp /etc/www/vsftp.conf /etc/www/vsftp.conf.original`

![](awsimages5/aws-crear-copia-conf.png)

Ahora crearemos los usuarios de tipo ftp para asignarles una ruta de carpeta y que se dirijan a esa al hacer la conexión.

`sudo useradd -g ftp -d ruta_de_la_carpeta -c "comentario" nombre_usuario`

![](awsimages5/aws-crear-usuarios.png)

Al crear los usuarios de esta manera hay que asignarles una contraseña manualmente.

`sudo passwd nombre_usuario`

![](awsimages5/aws-contraseñas.png)

Ahora editaremos el archivo de configuración.

`sudo nano /etc/var/vsftp.conf`

![](awsimages5/aws-comando.nano.png)

Con ese comando accederemos al archivo en el cual tienen que aparecer las siguientes líneas sin comentar:

![](awsimages5/aws-configuracion.png)

Una vez tengamos esas líneas saldremos del archivo con `Ctrl+O` y reiniciaremos el servicio:

`sudo service vsftpd restart`

![](awsimages5/aws-restart-ftp.png)
