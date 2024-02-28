# Práctica 1: Servidor de alojamiento web

## Instalar vsftpd

Para instalar vsftpd primero ejecutamos el siguiente comando de instalación
```
sudo apt install vsftpd
```

![Screenshot1](img/vsftpd1.png)

Ahora iniciaremos el servicio

```
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

Lo siguiente es crearnos un usuario

```
sudo useradd -m [username]
sudo passwd [username]
```

Para configurarlo y poder usar TLS debemos ejecutar este comando

```
sudo nano /etc/vsftpd.conf
```

Ahora deberemos descomentar las siguientes lineas 

´´´
ssl_enable=YES
rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
´´´

generacion del certificado tls

```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/vsftpd.pem -out /etc/ssl/private/vsftpd.pem

```

Despues hacemos un restart del servicio

```
sudo systemctl restart vsftpd
```

### Habilitar SSH y SFTP

Ejecutamos este comando para instalar el ssh

```
sudo apt install openssh-server
```


### Creacion de los scripts para la automatizacion

Una vez instalado lo iniciamos

```
sudo systemctl enable ssh
sudo systemctl start ssh

```

Creamos los dos scrpits necesarios

crear_usuarios.sh
```
#!/bin/bash

# Verificar argumentos
if [ $# -eq 0 ]; then
    echo "Error: Se requiere al menos un nombre de usuario como argumento."
    exit 1
fi

# Iterar sobre cada argumento (nombre de usuario)
for username in "$@"; do
    # Crear usuario
    sudo adduser --disabled-password --gecos "" $username

    # Crear directorio de alojamiento web
    sudo mkdir -p /var/www/html/$username
    sudo chown $username:$username /var/www/html/$username
    sudo chmod 755 /var/www/html/$username

    echo "Usuario $username creado con éxito."
done
```

configurar_vhosts.sh
```
#!/bin/bash

# Verificar argumentos
if [ $# -eq 0 ]; then
    echo "Error: Se requiere al menos un nombre de usuario como argumento."
    exit 1
fi

# Iterar sobre cada argumento (nombre de usuario)
for username in "$@"; do
    # Configurar archivo de host virtual
    conf_file="/etc/apache2/sites-available/${username}.conf"
    echo "<VirtualHost *:80>
        ServerAdmin admin@${username}.example.com
        ServerName ${username}.example.com
        DocumentRoot /var/www/html/${username}
        <Directory /var/www/html/${username}>
            Options Indexes FollowSymLinks
            AllowOverride All
            Require all granted
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/${username}.error.log
        CustomLog ${APACHE_LOG_DIR}/${username}.access.log combined
    </VirtualHost>" | sudo tee $conf_file > /dev/null

    # Habilitar el host virtual
    sudo a2ensite $username.conf

    echo "Host virtual para $username configurado con éxito."
done

# Reiniciar Apache para aplicar los cambios
sudo systemctl reload apache2

```

También hay que darles permisos cuando los creemos

```
sudo chmod +x /usr/local/bin/crear_usuarios.sh
sudo chmod +x /usr/local/bin/configurar_vhosts.sh
```

Ahora creamos un usuario y haremos el archivo de configuración

```
sudo /usr/local/bin/crear_usuarios.sh usuario1
sudo /usr/local/bin/configurar_vhosts.sh usuario1
```

Eso nos creara un .conf para ese usuario
