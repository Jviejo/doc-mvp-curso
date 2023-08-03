# Sobre la terminal (1)
===========


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

# Dia 3

## Publicacion en Github y Vercel de proyectos.

## Red IP local

Una red domestica habitualmente tiene la direccion 192.168.1.x y el router (que permite acceder a internet) tiene la direccion 192.168.1.1

El router dispone de un servicio llamado DHCP. Cuando un dispositivo arranca no tiene direccion ip y pide una al servicio DHCP, el cual le da una. Normalmente suele ser la misma, pero no tiene por que

Si tenemos un ordenador dentro de la red domestica que tiene servidores y queremos que se pueda acceder a ellos desde el exterior, tenemos que decirle en el router que a un determinado puerto externo le corresponde un puerto interno.

Por ejemplo si tengo un servidor web en la maquina con ip interna (privada) 192.168.1.69 que esta escuchando (listen) en el puerto 3000. Tendremos que decirle a router en la redireccion de puertos que

el puerto externo 80 es el puerto interno 3000 de la maquina 192.168.1.69.

Por otro lado si queremos que se pueda acceder por nombre de dominio concreto, tendremos que ir al dns y crear una entrada en el mismo que diga que el nombre esta asociada a la ip externa del router (la que nos da el operador de comunicaciones). Hecho esto tendremos la posibilidad de hacer http://nombrednsquehemospuest:puertoexterno y esto lo procesara nuestra maquina interna.

El problema es que cuando se va la luz, algunos operadores cambian la ip externa del router y ya no vale la entrada en el dns que hicimos.

Para solucionar este problema podemos usar en nuestra maquina servidora un contenedor llamado 

docker run \
  -d \
  --name ddns
  -e API_KEY=apikeydecloudflare \ (ver en google keep)
  -e ZONE=kfs.es \
  -e SUBDOMAIN=*.jvh \
  oznu/cloudflare-ddns

Este contenedor actualiza la ip del dns cuando esta cambia.


Si quisiera saber la ip de mi equipo normalmente haria una busqueda en google "cual es mi ip".

Si lo quiero hacer con un programa podria hacer curl ifconfig.me

## ngrok

Hablamos de pasada que si queriamos publicar un servidor en nuestra maquina que estuviera visible para todo el mundo usariamos ngrok.

https://ngrok.com/

El servicio es gratuito hasta un determinado nivel.


## CSS Flex y Grid

Css es la tecnologia para estilizar paginas.

Ya no se usa CSS directamente sino que usamos frameworks entre los que descatan bootstrap y sobre todo tailwind.

Habria que usar tailwind siempre que se pueda. Por otro lado tailwind tiene un servicio de subcripcion de pago unico para toda la vida que permite obtener componentes cuidadosamente disenados para ser usados e html, react o vue.

El servicio esta en https://tailwindui.com/ y las credenciales estan en google keep.

No obstante debemos de conocer la teoria de flex y grid, dos elementos fundamentales en el diseno que van a permitir hacer web responsive.

Para detalles de flex y grid 
https://css-tricks.com/snippets/css/a-guide-to-flexbox/
https://css-tricks.com/snippets/css/complete-guide-grid/

Esta web tiene un monton de detalles sobre css

No es necesario perder mucho tiempo conociendo las bases de flex y grid ya que lo importante son el uso de los componentes de tailwind. (es como el conocimiento de armonia para tocar, es bueno pero no imprescindible)

## proyecto nextjs

Abrimos con el code un directorio vacio en el que con la termminal hacemos yarn init -y

Luego instalamos yarn add react react-dom next

A continuacion creamos una carpeta llamada app (este es el app router) en la que metemos un un fichero llamado page.js (se tiene que llamar asi por el framework)

Ahora dentro del fichero metemos un componente de react (que basicametne es una funcion)

export default function ElNombreQueYoQuiera() {
  return <p>Hola </p>
}


Para ejecutar el proyecto (que es un webserver que proporciona next)

hacemos desde la terminal npx next dev

Esto escucha en el puerto, normalment4e 3000.

Nos vamos a un navegador con http://localhost:3000 y debemos de ver Hola.

## La aplicacion

Se trata de una aplicacion web que sera usada por tres tipos de roles (admin, funcionario, contribuyente)

