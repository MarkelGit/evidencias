# IP Elástica.
En esta ocasión haremos que nuestra IP no varíe cada vez que encendemos la máquina virtual. 

Para conseguir esto completaremos dos pasos:

  - [Alquilar IP Elástica](#alquilar-ip-elastica)
  - [Asociar IP Elástica](#asociar-ip-elastica)

## Alquilar IP Elástica

Para empezar, en el **panel de navegación de aws** entraremos en `Elastic IPs`:
   
![](awsImages2/aws-panel-de-navegacion.png)

Una vez dentro clickaremos sobre cualquiera de las dos opciones donde pone `Allocate Eladtic IP Address`:

![](awsImages2/aws-allocate-elastic-ip-address.png)

Nos saldrá una ventana para elegir si queremos una IP ofrecida por Amazon o si queremos una IP propia que tengamos previamente guardada.

Nosotros elegiremos `Amazon´s pool of IPv4 address` para que Amazon nos proporcione una IP:

![](awsImages2/aws-amazons-pool.png)

Una vez seleccionada esa opción continuaremos clickando en `Allocate` y ya tendremos la IP elástica alquilada:

![](awsImages2/aws-allocated-ip.png)

## Asociar IP Elástica

Una vez tengamos alquilada la IP elástica tenemos que asociarla con la máquina virtual que queremos usarla:
   
![](awsImages2/aws-associate-elastic-ip-address.png)

En la ventana de configuración configuraremos los datos seleccionando `Instance` en la primera opción y rellenando los campos con la ID e IP fija de nuestra máquina virtual:

![](awsImages2/aws-associate-instance.png)

Ahora ya tendríamos la IP Elástica asociada con nuestra máquina virtual:

![](awsImages2/aws-ip-associated.png)

Ahora podemos ver la IP asociada en los detalles de nuestra máquina virtual:

![](awsImages2/aws-instance.png)
