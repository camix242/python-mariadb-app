#Comandos Docker

Para hacer correr el contenedor en una red

$ docker network create some-network # Create the network


##Contenedor de APP

Ingresar a la carpeta APP

$ docker build --no-cache -t my-python-app .

$ docker run --net some-network -p 5000:5000 -it --rm --name my-running-app -d my-python-app

##Contenedor de APP

Para contruir el contenedor de base de datos ingresar a DB


docker build --no-cache -t mymariadb -f Dockerfile .



$ docker run --net some-network -p 3306:3306  --name dbalpine -e MYSQL_ROOT_PASSWORD=pwd -e MYSQL_DATABASE=contactsflask -d mymariadb

MYSQL_ROOT_PASSWORD representa la contraseña del usuario "root" que puede ser cambiada de ser necesario.


Para crear y llenar la base de datos de la aplicación "contactsflask"
docker exec -i dbalpine sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD" contactsflask < /home/data/contacts.sql -v'

# Valdación base de datos

Ingresar al contendeor:
docker exec -ti dbalpine sh

Ingresar a MariaDB

mysql -p -> (Luego escribir la contraseña asignada)

show databases; (Validar que la bd ese creada)


#Fuente principal:

https://hub.docker.com/_/mariadb
