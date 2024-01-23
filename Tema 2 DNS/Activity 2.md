#### La UHU (Universidad de Huelva) tiene varios servidores DNS. Consulta a tu servidor DNS por defecto sus direcciones IP al menos 2 de ellos.
nslookup -type=ns uhu.es

  Servidor:  dns.google
  Address:  8.8.8.8
  
    Respuesta no autoritativa:
    uhu.es  nameserver = chico.rediris.es
    uhu.es  nameserver = dns.uhu.es
    uhu.es  nameserver = dns1.cica.es
    uhu.es  nameserver = dns-1.uhu.es
    uhu.es  nameserver = sun.rediris.es
    uhu.es  nameserver = dns2.cica.es
    uhu.es  nameserver = dns-p.uhu.es
    uhu.es  nameserver = master.infoblox

uhu.es  nameserver = dns.uhu.es
  Nombre:  dns.uhu.es
  Address:  150.214.167.1


uhu.es  nameserver = dns-1.uhu.es
  Nombre:  dns-1.uhu.es
  Address:  150.214.167.1
    


#### ¿Son las respuestas anteriores autoritativas? 
No son autoritativas porque la información no proviene del servidor autoritativo para la zona, sino de la caché de algún otro servidor.


#### Consulta la dirección IP de un servidor de correo de uhu.es.
C:\Users\PORTATIL>nslookup  -type=mx uhu.es dns.uhu.es
Servidor:  dns-1.uhu.es
Address:  150.214.167.1

uhu.es  MX preference = 10, mail exchanger = mx04.puc.rediris.es
uhu.es  MX preference = 10, mail exchanger = mx03.puc.rediris.es

#### ¿Son las respuestas anteriores autoritativas? 
Sí, porque la respuesta proviene del servidor autoritativo del dominio. Además comprobamos que puede existir más de un servidor autoritativo para el mismo dominio.


#### Si hay más de un servidor dns autoritativo para el dominio uhu.es, ¿cómo sabemos cuál es el primario?¿en qué fecha se actualizó por última vez?¿cúal es la dirección e-mail del administrador?

C:\Users\PORTATIL>nslookup -type=soa uhu.es dns-1.uhu.es
Servidor:  dns-p.uhu.es
Address:  150.214.167.1

uhu.es
        primary name server = master.infoblox
        responsible mail addr = please_set_email.absolutely.nowhere
        serial  = 2019022075
        refresh = 14400 (4 hours)
        retry   = 7200 (2 hours)
        expire  = 604800 (7 days)
        default TTL = 900 (15 mins)

#### Comprueba que el DNS inverso está bien configurado para dns-1.uhu.es.

C:\Users\PORTATIL>nslookup   150.214.167.1
Servidor:  dns.google
Address:  8.8.8.8

Nombre:  dns-1.uhu.es
Address:  150.214.167.1

#### Comprueba que el DNS inverso está bien configurado para www.bp.com.

C:\Users\PORTATIL>nslookup bp.com
Servidor:  dns.google
Address:  8.8.8.8

Respuesta no autoritativa:
Nombre:  bp.com
Address:  54.72.215.189


C:\Users\PORTATIL>nslookup  54.72.215.189
Servidor:  dns.google
Address:  8.8.8.8

Nombre:  ec2-54-72-215-189.eu-west-1.compute.amazonaws.com
Address:  54.72.215.189

#### Por defecto, el comando NSLOOKUP devuelve los registros de tipo A. ¿Qué se obtiene al consultar los registros NS? Se obtienen los servidores autoritativos para un dominio.

C:\Users\PORTATIL>nslookup
Servidor predeterminado:  dns.google
Address:  8.8.8.8

> set type=ns
> uhu.es
Servidor:  dns.google
Address:  8.8.8.8

Respuesta no autoritativa:
uhu.es  nameserver = dns-1.uhu.es
uhu.es  nameserver = dns.uhu.es
uhu.es  nameserver = sun.rediris.es
uhu.es  nameserver = chico.rediris.es
uhu.es  nameserver = dns1.cica.es
uhu.es  nameserver = dns2.cica.es
uhu.es  nameserver = master.infoblox
uhu.es  nameserver = dns-p.uhu.es


#### Consulta el TLD de las páginas de España: “es”.

C:\Users\PORTATIL>nslookup es
Servidor:  dns.google
Address:  8.8.8.8

Nombre:  es.


#### ¿Se obtiene alguna respuesta? No, porque por defecto se buscan registros de tipo A y tipo AAAA. Como “es” no es un FQDN, lo lógico es buscar registros NS para saber qué servidores lo resuelven.

C:\Users\PORTATIL>nslookup -type=ns es
Servidor:  dns.google
Address:  8.8.8.8

Respuesta no autoritativa:
es      nameserver = h.nic.es
es      nameserver = a.nic.es
es      nameserver = c.nic.es
es      nameserver = g.nic.es


#### Consulta las direcciones IP de www.google.com.

C:\Users\PORTATIL>nslookup google.com
Servidor:  dns.google
Address:  8.8.8.8

Respuesta no autoritativa:
Nombre:  google.com
Addresses:  2a00:1450:4003:80c::200e
          142.250.201.78

#### ¿Puede un mismo nombre de dominio traducirse en varias direcciones IP distintas? 

Sí, por motivos de disponibilidad: si un servidor se avería, los otros pueden mantener el servicio.


#### ¿Quién decide a cuál de las direcciones IP se envía una petición? 

El solucionador local es quien toma la decisión, ordenando todos los registros A recibidos aleatoriamente y utilizando el primero de la lista. De esa forma se produce un balanceo de carga entre todos los servidores.




