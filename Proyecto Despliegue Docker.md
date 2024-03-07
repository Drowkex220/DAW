# PROYECTO DOCKER

#### Actividad 1
Ejecutamos este comando para eliminar cualquier paquete que pueda entrar en conflicto con la instalación
![image](https://github.com/Drowkex220/DAW/assets/131724845/1430efe6-2176-4b0c-9892-f5fa9934e4d9)

COnfiguramos el repositorio apt de Docker
![image](https://github.com/Drowkex220/DAW/assets/131724845/c8d9bea3-5b6c-4dad-bd08-9d1174b9b9f7)

Instalamos Docker con este comando
![image](https://github.com/Drowkex220/DAW/assets/131724845/8782229f-1145-41d6-81b2-5380d859e9d8)

Una vez instalado podemos ver las imagenes que tenemos en docker para probarlo
![image](https://github.com/Drowkex220/DAW/assets/131724845/d4c71e05-9881-4e90-a71b-9ac8fc1760d3)


#### Actividad 2

Vamos a crear una imagen con la guia, lo primero es clonar el repositorio de github
![image](https://github.com/Drowkex220/DAW/assets/131724845/6a73f775-8c07-4bcf-8fc1-817caf63b4eb)

Creamos un Dockerfile para la imagen
![image](https://github.com/Drowkex220/DAW/assets/131724845/d129ece4-9eaf-42fc-a4dc-b44cb2a69716)

![image](https://github.com/Drowkex220/DAW/assets/131724845/4a914625-e01a-4134-9810-2d0b9493fa34)

Visualizamos las imagenes creadas
![image](https://github.com/Drowkex220/DAW/assets/131724845/02a76544-3db7-4c8f-8b14-e3bdae0d4e5c)



Ahora nos creamos la imagen con el siguiente comando
![image](https://github.com/Drowkex220/DAW/assets/131724845/29eb383f-50fd-46f9-a81d-419e4f55fc54)


Volvemos a visualizar la imagen creada
![image](https://github.com/Drowkex220/DAW/assets/131724845/e35cf31c-a207-4ef0-9d77-0c546ab81d6a)

Ahora vamos a iniciar el contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/dc59c37f-4c87-4067-be0a-1b85e4992c8c)

Para publicar el contenedor primero iniciamos sesion con nuestra cuenta de docker hub
![image](https://github.com/Drowkex220/DAW/assets/131724845/7f040cda-1979-43bb-b337-34d14f7d2d90)

Indicamos el nombre de la imagen y hacemos un push
![image](https://github.com/Drowkex220/DAW/assets/131724845/9c1d4984-4ed5-46fd-8117-2821281890c4)



#### Actividad 3

Primero descargamos las imagenes necesarias
![image](https://github.com/Drowkex220/DAW/assets/131724845/adbe5d13-532e-470c-a558-6d9c7060481c)
![image](https://github.com/Drowkex220/DAW/assets/131724845/85b98fad-e3d8-4df2-9e92-d5ae9d310c05)
![image](https://github.com/Drowkex220/DAW/assets/131724845/9f94942f-53cb-47cd-883a-0c5183a09e27)

Las mostramos

![image](https://github.com/Drowkex220/DAW/assets/131724845/3bc2643e-1177-4a4d-81ff-97d649afef36)

Ahora generaremos 3 contenedores con la imagen hello world, repitiendo el comando con distintos nombres
![image](https://github.com/Drowkex220/DAW/assets/131724845/c5061126-061f-488a-b785-1855c61e8a99)


Ahora los listamos
![image](https://github.com/Drowkex220/DAW/assets/131724845/b60e4b8c-2f66-45e3-9af2-f893997876e7)

Para parar los contenedores hacemos lo siguiente 
![image](https://github.com/Drowkex220/DAW/assets/131724845/966a82a0-9f4f-4fae-a9cc-d6697b8be07f)

Ahora podemos ver que no se están ejecutando
![image](https://github.com/Drowkex220/DAW/assets/131724845/98a61867-c02f-4516-a31d-64736799f124)

Por ultimo los eliminamos
![image](https://github.com/Drowkex220/DAW/assets/131724845/c3ed25f2-39fe-449e-aee2-429a66706843)

#### Actividad 4

Creacion de redes para contenedores
![image](https://github.com/Drowkex220/DAW/assets/131724845/5232f36d-2f14-4a2b-a7ab-c2673b22f0f6)

Creamos un contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/f9a84497-dd04-4880-b885-8a686c37dd5f)

Al crear el contenedor con este volumen ahora si eliminamos el contenedor y creamos otro igual siempre guardará cualquier progreso hecho con el antiguo
![image](https://github.com/Drowkex220/DAW/assets/131724845/6763572d-bff2-410c-bc0f-5cb104fcc8e0)


# Usando bind mount para asociar almacenamiento a los contenedores

En este caso vamos a crear un directorio en el sistema de archivo del host, donde vamos a crear un fichero
![image](https://github.com/Drowkex220/DAW/assets/131724845/0b23a3f6-bad5-4a34-ae4a-8256fd86628d)

Ahora montamos el fichero en un contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/22ad3492-6b4f-4a69-8fcd-de1e3098a263)

Y al hacerle un curl podemos ver como se muestra el contenido del archivo
![image](https://github.com/Drowkex220/DAW/assets/131724845/7ea7635b-9af5-4970-afbb-73e8d4f00829)


Podemos ver que si modificamos el archivo index se modifica el resultado del contenedor aunque esté corriendo
![image](https://github.com/Drowkex220/DAW/assets/131724845/c4b37edd-8e19-4040-9864-bed9090bdaa7)

# Redes

Vamos a crear un contenedor interactivo con la imagen debian
![image](https://github.com/Drowkex220/DAW/assets/131724845/d85b5e64-9c57-4be4-851d-ebaf234169b9)

Ahora desde otra ventana del termina vemos la ip asignada al contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/11d01d94-7e5f-4f20-9505-8cbb6ea3e193)

Ahora obtenemos informacion del contenedor filtrando el json de salida para obtener la IPv4 que se le ha asignado
![image](https://github.com/Drowkex220/DAW/assets/131724845/379eb110-f41f-47a5-98ac-d47d232679be)
![image](https://github.com/Drowkex220/DAW/assets/131724845/36dcfd0d-5f38-4c0e-9c72-5ffec3f8bd9b)

Si conectamos un contenedor a la red host, el contenedor ofrece el servicio que tiene configurado en el puerto de la red del anfitrión. No tiene ip propia, sino es cómo si tuviera la ip del anfitrión. Por lo que los puertos son accesibles directamente desde el host

![image](https://github.com/Drowkex220/DAW/assets/131724845/79229895-0b7c-4f2e-a4a9-e4315820bdf1)
![image](https://github.com/Drowkex220/DAW/assets/131724845/17b21849-7939-4f42-84e6-93c24879d40d)

#### Actividad 5


Vamos a hacer uso del fichero docker-compose.yml, nos crearemos un archivo yaml con este contenido, este nos creará un contenedor con todo lo definido en el, los docker compose permiten agilizar bastante la creacion de contenedores en docker

![image](https://github.com/Drowkex220/DAW/assets/131724845/246898e1-c7b8-488c-97c7-6f92195cb0c4)


Lo siguiente es levantar el contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/9bffa6a7-d85e-4865-835a-a4569ae21799)

Y mostramos los contenedores activos
![image](https://github.com/Drowkex220/DAW/assets/131724845/b40cd324-3b9b-467a-b448-6a304ff2f519)

comprobamos que se ha creado el volumen
![image](https://github.com/Drowkex220/DAW/assets/131724845/e5534af2-b619-47ae-80c2-5f9c4a3da6ac)

##### Usando bind mount con docker compose

Creamos un yml con este contenido
![image](https://github.com/Drowkex220/DAW/assets/131724845/568b42e8-2601-4272-9e00-084a7752eed1)

Iniciamos el contenedor
![image](https://github.com/Drowkex220/DAW/assets/131724845/f3a2db08-20ba-49d1-8903-fbdce98abac8)

Y podemos ver como se ha creado el directorio data
![image](https://github.com/Drowkex220/DAW/assets/131724845/c53f5e60-c6d5-4509-82b4-9022de54f04b)

##### Despliegue de aplicacion 

Creamos un yml e introducimos esto en el
![image](https://github.com/Drowkex220/DAW/assets/131724845/dd3a77ab-c44a-471d-943a-474b540a9477)

Lo siguiente es hacer un docker compose up -d
![image](https://github.com/Drowkex220/DAW/assets/131724845/cba4f0e1-e299-45a0-9de8-8a3a47952d25)

Si queremos ver los contenedores que se han creado basta con usar este comando
![image](https://github.com/Drowkex220/DAW/assets/131724845/42bead4f-c609-4e6e-80d6-3facbe08274e)


 
