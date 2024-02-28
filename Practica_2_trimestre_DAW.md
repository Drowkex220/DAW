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





