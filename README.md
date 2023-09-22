# MongoDB ![MongoDB](.img/logo.png)

# Tabla de contenidos

# Instalacion y configuracion

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