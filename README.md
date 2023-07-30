# Sobre la terminal

La terminal es un programa básico en el ambito de la programación.

Se usa para interactuar con el sistema. 

Con la terminal podemos, por ejemplo, crear contenedores de docker con el comando apropiado

Algunos comandos de la terminal
```
ls -l (lista de ficheros / directorios)
ls -la (lista de fichero / dir tanto los ocultos como los visibles)
pwd (nos da el directorio donde estamos)

```

# Sobre docker

Para instalar docker-destop en mac y windows tenemos que ir a 

https://www.docker.com/products/docker-desktop/

Hay versiones para windows mac x86 / mac m1 / linux

Docker es una tecnología que nos permite instalar en nuestro local bases de datos y otros sistemas.

Creación de una base de datos postgres
```
docker run -d --name pg -p 5432:5432 -e POSTGRES_PASSWORD 123456 postgres
```

Diferentes opciones para crear contenedores de postgres en 

https://hub.docker.com/_/postgres

Comandos útiles para manejo de contenedores

```
docker ps (lista de contenedores activos)
docker ps -a (lista de todos los contendores activos o no )
docker rm -f pg (elimina el contenedor llamado pg)
docker logs pg (nos aparece el log del contenedor pg)
```

# DBeaver

Software multiplataforma para tratar con sql. Se puede configurar para acceder a multiples bases de datos. 

# Sobre el script para cargar la base de datos northwind

En este repo github 
https://github.com/pthom/northwind_psql
hay un fichero llamado northwind.sql que contiene el script que hay que ejecutar con un programa como DBeaver.


