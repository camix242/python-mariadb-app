##Docker Composer APP Flask

Se desarrolló una pequeña aplicación web basada en Python con el framework Flask y se usa como motor de base de datos Mariadb para realizar un CRUD de contactos



Se generaron y subieron a docker hub las imagenes para Python y base de datos que fueron llamadas en el docker-composer.yml.

Repositorio en Docker Hub para la parte de la app con python y flask:
https://hub.docker.com/repository/docker/ncbeltranb/flask-python-app
ncbeltranb/flask-python-app

Repositorio en Docker Hub para la parte de base de datos:
https://hub.docker.com/repository/docker/ncbeltranb/flask-python-db
ncbeltranb/flask-python-db

##Pasos para hacer correr proyecto

1) Crear una carpeta para que la base de datos sea persitente en la mismas carpeta  del proyecto

$ mkdir mariadb

2) Crear la red

$ docker network create mynet:


2) Ejecutar el docker-composer:

$ docker-compser up -d

3) Una vez los contenideores estén corriendo  se carla base de datos:

$ docker exec -i dbalpine sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD" contactsflask < /home/data/contacts.sql -v'

4) Acceder por el puero 5000 del host

##Integrantes

20191099011 EDSON ANDREI LADINO FRANCO
20202099033 Edda Camila Rodríguez Mojica
20202099021 Néstor Camilo Beltrán Beltrán
