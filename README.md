# Bienvenidos

##### Este es un README para el proyecto de desarrollo.

###### Instalación.
Una vez tengamos el archivo ***package.json*** debemos instalar las dependencias de producción que utilizaremos en el proyectos, las cuales son:
- ***npm i express*** la cual sirve para es un framework de Node para que podamos enviar respuestas y recibir peticiones.
- ***npm i morgan*** esta sirve para poder visualizar en consola las peticiones que van llegando.
- Instalaremos el modulo principal el cual es ***npm i sequelize***  pero debido a que este funciona con distintas bases de datos nos pide que instalemos modulos relacionados con esa base de datos. La cual yo utilice fue PostgreSQL por lo tanto instale el modulo ***npm i pg pg-hstore*** 

###### Estructura principal.
Crearemos una carpeta llamada *src* la cual trandra los archivos principales de nuestro proyecto, los principales que nosotros necesitaremos para correr la aplicacion seran ***index.js*** el cual se encargara de arrancar nuestra aplicación, mientras que ***app.js***  es quien trendra la configuración de ***express***.

Para poder utilizar **import** y **export** debemos agregar una propiedad en nuestro archivo principal ***package.json*** el cual es 

    "type": "module"

> Nota, los archivos creados por nosotros para poder importarlos se tienen que importar con la extencion .js, ejemplo "import app from './app.js'"

Para poder ejecutar nuestro proyecto seria de la siguiente manera.
***node src/index.js***

###### Conexion de base de datos.
Para ejecutar la conexion de sequelize debemos hacer:
```json
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: /* one of 'mysql' | 'postgres' | 'sqlite' | 'mariadb' | 'mssql' | 'db2' | 'snowflake' | 'oracle' */
});
```

Dentro de una carpeta llamada *models*  crearemos un nuevo archivo llamado ***pets.js***  el cual es el que vamos a conectar con **sequelize** y por este medio crearemos la tabla que utilizaremos.

Luego crearemos un archivo llamado ***pets.routes.js*** en una carpeta llamada *routes*  en el cual definiremos cuando queremos hacer una consulta, agregar una mascota o eliminar una mascota.

En la carpeta *controller* vamos a crear un archivo llamado ***pets.controller.js*** donde podremos poner las peticiones que necesitamos, como consulta, agregar o crear y eliminar, luego de eso lo exportaremos al archivo de ***pets.routes.js*** el cual es el que esta conectado directamente con express y nos permitira recibir y enviar las peticiones.