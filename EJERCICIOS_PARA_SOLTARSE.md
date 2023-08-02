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

# Ejercicios Diseno Tailwind.

1. Componente de lista de productos

2. Componente de presentacion de un producto.

3. Disenar un layout de un ecommerce  con Header, Footer, Menu lateral de Categorias 

# Ejercicios

1. Crea un proyecto nextjs from scratch usando el app router con dos pagina Home About

2. Crea un proyecto nextjs from scratch y anadele despues tailwind. 

3. Crear proyectos con npx create-next-app@latest nextjs-prueba1 y dar diferentes respueste para ver lo que hace. Ojo que no tengan errores. Probar que funcionan. Dar un vistazo a los ficheros y luego borralos.

4. Crear un proyecto nextjs con typescript, tailwind  e instalar prisma. Prisma debe de usar sqlite. Seguir esta guia https://mael.app/blog/nextjs-13-app-directory-prisma-3nnl. (Puede haber otras guias). La idea es soltarse con el concepto de ORM usando el modulo prisma.

5. Crea un contenedor de postgres que escuche en el puerto 5454. Metele la base de datos northwind usando el cliente dbeaver.

6. Crear un proyecto en Github llamado borrame. Clonarlo en tu local. Borrarlo al final

7. Crear un proyecto en Github llamado borrame. En local con vscode inicializar un repositorio y meterle como url remota la del proyecto github.

8. Hacer un proyecto nextjs y publicarlo en vercel.

9. Modificar el proyecto anterior y actualizar vercel. Asignar un dominio propio a el dominio. Comprobar que se crea el certificado de servidor.

10. Crear un base de datos RDS postgres en AWS y conectarla con una aplicacion nextjs

11. Crear una mquina EC2 en AWS y crear un proyecto en dicha maquina usando VSCODE y SSH.

12. Crear un componente products en un proyecto reactjs. El componente debe sacar un card por cada producto en el que aparezca una foto, un nombre. Para hacer esto tenemos que crear una base de datos de productos sqlite que tenga una tabla products. Usar los datos de ejemplo de https://diviengine.com/woocommerce-sample-products-csv-import-file-freebie/

13. Generar ficheros csv a partir de las tablas de la base de datos northwind, un fichero por tabla.

14. Importar datos en formato csv a una base de datos. 
    * https://sample-videos.com/download-sample-csv.php#google_vignette
    * https://www.datablist.com/learn/csv/download-sample-csv-files#people-dataset

16. Hacer una pull request a un repositorio.

17. En un router domestico redireccionar un puerto externo a uno interno.

18. Hacer un servidor web seguro. Usar ngrok para publicarlo en nuestro local.