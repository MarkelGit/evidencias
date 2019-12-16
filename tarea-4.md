# Virtual Hosts

Primero crearemos los registros DNS (como en la tarea anterior).

En esta ocasión crearemos dos DNS, uno para el cliente y uno para el servidor.

![](awsImages4/aws-cliente-dns.png)

![](awsImages4/aws-servidor-dns.png)

![](awsImages4/aws-dns-creado.png)

Una vez creados los DNS crearemos una carpeta para el cliente y otra para el servidor (con sus respectivos index).

![](awsImages4/aws-crear-carpetas.png)

Ahora tenemos que darle los permisos correctos a la carpeta **www**.

![](awsImages4/aws-permisos-www.png)

Seguidamente crearemos copias de los archivos de configuración para editar uno para el cliente y otro para el servidor.

![](awsImages4/aws-crear-copias.png)

Es hora de editar cada archivo con el **ServerName** adecuado (el del registro DNS) y cambiar el **DocumentRoot** a la carpeta.

![](awsImages4/aws-cliente-dns.png)

![](awsImages4/aws-servidor-dns.png)

Una vez configurados los archivos debemos habilitar esa configuración con el siguiente comando

`sh sudo a2ensite cliente.conf`

![](awsImages4/aws-a2ensite.png)

Por último reiniciaremos el apache para que los cambios se guarden.
`sh sudo systemctl restart apache2`

![](awsImages4/aws-restart-apache.png)

Ahora buscando en el navegador con el DNS creado nos deberian de salir los index.

![](awsImages4/aws-cliente-html.png)

![](awsImages4/aws-servidor-html.png)
