# Help to the ocean
Proyecto fullstack desarrollado en el hackaton Hack the ocean de innovacción virtual



![gifH20](https://user-images.githubusercontent.com/89043553/168487473-afdc8688-3bb7-4115-83db-2e222a2474e4.gif)

## Introducción

### Reto:

Elaborar un proyecto web (fullstack) que de solución escalable y ágil a una problemática relacionada con los océanos, utilizando, las tecnologías, marcos de trabajo y metodologías revisadas en Launch X.

### Tema seleccionado:

Especies marinas en peligro de extinción / contaminación marítima.​

## Contenido: 📋
---
- [Dependencias de desarrollo](#id1)
- [Propuesta de solución)](#id2)
- [Solución Frontend](#id3)
- [Solución Backend](#id4)
- [Autores](#id5)

<div id='id1' />

## Dependencias de desarrollo, herramientas, tecnologías y links a repositorios 🛠️
| |Tecnologías|
|------|------|
|1| [HTML](https://developer.mozilla.org/es/docs/Web/HTML)|
|1| [CSS](https://developer.mozilla.org/es/docs/Learn/Getting_started_with_the_web/CSS_basics)|
|1| [VUE3](https://vuejs.org/)|
|1| [Node js](https://nodejs.org/en/)|


| |Dependencia|
|------|------|
|1| [Prisma](https://www.prisma.io/)|
|2| [Express](http://expressjs.com/)|
|3| [Eslint](https://eslint.org/)|
|4| [Cosr](https://www.npmjs.com/package/cors)|

| |Base de datos|
|------|------|
|1| [PostgreSQL](https://www.postgresql.org/)|

|Repositorio|Link|
|------|------|
|Diseño y prototipado de la solución| [FIGMA](https://www.figma.com/file/dmR2q94fjEHWluk2vyVlVG/H2O-Mexico?node-id=11%3A164)|
|Repositorio de Frontend| [Frontend](https://github.com/Gera097/H2O_client)|
|Repositorio de Backend| [Backend](https://github.com/harold-barron/H2O-Backend)|
|Explicación en Tiktok| [TikTok](https://vm.tiktok.com/ZMLc3MGcA/?k=1)|

<div id='id2' />

##  Propuesta de solución 

### Crear una plataforma que permita la conexión de activistas ambientales. Dicha plataforma ayudará a concientizar sobre las actividades que se pueden realizar como individuos e incentivará la creación y la participación de eventos que ayuden a la flora y fauna del océano.

![P11](https://user-images.githubusercontent.com/73314870/168504456-50e6486a-c63f-4b44-81e9-84c87d1f551c.PNG)

![P22](https://user-images.githubusercontent.com/73314870/168504457-78481a3d-decb-4fb7-8127-4d1dda7ae0f0.PNG)

![P1](https://user-images.githubusercontent.com/73314870/168504471-7b49a1bf-118d-4921-8b87-36fb97f417bb.PNG)

![P2](https://user-images.githubusercontent.com/73314870/168504472-ee3f1ba6-0711-4f20-9fd4-2fcdd18cbfdb.PNG)

![p3](https://user-images.githubusercontent.com/73314870/168504474-0778d917-100f-4f43-a5d2-3f6a0c6aaff6.PNG)

![P4](https://user-images.githubusercontent.com/73314870/168504477-a045345b-18ed-4737-8d45-8a2ae9ca5b51.PNG)

![P5](https://user-images.githubusercontent.com/73314870/168504479-b8b16da8-797c-403b-9670-dc986aeb9ce8.PNG)

![P6](https://user-images.githubusercontent.com/73314870/168504468-ae897b18-0686-446c-ae5c-89c6d5c9332c.PNG)




<div id='id3' />

## Solución Frontend

### Enlance a la solución:

https://gera097.github.io/H2O_client/


<div id='id4' />

## Solución Backend

### 1. Creación de una base de datos en PostgreSQL:

#### 1.1. Hacemos login con el usuario creado en la instalación de PostgreSQL:

![LoginPostgreSQL](https://user-images.githubusercontent.com/73314870/168500573-fac6b09e-5f00-4a76-a7f0-7cdff983e39c.PNG)

#### 1.2. Creamos la base de datos con el comando create database <nombre de la base a crear>;

![CreateDB](https://user-images.githubusercontent.com/73314870/168500703-fd245c9c-cc0b-4e97-9cf0-56ae83d65017.PNG)

#### 1.3. Revisamos que la tabla ha sido creada correctamente con \l

![backslashl](https://user-images.githubusercontent.com/73314870/168500773-99714441-87fd-498f-bf19-90fe08b293c8.PNG)

### 2. Creación del API:

#### 2.1  Inicializamos un nuevo proyecto de JS e instalamos las dependencias de Prisma DB y Express
  
  | |Comandos|
|------|------|
|JS| npm init|
|Express|npm install express --save-dev|
|Prisma DB|npm install prisma --save-dev|
|Prisma DB|npx prisma init (Inicialización de prisma)|
  
#### 2.1 Modificamos el archivo .env creado con el usuario,contraseña  y nombre de la base de datos
  
![url](https://user-images.githubusercontent.com/73314870/168501393-a977489c-b187-494a-8b53-9fa514107d2c.PNG)

#### 2.2 Declaramos un nuestros modelos para las tablas en prisma/schema.prisma
  
  ![schema1](https://user-images.githubusercontent.com/73314870/168501621-000f54fb-9a8b-468d-b33a-ca97bd356b5c.PNG)

  ![schema2](https://user-images.githubusercontent.com/73314870/168501626-0c8739b4-6101-421b-990b-dd4138594527.PNG)

#### 2.3 Versionamos nuestros cambios utilizando npx prisma migrate dev --name init

  
#### 2.4 Creamos los archivos seed.js para llenar cada uno de nuestros modelos
  
  ![seeds](https://user-images.githubusercontent.com/73314870/168501792-a1a78d08-31b1-482f-a8b2-25137638f513.PNG)

#### 2.5 Automatizamos los datos de la db en los archivos seed<nombre del modelo>.js
  
  Ejemplo de automatización para el llenado de la tabla user:
  
  [seedUser](https://user-images.githubusercontent.com/73314870/168501877-8058e2d0-e781-4beb-b7c6-9c99b6ca3be2.PNG)
  
#### 2.5 Corremos el archivo con el comando node prisma/seeUser.js para cada uno de los archivos creados y verificamos que las tablas fueron llenadas
  
### 3. CRUD
  
  #### Creamos un archivo llamado server.js y agregamos el cliente de prisma 

  ![crud](https://user-images.githubusercontent.com/73314870/168502090-179766c4-8f7b-45b9-8dcd-85ab03c6f552.PNG)

### 4. API CRUD:
  
  #### Creamos los endpoints necesarios (get,put,post,delete)
  
  ##### Ejemplo de enpoints para Users
  
  ![EPUSers1](https://user-images.githubusercontent.com/73314870/168502274-47a58c91-dd1c-4100-bfa8-103c7339af22.PNG)
  
  ![EPUSers](https://user-images.githubusercontent.com/73314870/168502275-3d3b91e2-2e4f-4540-8bdf-17f368676fd3.PNG)

### 5. Automatización de pruebas con Postman:
  
  #### Probamos el api corriendo el archivo server.js con node server.js, la url del api es : http://localhost:3000/Animal y http://localhost:3000/Users/
  
  #### Probamos los endpoinds con Postman:
  
  ![PostmanAnimals](https://user-images.githubusercontent.com/73314870/168502644-87d9b4c4-7ce2-4be4-ac2d-401c5f37b4c5.PNG)

  #### Colecciones de postman:
 
  [Postman_Collections.zip](https://github.com/harold-barron/Help-to-the-ocean-/files/8696469/Postman_Collections.zip)


<div id='id5' />

## Autores ✒️

* **Gerardo Sanchez Alba** - *Frontend* - [Gera097](https://github.com/Gera097)
* **Harold Alejandro Barron Perez** - *Backend y documentación* - [harold-barron](https://github.com/harold-barron)
* **Eugenio Torres García Luna** - *Direccion Creativa* - [Eugenio-tgl](https://github.com/Eugenio-tgl)
* **Ernesto Botello Barron** - *Documentación* - [ErnestoBotello](https://github.com/ErnestoBotello)

