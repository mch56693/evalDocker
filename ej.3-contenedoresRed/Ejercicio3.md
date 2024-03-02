# Ejercicio 3 - Contenedores de Red

> Hecho por: Álvaro Fernández 
> Fecha de creación: 19 de Febrero de 2024 - 10:21

[TOC]

------

#### Enunciado

1. Crea una red bridge redbd
2. Crea un contenedor con una imagen de mariaDB que estará en la red redbd . Este contenedor se
    ejecutará en segundo plano, y será accesible a través del puerto 3306. (Es necesario definir la
    contraseña del usuario root y un volumen de datos persistente)
3. Crear un contenedor con Adminer que se pueda conectar al contenedor de la BD
4. Comprobar que el contenedor Adminer puede conectar con el contenedor mysql abriendo un
    navegador web y accediendo a la URL: http://localhost:8080

------

#### Proceso

- (1)

```bash
$ docker network create --driver bridge redbd
```

![ej1](./E3-Imagenes/ej1.png)



- (2) - mariadb

```bash
$ docker run -d --name mariadb --network nombre_red -p 3306:3306 -e MYSQL_ROOT_PASSWORD=1234 -v mariadb_data:/var/lib/mysql mariadb
```

![ej2](./E3-Imagenes/ej2.png)



- (3) - adminer

```bash
$ docker run -d --name adminer --network nombre_red -p 8080:8080 adminer
```

![ej3](./E3-Imagenes/ej3.png)



- (4)

  ![ej4](./E3-Imagenes/ej4.png)





------

#### Capturas de Pantalla

- Captura de pantalla y documento donde se vean los contenedores creados y en ejecución

  ```bash
  $ docker ps
  ```

  ![ej5](./E3-Imagenes/ej5.png)

  

- Captura de pantalla y documento donde se vea el acceso a la BD a través de la interfaz web de Adminer 

  ![ej6](./E3-Imagenes/ej6.png)

  

- Captura de pantalla y documento donde se vea la creación de una BD con la interfaz web Adminer

  ![ej7](./E3-Imagenes/ej7.png)

  ![ej7.1](./E3-Imagenes/ej7.1.png)

  

- Captura de pantalla y documento donde se entre a la consola del servidor web en modo texto y se compruebe que se ha creado la BD

  ```bash
  $ docker exec -it mariadb /bin/bash
  # mariabd -u root -p
  ```

  ```php
  > show databases;
  ```

  ![ej8](./E3-Imagenes/ej8.png)

  

- Borrar los contenedores la red y los volúmenes utilizados

  ```bash
  $ docker rm adminer
  $ docker rm mariadb
  ```

  ![ej9](./E3-Imagenes/ej9.png)