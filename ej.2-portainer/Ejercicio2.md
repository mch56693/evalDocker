# Ejercicio 2 - Portainer

> Hecho por: Álvaro Fernández 
> Fecha de creación: 19 de Febrero de 2024 - 10:21

[TOC]

------

#### Enunciado

Utiliza una imagen de 'Portainer' para gestionar Docke. Documenta la aplicación, su puesta en funcionamiento y realiza capturas de varias operaciones, por ejemplo:

- Muestra contenedores activos, para un contenedor, borra un contenedor
- Muestra alguna operación con redes Docker
- Muestra alguna operación con volúmenes Docker



------

#### Capturas de Pantalla



- (1)

```bash
$ docker run -d -p 9000:9000 --name portainer -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```

![ej1](./E2 - Imagenes/ej1.png)



- (2)

![ej2](./E2 - Imagenes/ej2.png)



- ##### Muestra contenedores activos, para un contenedor, borra un contenedor

![ej3](./E2 - Imagenes/ej3.png)

![ej3.1](./E2 - Imagenes/ej3.1.png)

![ej3.2](./E2 - Imagenes/ej3.2.png)

![ej3.3](./E2 - Imagenes/ej3.3.png)

![ej3.4](./E2 - Imagenes/ej3.4.png)

![ej3.5](./E2 - Imagenes/ej3.5.png)



- ##### Muestra alguna operación con redes Docker

  - Crear una red

    ![ej4](./E2 - Imagenes/ej4.png)

    ![ej4.1](./E2 - Imagenes/ej4.1.png)

    

  - Consultar detalles de red

    ![ej4.2](./E2 - Imagenes/ej4.2.png)

    

  - Borrar una red

    ![ej4.3](./E2 - Imagenes/ej4.3.png)

​		

- ##### Muestra alguna operación con volúmenes Docker

  - Crea un volumen

    ![ej5](./E2 - Imagenes/ej5.png)

    ![ej5.1](./E2 - Imagenes/ej5.1.png)

    

  - Consulta detalles de volumen

    ![ej5.2](./E2 - Imagenes/ej5.2.png)

    

  - Elimina un volumen

    ![ej5.3](./E2 - Imagenes/ej5.3.png)

    ![ej5.4](./E2 - Imagenes/ej5.4.png)
