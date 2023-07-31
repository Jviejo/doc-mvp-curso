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

# Alta en Github, Vercel, AWS

Nos damos de alta en los servicios de Github, Vercel (publicación de web) y AWS

# Javascript intro

Introducción a la programación javascript con nodejs

Creamos un directorio llamados js en el que vamos a meter los programas

Para ejecutar un programa hacemos desde la terminal de vscode

Para que aparezca una terminal en vscode 

Ctrl + Shift + `

O tambien con la opción del menu Terminal -> New Terminal


```
npx nodemon <nombreprograma>
```

El programa se ejecuta cada vez que cambiamos algo

Shortcut que hemos visto

```
Ctrl + ` (teclado ingles mac)
Ctrl + < (teclado spanish mac)
Option + Shift + F (formatea el código)
Cmd + S (Save del fichero)
Cmd + Shift + S (Save all files cambiado)
Cmd + B (oculta o muestra la ventana del arbol de ficheros)
```
# Tipos de entornos WEB (Dia 2)

## Server render 
El servidor accede a base de datos y genera todo el html 
necesario que envia al browser

Tecnologas de server render:

1. nodejs + express + templates 
2. php
3. asp.net (c#)
4. java
5. django (python)
6. flask (python)
7. Rubi on Rails
8. y muchos mas en todos los lenguajes

## SPA (Single Page Application)

Nada mas arrancar la aplicacion se envia una pagina al cliente que contiene el javascript necesario para ejecutar la aplicacion.

Estos entornos estan compuestos por dos proyectos bien diferencias: un front y un back.

El back recibe peticiones del front y basicamente realiza transacciones contra una base de datos. El back accede a base de datos y devuelve los resultado normalmente en formato JSON. Al back se le llama API (Aplication Programing Interface). 

Hay varias tecnologias para hacer API entre las que destacan API REST y GRAPHQL (facebook)

En cuanto al front destacan las siguientes tecnoloigias

1. React
2. Angular
3. Vue
4. Svelte
5. Astro

Hay diferentes tecnologias que tienen nombres cuyas iniciales identifican los elementos mas importantes

1. MERN (Mongo Express React Node)
2. LAMP (Linux Apache MySql Php)
3. MEAN (Mong Express Angular Node)

# Bases de datos

Existen diferentes tipos de bases de datos entre las que estan

1. Bases de datos SQL (Postgres,MariaDb (igual a mysql) Mysql, Oracle, SqlServer (microsoft), sqlite (se suele usar en móviless))
2. Bases de datos Non SQL (Mongo, CouchDB)
3. Bases de datos Key/Value entre las que destacan RocksDB, LevelDB (ethereum)

# El servidor WEB

Un servidor web escucha (listen) en un puerto. En producción escuchan en el 443 cuando van por https.

El http, que escuchaba por defecto en el 80 ahora esta desaconsejado en el navegador. Google da avisos de seguridad si se accede por http en vez de por https.

El servidor web escucha peticiones (request) y devuelve (response).

Métodos usados en la peticiones (los comunes son GET y POST)
POST para formularios y subidas de ficheros
Detalles en:
https://developer.mozilla.org/es/docs/Web/HTTP/Methods


En las response viene el status code que indica como ha ido la peticion

2xx (success)
3xx (redirect)
4xx (client error)
5xx (server error )

Relación de statusCode
https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

Tanto en las peticiones como en la respuesta hay unos headers que indican cosas como

1. tipo de contenido Content-Type
2. Content-Length

Una lista de los headers tenemos en https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

Las reponses vienen con un content-type que permite al navegador interpretar el contenido. 

Algunos ejemplos:

application/json
application/pdf
text/html
text/javascript

Una lista de contenidos 
https://www.iana.org/assignments/media-types/media-types.xhtml


# Renderizado de una pagina en el navegador.

Cuando la pagina generada en el servidor llega al navegador, este interpreta el texto del html y empieza a interpretar el contenido renderizando (pitando) el contenido en pantalla. 

Es muy posible que la pagina lleve imagenes, videos, javascript y otros contenidos. En este caso se iran descargando y pintando hasta que esten todos. Es por eso que las paginas tienen una demora hasta que estan completas.

El protocolo de acceso del navegador es el http, el cual tiene a dia de hoy varias versiones http 1.0 http 1.1 http2 (optimiza la comunicacion) http3 (usado por google)

# Herramientas de desarrollador en Navegadores

Con la funcion F12 (fn+F12 en mac), aparece una ventana en el navegador que son muy utiles para ver como estan construidas las paginas.

Tambien si pinchamos en un punto de una pagina con inspect (boton derecho, inspect) podemos acceder al html del elemento seleccionado. Esto nos permite aprender como esta hecho un determinado elemento.

# Node JS y Express. 

Express es una servidor muy usado para la construccion de web y apis.

Pasos para construir un servidor web express.

1. Crear un direcorio.
2. Abrir directorio con VSCODE
3. Abrir una terminal dento de VSCODE (Menu->Terminal->New Terminal)
4. Desde la terminal yarn init -y (esto crea el fichero package.json)
5. yarn add express (esto instala el express. Crea el directorio node_modules y mete los componentes de express)
6. Crear un fichero nuevo con el editor vscode llamado app.js (puede llamarse como se quira)
7. Escribir el siguiente codigo
  ```
  // el siguiente servidor escucha en 3333 y responde hola cuando 
  // en el navegador se accede con http://localhost:3333

  const express = require("express")
  const app=express()
  app.listen(3333) // el servidor escucha en el puerto 3333
  app.get("/", (req, res) => {
    res.send("hola")
  })
  ```

# Terminal history

