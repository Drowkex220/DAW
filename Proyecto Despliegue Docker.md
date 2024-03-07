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


Usando bind mount para asociar almacenamiento a los contenedores

