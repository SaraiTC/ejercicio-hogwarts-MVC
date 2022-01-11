# APP con Modelo Vista Controlador

Siguiendo el tutorial: https://www.jairogarciarincon.com/clase/creacion-de-un-cms-desde-cero-con-patron-mvc

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

10. Creación de contacto.php para crear una nueva página dentro de la APP y modificación del archivo header.php para incluir la página en el menú de navegación.

11. En AppController.php creamos la función:
    
     public function contacto(){

        //Llamo a la vista
        $this->view->vista("app", "contacto");

    }

12. En el index.php contenido en public añadimos lo siguiente:
    
    switch ($ruta){

    //Front-end
    case "":
    case "":
        controller()->index();
        break;
    case "acerca-de":
        controller()->acercade();
        break;
    case "contacto":
        controller()->contacto();
        break;
    case "noticias":
        controller()->noticias();
        break;
    case (strpos($ruta,"noticia/") === 0):
        controller()->noticia(str_replace("noticia/","",$ruta));
        break;

para crear el caso que se ejecuta cuando la persona usuaria clicka en el apartado Contacto del Header.

13. Finalmente, ejecutamos el ejercicio con Laragon y ¡ya tenemos nuestra página!

## Capturas

![Home](https://i.ibb.co/dr3gbHC/Fire-Shot-Capture-023-Noticias-de-Harry-Potter-ejercicio-mvc-test.png)
![Noticias](https://i.ibb.co/Js0YT5j/MVC-HP-02.png)
![About](https://i.ibb.co/rmTbmcW/MVC-HP-03.png)
![Admin](https://i.ibb.co/8N9qnMt/MVC-HP-04.png)


    