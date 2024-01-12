##DNS ACTIVITY 1



#1. ¿Qué es TLD? ¿Cómo se clasifican los dominios de nivel superior?, Pon algunos ejemplos.


Un dominio del nivel superior o TLD (del inglés top-level domain) es la más alta categoría de los FQDN que es traducida a direcciones IP por los DNS oficiales de Internet

Son clasificados en los siguientes grupos
•	Dominios de nivel superior geográficos: .uk .us .jp

•	Dominios de nivel superior genéricos: .com .org .net

•	Dominios de nivel superior de infraestructura: .arpa .int 

#2. Dominios de nivel superior descentralizado
#¿Qué es FQDN?, Pon algún ejemplo de FQDN

FQDN (Fully Qualified Domain Name) la dirección completa y única necesaria para tener presencia en Internet. Está compuesta por el nombre de host y el de dominio y se utiliza para localizar hosts específicos en Internet y acceder a ellos mediante la resolución de nombres.

Ejemplo:
hosting.ionos.es. ([Nombre de host].[Dominio].[TLD].[Raíz])


#3. ¿Qué son los root servers? , ¿Cuántos root servers hay?, ¿Cuántos servidores raíz físicos existen y dónde se encuentran?, ¿Qué es anycast?
Los root servers (servidores raíz) son una parte fundamental de la infraestructura del Sistema de Nombres de Dominio (DNS). Su función principal es responder a las consultas DNS iniciando la resolución de nombres de dominio desde la raíz del árbol del DNS

Actualmente, hay 13 conjuntos de servidores raíz distribuidos en todo el mundo.

Aunque hay 13 conjuntos lógicos de servidores raíz, en la práctica, cada conjunto puede estar compuesto por múltiples servidores físicos para garantizar la redundancia y la disponibilidad. Estos servidores físicos están distribuidos globalmente en diferentes regiones geográficas.

Anycast es una técnica de enrutamiento de red que permite a múltiples servidores repartir la carga de trabajo para una dirección IP específica. En el contexto de los root servers, algunos de ellos utilizan la técnica de anycast para tener varias instancias que comparten la misma dirección IP, pero están ubicadas en diferentes lugares geográficos. Cuando un usuario realiza una consulta DNS a un servidor anycast, la solicitud se envía a la instancia más cercana geográficamente, mejorando la velocidad y la eficiencia de la respuesta.

#4. ¿Qué es un archivo de zona (zone file)? Indica para qué sirven los registros de un archivo de zona. Pon un ejemplo de un archivo de zona e interpreta la información almacenada

Un archivo de zona es un archivo de texto que almacena información de configuración sobre un dominio específico en el Sistema de Nombres de Dominio (DNS). Los archivos de zona contienen registros que asignan nombres de dominio a direcciones IP y realizan otras funciones esenciales del DNS.

Ejemplo:

 

Interpretación:

Se define la autoridad de la zona y otros parámetros en el registro SOA.
Se especifican servidores de nombres con registros NS.
Se asignan direcciones IPv4 e IPv6 a nombres de dominio específicos con registros A y AAAA.
Se establecen alias con registros CNAME.
Se configuran servidores de correo con registros MX.
Se incluye información de texto adicional con registros TXT.
