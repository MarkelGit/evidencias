# Automatizar copias de seguridad

El primer paso es acceder a la ubicación donde guardaremos las copias de seguridad para crear ahi el script que los creará.

![](awsImages7/aws-home.png)

Una vez aquí crearemos la carpeta para guardas las copias y el script.

![](awsImages7/aws-crear-carpeta-backup.png)

Para crear el script accederemos a la carpeta recien creada y ejecutaremos el siguiente comando:

`sudo nano script.sh`

![](awsImages7/aws-crear-script.png)

Al ejecutar el comando nos abrirá el archivo para escribir las líneas del script.

![](awsImages7/aws-crear-script.png)

Ahora accederemos a la ubicación donde estara el ejecutable que iniciará el script.

![](awsImages7/aws-comprobar-html.png)

Al entrar crearemos el ejecutable:

`sudo nano script.php`

![](awsImages7/aws-crear-ejecutable.png)

En el archivo escribiremos las líneas pertinentes.

![](awsImages7/aws-ejecutar-script.png)

Una vez hecho esto le daremos los permisos necesarios a la carpeta donde  esta el **.php**.

![](awsImages7/aws-permisos-ejecutable.png)

También daremos los permisos necesarios a la carpeta donde esta el script.

![](awsImages7/aws-permisos-backup.png)

Por último cambiaremos el propietario de la carpeta donde está el script.

![](awsImages7/aws-cambiar-propietario.png)

# Borrado automatico de los backups

Primero crearemos el archivo de crontab con el siguietne comando:

`crontab -e`

![](awsImages7/aws-crontab.png)

Finalmente añadiremos las líneas que efectuan el borrado de archivos de más de 7 días.

![](awsImages7/aws-borrar-copias.png)
