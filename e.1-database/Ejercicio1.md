# Ejercicio 1 - Base de Datos

> Hecho por: Álvaro Fernández 
> Fecha de creación: 19 de Febrero de 2024 - 10:18

[TOC]

------

#### Enunciado

- Arrancar un contenedor que se llame bbdd y que ejecute una instancia de la imagen mariadb para que sea accesible desde el puerto 3306.
- Antes de arrancarlo visitar la página del contenedor en Docker Hub y establecer las variables de entorno necesarias para que:
  - La contraseña de root sea root .
  - Crear una base de datos automáticamente al arrancar que se llame prueba .
  - Crear el usuario invitado con la contraseña invitado.

------

#### Proceso

- (1)

  ```bash
  $ docker run -d --name bbdd -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=prueba -v MYSQL_USER=alvaro -v MYSQL_PASSWORD=alvaro1234
  ```

  ![ej1](./E1 - Imagenes/ej1.png)

  

- (2)

  ```bash
  $ cd ProyectoEval/Database
  $ nano index.html
  ```

  ![ej2](./E1 - Imagenes/ej2.png)



- (3)

  ```bash
  $ cd ProyectoEval/Database
  $ nano mes.php
  ```

![ej3](./E1 - Imagenes/ej3.png)



- Captura de pantalla y documento que desde el navegador muestre el fichero index.html.

  ![ej4](./E1 - Imagenes/ej4.png)

  

  

- Captura de pantalla y documento que desde un navegador muestre la salida del script mes.php

  ![ej5](./E1 - Imagenes/ej5.png)

  

- Captura de pantalla y documento donde se vea el tamaño del contenedor web después de crear los dos ficheros.

  ```bash
  $ docker ps -s
  ```

  ![ej6](./E1 - Imagenes/ej6.png)

  

- Captura de pantalla y documento donde desde un cliente de base de datos (instalado en tu ordenador) se pueda observar que hemos podido conectarnos al servidor de base de datos con el usuario creado y que se ha creado la base de datos prueba ( show databases ). El acceso se debe realizar desde el ordenador que tenéis instalado docker, no hay que acceder desde dentro del contenedor, es decir, no usar docker exec.

  ![ej7](./E1 - Imagenes/ej7.png)

  

- Captura de pantalla y documento donde se comprueba que no se puede borrar la imagen mariadb
  mientras el contenedor bbdd está creado.

  ```bash
  $ docker rmi mariadb
  ```

  ![ej10](./E1 - Imagenes/ej10.png)
