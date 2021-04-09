# Docker Composer APP Flask

Se desarrolló una pequeña aplicación web basada en Python con el framework Flask y se usa como motor de base de datos Mariadb para realizar un CRUD de contactos


Se generaron y subieron a docker hub las imagenes para Python y base de datos que fueron llamadas en el docker-composer.yml.

Repositorio en Docker Hub para la parte de la app con python y flask:

[ncbeltranb/flask-python-app](https://hub.docker.com/repository/docker/ncbeltranb/flask-python-app)


Repositorio en Docker Hub para la parte de base de datos:

[ncbeltranb/flask-python-db](https://hub.docker.com/repository/docker/ncbeltranb/flask-python-db)


## Pasos para hacer correr proyecto

1. Crear una carpeta para que la base de datos sea persitente en la mismas carpeta  del proyecto:
```bash
$ mkdir mariadb
```
2. Crear la red:
```bash
$ docker network create mynet
```

3. Ejecutar el docker-composer:
```bash
$ docker-compser up -d
```
4. Una vez los contenideores estén corriendo  se carga la base de datos:
```bash
$ docker exec -i dbalpine sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD" contactsflask < /home/data/contacts.sql -v'
```
5. Acceder por el puero 5000 del host
```
http://localhost:5000
```

## Integrantes

**20191099011 Edson Andrei Ladino Franco**

**20202099033 Edda Camila Rodríguez Mojica**

**20202099021 Néstor Camilo Beltrán Beltrán**
