# Objetivos

Es importante adquirir habilidad en la creación de proyectos e instalación de paquetes.

Hay que tener en cuenta que usamos muchas cosas y que cualquier cosa nos puede dar un  problema, que a veces es por incompatibilidad de los packages que usamos.

Como leemos poco, es posible que no nos demos cuenta de los errores que tenemos cuando instalamos algo.

Como regla general hasta conseguir ser consistente en necesario es cuidadoso.

Tambien si vemos un problema y se nos ha hecho bola, empezamos de cero. De esta manera podremos ver el error.

El centro del aprendizaje esta alrededor del nextjs version 13. Ojo cuando leamos doc de nextjs ya que es posible que nos hable de otra version y no nos demos cuenta.

La version 13 ha cambiado el Router (que es el elemento central de NextJS). Este se encuentra situado en el directorio app. Se le llama app router en la docu.

Aunque el lenguaje basico es Javascript hay que intentar pasar cuanto antes a Typescript. Este es un superset de javacsript (cualquier codigo javascript es valido en TypeScript).

Typescript es trending y ademas hace que el programador cometa menos errores. Tambien permite tener intellisense en los objetos y estos hace que te sugiera el editor y esto facilita el trabajo.

En cuanto a la base de datos vamos a usar una base de datos SQL. Pero para el acceso vamos a usar una tecnologia llamada ORM (Object Relationship Management) que permite realizar operaciones de base de datos a traves de los objetos. Esto va a evitar los clasicos errores escribiendo SQL. Hay varios ORM disponibles en javascript y hemos elegido Prisma ya que alguno habia que elegir. Tambien es uno de los mas modernos y suficiente para el trabajo.

Prisma puede trabajar con base de datos SQL (sqlite, pg, mysql, ..) y bases de datos non SQL como Mongo.

Es bueno realizar proyectos from scracth ya que estos te dan una idea de que componentes hay que instalar y demas, pero no es practico. En realidad hay que usar programas que nos crean el proyecto con las caracteristicas que queramos. 

Vercel que es el que mantiene el proyecto nextjs dispone de templates que nos permite empezar con un proyecto con paginas.


El comando para crear un proyecto nextjs que nos hara ciertas preguntas es

npx create-next-app@latest nextjs-prueba1

nos preguntara si queremos typescript, tailwind, eslint (validador de codigo)
si queremos que meta lo generado en el directorio src
si queremos usar App router (las caracteristicas de la 13)


# Ejercicios

1. Crear proyectos con npx create-next-app@latest nextjs-prueba1 y dar diferentes respueste para ver lo que hace. Ojo que no tengan errores. Probar que funcionan. Dar un vistazo a los ficheros y luego borralos.

2. Crear un proyecto nextjs con typescript, tailwind  e instalar prisma. Prisma debe de usar sqlite. Seguir esta guia https://mael.app/blog/nextjs-13-app-directory-prisma-3nnl. (Puede haber otras guias). La idea es soltarse con el concepto de ORM usando el modulo prisma.


