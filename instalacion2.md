# Instalacion de Owncloud

Explicar como instalar un Owncloud atraves de un contenedor

Lo primero es crear el contenedor,  comando `cd` nos ponemos en la carpeta en la que hemos guardado el archivo .zip que hemos descargado.
Una vez ahí ejecutamos el siguiente comando para crae el contenedor:

~~~
lxc launch ubuntu:20.04 elmeucontenidor
~~~

Una vez creado lo iniciamos con

~~~
lxc start elmeucontenidor
~~~

Cuando ya esta crado e iniciado lo executamos el en comando

~~~
lxc exec elmeucontenidor -- /bin/bash
~~~


El siguiente paso es instalar el servidor web y para ello ejecutamos estos comandos:

~~~
apt update
apt install -y apache2
~~~


Lo que tenemos que hacer ahora es descargar el aricho .zip y hacerle unzip entro de nuestra carpeta `/var/www/html`. Para ello ejecutamos `cd /var/www/html` y seguidamente ejecutamos la siguiente lista de comandos:

~~~
apt update
apt install unzip
wget https://download.owncloud.org/community/owncloud-complete-20210721.zip
unzip owncloud-complete-20210721.zip
~~~

Despues de esto lo que tendremos que hacer es cambiarle los permisos a todos estos ficheros, para ellos dentro de esta carpeta ejecutamos todos estos comandos:

~~~
chown -R www-data:www-data /var/www/html
chmod -R 775 /var/www/html
~~~

Lo siguiente sera intalar el `mysql-server` y algunas librerias `php`. Para ello ejecuta la siguiente lista de comandos:

~~~
apt update
apt install -y mysql-server
apt install php libapache2-mod-php
apt install php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl mysql php-cli php-ldap php-zip php-curl
~~~

 `systemctl restart apache2`


Ahora crearemos la base de datos, para ello entramos en el mysql ejecutando `mysql` en el terminal. Seguidamente ejecutamos el siguiente comando:
~~~
CREATE DATABASE bbdd;
~~~
Seguidamente creamos los usuarios (en este caso se llaman usuario y de contraseña tienen password)
~~~
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
CREATE USER 'usuario'@'172.16.0.57' IDENTIFIED WITH mysql_native_password BY 'password';
~~~
Y ahora le daremos privilegios a los usuarios que acabamos de crear con los siguientes comandos:
~~~
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
GRANT ALL ON bbdd.* to 'usuario'@'172.16.0.57';
~~~

reiniciamos el servidor con `systemctl restart  apache2`.
Para acceder al nexcloud simplemente vamos a nuesto navegador y buscamos `localhost:8080`
