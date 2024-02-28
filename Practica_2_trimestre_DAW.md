# Práctica 1: Servidor de alojamiento web

## Instalar vsftpd

Para instalar vsftpd primero ejecutamos el siguiente comando de instalación

![Screenshot1](img/vsftdp1.png)

Ahora iniciaremos el servicio

```
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

Tambien nos hace falta instalar openssh-server

![image](https://github.com/Drowkex220/DAW/assets/131724845/ff6f8ffe-f26b-4972-95b1-bae50ff0cf82)


### Configuracion de servicios
Ahora crearemos un directorio para el sitio web y le damos permisos al directorio

![image](https://github.com/Drowkex220/DAW/assets/131724845/985ff45c-9d5c-4e90-b0c1-6a6e7f0dc550)

Lo siguiente es crear el archivo de configuracion del sitio

Haciendo un nano  a esta dirección deberemos crear el siguiente archivo en la carpeta
![image](https://github.com/Drowkex220/DAW/assets/131724845/b808a2c3-9ef3-454c-8f11-94e5f9acb825)


![image](https://github.com/Drowkex220/DAW/assets/131724845/7547f3b1-3cc5-45bd-9c7c-5b87becc80e0)


Lo siguiente es activarlo con un enlace simbolico y reiniciar el servidor

![image](https://github.com/Drowkex220/DAW/assets/131724845/989697f9-de0e-480f-a663-8005da769e27)

Con un nano nos aseguramos de que el dominio esté en el archivo de hosts

![image](https://github.com/Drowkex220/DAW/assets/131724845/c3dcb6a3-4a99-4cd1-bf85-64001247ee0c)

Y vemos si funciona

![image](https://github.com/Drowkex220/DAW/assets/131724845/e500efe2-9c7f-4fbc-96dd-c6e4c74fc532)

Lo que sigue es configurar el vsftpd para el acceso FTP seguro o TLS

Hacemos un nano en /etc/vsftpd.conf y dejamos el archivo así
![image](https://github.com/Drowkex220/DAW/assets/131724845/a2986905-fae7-4a01-be60-14064d06e657)

lo siguiente es reiniciar el servicio usando

```
sudo service vsftpd restart
```


### Automatización mediante scripts

primero miraremos el script de crear usuarios

![image](https://github.com/Drowkex220/DAW/assets/131724845/7159c6a1-5c01-4e32-958a-f1fcb1abbb51)

Ahora iniciamos el script pero antes le damos permisos

![image](https://github.com/Drowkex220/DAW/assets/131724845/6fc70e10-48ee-4635-a287-c8812bd32af7)

Ahora para el sstema de acceso a ftp, ssh, smtp creamos el archivo sistema_acceso.sh

![image](https://github.com/Drowkex220/DAW/assets/131724845/f67892b9-3578-494d-b7d8-647dc879933f)


le damos permiso y lo ejecutamos

Al haberlo ejecutado anteriormente nos saldra que ya existe el usuario

![image](https://github.com/Drowkex220/DAW/assets/131724845/06333030-2d18-433e-ae38-1fa52b1e785e)


Para este script necesitamos instalar bind usando
```
sudo apt install bind9
```


Ahora para automatizar los servidores DNS usaremos un script llamado servidor_DNS.sh

![image](https://github.com/Drowkex220/DAW/assets/131724845/b0a966f3-7802-4d33-9ac7-7cf374ad400f)


Damos permisos y ejecutamos

![image](https://github.com/Drowkex220/DAW/assets/131724845/78eb0789-652c-4834-bb16-7e7a6225006f)


Ahora toca crear el Script para la creacion de bases de datos con permisos, para ello crearemos el archivo Base_Datos.sh

![image](https://github.com/Drowkex220/DAW/assets/131724845/6031e048-7a2a-4089-bb76-7819184afbae)

Permisos y ejecutamos

![image](https://github.com/Drowkex220/DAW/assets/131724845/4d2c8051-24a2-43eb-a40b-d2a62dc67a66)

Ahora solo queda comprobarlo en phpmyadmin
Iniciamos sesion...
![image](https://github.com/Drowkex220/DAW/assets/131724845/256fc855-66ea-41e1-b112-b6e78afb3456)

Y comprobamos que la base de datos ha sido creada correctamente

![image](https://github.com/Drowkex220/DAW/assets/131724845/11b4bb5b-c012-458a-94c9-17d8d660451d)


Lo último sería automatizar la habilitación de Python, así que crearemos el archivo Habilitar_python.sh
![image](https://github.com/Drowkex220/DAW/assets/131724845/c67b3029-023a-4fb9-a8ad-e51fe73411bf)


Permisos y ejecutamos
![image](https://github.com/Drowkex220/DAW/assets/131724845/f1c58443-d8d6-4bc2-ab7f-39e5c9071361)


