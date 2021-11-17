# manual


Descargar Nextcloud

1. Primero de todos descargamos el Nextcloud clicamos en el `Get Nextcloud`.
![](/Manual/nextcloud1.png)

2. Despues de clicar en Get Nextcloud clicamos en el `Server packages`
![](/Manual/nextcloud2.png)

3. Despues de clicar en el `server packages` nos  saldra la pantalla definitiva donde lo podremos descargar finalmente
![](/Manual/descargarnextcloud.png)

4. Ahora creareamos un directorio llamado `clouds` y despues hacer un `cd`
![](/Manual/vagrantcomandosmanual2.png)

5. Ahora bajaremos la maquina que queremos que es con el commando `vagrant init ubuntu/focal64` y el comando `vagrant up --provider=virtualbox` para proveer el virtualbox

 ![](/Manual/vagrantcomandosmanual.png)

6. Para copiarlo directamente usamos el siguiente comando `cp ~/Baixades/nextcloud-22.2.0.zip .` este comando lo que hace es que pasa directamente la cosa que quieres copiar, al directorio o archivo que quieres.

  ![](/Manual/siuuuuuuuu.png)

7. lo enciende y la prepara con la clave pública del host para poder iniciar sesión con `vargrant ssh`

 ![](/Manual/vagrantssh.png)

 8. Despues hay  que hacer  `sudo su` y aplicarlos  siguientes commandos para descargar unos paquetes.

 ![](/Manual/next1.png)
 ![](/Manual/next2.png)
 ![](/Manual/next3.png)
 ![](/Manual/next4.png)
 ![](/Manual/next5.png)
 ![](/Manual/next6.png)

 9. Hacemos un `mysql` que nos permitira poner unos textos que tendremos que poner. Despues de hacer el mysql tenemos que un  `exit` para que se salga del sitio de  donde estamos poniendo los textos
   ![](/Manual/next8.png)

 10. Tambien hay que crear un Data base y el comando para hacerlo es `CREATE DATABASE bbdd;` esto hay que hacerlo dentro del `mysql`
 11.  Despues hay estoos dos comandos que sirven para apagar el vagrant y encenderlo `vagrant halt` este comando sirve para apagar y para encenderlo es este `vagrant up`

 12. Ahora pondrdemos este comando `rm nextcloud`
![](/Manual/nextcloud10.png)

 13.  Por lo ultimo ponemos estos 5 ultimos comandos para finalizar el proyecto, acontinuacion en la captura.

 ![](/Manual/nextcloudpartefinal.png)

 14. Empezamos a configurar el nextcloud y primero tenemos que crear un  usuario nuestro admin y estas son las  siguientes cosas que tendremos  que rellenar:

 ![](/Manual/manual2.1.png)

 ![](/Manual/manual2.2.png)

 y con esto finalizariamos la parte  de  instalacion.
