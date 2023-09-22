# MongoDB ![MongoDB](.img/logo.png)

# Tabla de contenidos
- [Instalacion y configuracion](#instalacion-y-configuracion)
  - [Windows](#windows)
  - [ArchLInux](#archlinux)
- [Creacion de una base de datos](#creacion-de-una-base-de-datos)
- [Creacion de una coleccion y añadir datos](#creacion-de-una-coleccion-y-añadir-datos)
- [Comprobar las bases de datos existentes](#comprobar-las-bases-de-datos-existentes)
- [Comprobar las colecciones que tiene una base de datos](#comprobar-las-colecciones-que-tiene-una-base-de-datos)
- [Filtrar datos por colecciones](#filtrar-datos-por-colecciones)
- [Eliminar datos de una coleccion](#eliminar-datos-de-una-coleccion)

# Instalacion y configuracion

## Windows
Desde Windows nos dirigimos a la pagina oficial de [MongoDB](https://www.mongodb.com/try/download/community), nos dirigimos a products > comunity server y descargamos dicha version  

Tendremos que crear el directorio "data" y "db", que es donde se almacenaran nuestras bases de datos  

Una vez tengamos listos los directorios, nos dirigimos donde tengamos el ejecutable de mongodb, si lo hemos hehco por defecto estara en "C:\Program Files\MongoDB\Server\7.0\bin\"
```powersehell
cd C:\Program Files\MongoDB\Server\7.0\bin\
```
Y para su ejecucion, ejecutamos mongod.exe
```powersehell
mongod.exe
```
En el caso de que hayamos creado los directorios de data, en una ruta alternativa, ejecutaremos
```powersehell
mongod.exe --dbpath D:/data/db
```
Con esto ya tendremos mongodb ejecutandose en segundo plano, para usarlo, nos dirigimos a la rtua de isntalacion y ejecutamos mongo.exe
```powersehell
mongo.exe
```
Es posible que segun la version no tengamos el ejecutable de mongo.exe, en este caso tendremos que descargar mongo shell para poder trabajar con una interfaz de comandos

## ArchLInux
Instalamos mongodb a traves de los repositorios de aur
```bash
yay -S mongodb-bin
```
```bash
mkdir -p data/db
```
```bash
mongod --dbpath data/db
```
```bash
mongosh
```
Tambien podemos gestionar mongodb con una interfaz grafica con compass
```bash
yay -S mongodb-compass
```

# Creacion de una base de datos
con el comando use podemos acceder a una base de datos, pero tambien nos sirve para crear en caso de que no exista
```javascript
use videojuegos
```

# Creacion de una coleccion y añadir datos
Para que la base de datos exista, necesita tener una coleccion, para la creacion de una coleccion de datos ejecutamos db.nombreColeccion.insertOne() y dentro un objeto json
```javascript
db.ps4.insertOne({titulo: "The Last of Us Part 2", genero: "Aventuras", year: "2020"})
```
Si queremos añadir mas de un elemento a la coleccion podemos usar insertMany
```javascript
db.ps4.insertMany([
  {titulo: "Juego 1", genero: "Aventuras", year: "2021"},
  {titulo: "Juego 2", genero: "Acción", year: "2019"},
  // Agrega más documentos aquí
])
```

# Comprobar las bases de datos existentes
```javascript
show dbs
```

# Comprobar las colecciones que tiene una base de datos
```javascript
show collections
```
Y si queremos visualizar los datos que hay en dicha coleccion
```javascript
db.ps4.find()
```

# Filtrar datos por colecciones
Para buscar un dato de una coleccion, podemos usar el metodo find como si fuera un where en SQL
```javascript
db.ps4.find({year:"2020"})
```

# Eliminar datos de una coleccion
```javascript
db.ps4.deleteOne({year:"2020"})
```
```javascript
db.ps4.deleteMany({year:"2020"})
```