La aplicacion permitira

1. Sin autenticarse
   Realizar la declaracion de la tasa del 1.5 sin autenticarse
   Pagar la tasa
   Imprimir el pdf con la Tasa
   Enviar por correo el documento de la tasa
2. Autenticado Admin
   Asignar / Quitar roles a usuarios

3. Autenticado Funcionario
   Podra ver todas los contribuyentes y las liquidaciones (les llamamos valores)
   Podra 

4. Autenticado Contribuyente
   Se podra autenticar con certificado digital 
   Podra ver los datos de los recibos suyos y el estado

5. La autenticacion.
   Se debe de permitir la autenticacion por usuario / password para los funcionarios
   La autenticacion para los contribuyente ira por un certificado digital


Otras aplicaciones

1. Simulador de banco
   Aparecera un formulario que pida tarjeta, caducidad, cvc y nombre
   El simulador recibira los datos siguiente
      la referencia
      el importe
      url_ok
      url_ko
  En la simulacion cuando se da cancelar se redigira a la url definida en ko
  Si va bien se redigira a la url defininda el ok.

2. Aplicacion autenticacion con certificado digital !!!ESTO NO LO HEMOS VISTO HOY

  Se trata de una aplicacion web que exija certificado digital de cliente.
  Para ello la web tiene que ser accesible via ssl
  La aplicacion debe de recibir la url de la aplicacion donde hay que redirigir 
  La aplicacion solicitara al usuario un certificado digital (de la gva, fabrica, dni)
  La aplicacion leera el certificado y validara que no ha expirado (no haremos ocsp)
  Si todo el correcto reenviara a la aplicacion origen el subject del certificado
  En el subject es donde estara en cif, el nombre de la empresa (contribuyente)

## EJERCICIOS

1. Usar un proyecto html para familiarizarse con los componentes de tailwind


# Dia 4

## Meter tailwind en nextjs

Esto esta sacado de https://tailwindcss.com/docs/guides/nextjs

Para instalar el tailwind debemos desde el terminal en el directorio del proyecto

```
yarn add tailwindcss postcss autoprefixer -D
```
Luego hacemos 
```
npx tailwindcss init -p
```
que crea el ficheros tailwind.config.js

Vamos al ficheros tailwind.config.js y sustituimos el elemento content con

```
content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",
 
    // Or if using `src` directory:
    "./src/**/*.{js,ts,jsx,tsx,mdx}",
  ],
```

Ahora creamos el fichero globals.css y metemos. Este fichero puede estar en el directorio app

@tailwind base;
@tailwind components;
@tailwind utilities;

Dentro del fichero layout.js importamos el tailwind con el import

import './globals.css'

export const metadata = {
  title: 'Next.js',
  description: 'Generated by Next.js',
}
 
export default function RootLayout({ children }) {
 return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}

# Recapitulacion

El foco es poder realizar un proyecto real con nextjs 13.

Para ello debemos de saber de los siguiente temas:

0. Ir aprendiendo HTML, CSS, JS (PREWORK)
1. Como crear un proyecto nextjs
2. Como crear una ruta (page.js y layout)
3. Crear una funcion de la API
4. Instalar el prisma para crear una base de datos (https://mael.app/blog/nextjs-13-app-directory-prisma-3nnl)
5. Meter datos en la base de datos seed.js.
6. Acceso a datos de un server component de nextjs y renderizar en pantalla.
7. Hacer una funcion del api que acceda a la base de datos.







# Para publicar en vercel ver si tenemos los scripts

Para publicar en vercel debemos de tener el package.json el apartado scripts definido.

```
{
  "name": "nextjs-01",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT",

  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "^13.4.12",
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "autoprefixer": "^10.4.14",
    "postcss": "^8.4.27",
    "tailwindcss": "^3.3.3"
  }
}
```

Vercel usara next build para construir el proyecto. Build el proyecto significa que hara la descarga de las dependencias y empaquetar los elementos algo que no es necesario en dev.

Vercel usara next start para ejecutar el proyecto.

Esto tardara alrededor de 50 segundos.

Lo que va a realizar vercel es levantar un servidor web como el express para realizar las operaciones.

