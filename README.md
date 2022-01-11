# APP con Modelo Vista Controlador

## Pasos

1. En la terminal de Laragon creamos las carpetas del proyecto, atomizando cada una de las partes del mismo.
   
2. Creamos una Base de Datos con MySql.
   
3. Introducimos contenido en la BBDD:
   
   a) TABLA USUARIOS

    USE cms;
    CREATE TABLE `usuarios` (
    `id` int(3) NOT NULL AUTO_INCREMENT,
    `usuario` varchar(16) NOT NULL,
    `clave` varchar(64) NOT NULL,
    `fecha_acceso` datetime DEFAULT NULL,
    `activo` tinyint(1) NOT NULL DEFAULT '0',
    `usuarios` tinyint(1) NOT NULL DEFAULT '0',
    `noticias` tinyint(1) NOT NULL DEFAULT '1',
    PRIMARY KEY (`id`),
    UNIQUE KEY `usuario` (`usuario`),
    UNIQUE KEY `id` (`id`)
    ) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;

    b) TABLA NOTICIAS
    
    USE cms;
    CREATE TABLE `noticias` (
    `id` int(3) NOT NULL AUTO_INCREMENT,
    `titulo` varchar(32) NOT NULL DEFAULT '',
    `slug` varchar(36) DEFAULT '',
    `entradilla` varchar(128) DEFAULT '',
    `texto` longtext,
    `activo` tinyint(1) NOT NULL DEFAULT '0',
    `home` tinyint(1) NOT NULL DEFAULT '0',
    `fecha` datetime DEFAULT NULL,
    `autor` varchar(64) DEFAULT NULL,
    `imagen` varchar(64) DEFAULT NULL,
    PRIMARY KEY (`id`),
    UNIQUE KEY `id` (`id`)
    ) ENGINE=InnoDB AUTO_INCREMENT=1 DEFAULT CHARSET=utf8;

4. Asimismo, introducimos contenido en la tabla de noticias usando la terminal de Laragon.

5. Creación de un archivo PHP para obtener el hash de las contraseñas.

6. Añadimos el contenido de los componentes del header y del footer.

7. Añadimos contenido al index.php dentro de view/app.

8. Añadimos contenido a acerca-de, noticia y noticias.
   
9. Añadimos una entrada extra a la sección de noticias utilizando php/myadmin.

10. Finalmente, ejecutamos el ejercicio con Laragon y ¡ya tenemos nuestra página!

## Capturas

![Home](https://i.ibb.co/dr3gbHC/Fire-Shot-Capture-023-Noticias-de-Harry-Potter-ejercicio-mvc-test.png)
![Noticias](https://i.ibb.co/Js0YT5j/MVC-HP-02.png)
![About](https://i.ibb.co/rmTbmcW/MVC-HP-03.png)
![Admin](https://i.ibb.co/8N9qnMt/MVC-HP-04.png)


    