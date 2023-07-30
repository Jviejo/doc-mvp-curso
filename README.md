# Sobre docker
Docker es una tecnología que nos permite instalar en nuestro local bases de datos y otros sistemas.

Creación de una base de datos postgres
```
docker run -d --name pg -p 5432:5432 -e POSTGRES_PASSWORD 123456 postgres
```

Diferentes opciones para crear contenedores de postgres en 

https://hub.docker.com/_/postgres

# DBeaver
Software multiplataforma para tratar con sql. Se puede configurar para acceder a multiples bases de datos. 

# Sobre el script para cargar la base de datos northwind

En este repo github 
https://github.com/pthom/northwind_psql
hay un fichero llamado northwind.sql que contiene el script que hay que ejecutar con un programa como DBeaver.


