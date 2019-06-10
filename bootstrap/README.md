# Bootstrap

## Qué es?

Es un framework para front-end, ayuda a construir sitios mobile responsive mas rápido y fácil.

Fue creado por Twitter por un pequeño grupo de desarrolladores para crear interfaces web consistentes, el proyecto fue creciendo hasta que decidieron hacerlo público en 2011. Está entre las herramientas mas usadas para desarrollo web, entre otras cosas, es el segundo proyecto con mas estrellas en Github.com

En programación, un framework podría verse como una librería. Contiene herramientas, partes y una funcionalidad existente que podemos usar para realizar tareas estándares de manera rápida y fácil.  En el caso de Bootstrap, esas tareas estándar son crear patrones de diseño tales como formularios, menus, columnas, bottones y otros componentes útiles para desarrollar nuestros sitios web.

Nos ayuda al ofrecer un gran número de clases que podemos aplicar a los elementos HTML para crear los componentes que necesitemos. Podemos diseñar páginas complejas desde el estándar de HTML y adaptarla a nuestra medida. Además viene con funcionalidad adicional y plugins de Jquery que preveen funcionalidad adicional tal como carruseles, botones, tooltips y mas.


## Configuración

Existen dos posibilidades para cargar Bootstrap:

1. De manera remota

2. Descargo y lo uso localmente.

### Crear una página HTML

Como primer paso crearemos una página HTML como base para Bootstrap. 

```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <title>Bootstrap Tutorial Sample Page</title>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1">
    </head>
    <body>
    </body>
    </html>

```

1a. Cargar a través de la CDN de Bootstrap.

   Como Bootstrap consiste en hojas de estilos y scripts, pueden ser cargados en el head de mi documento HTML, en la web de [Bootstrap](https://getbootstrap.com/docs/4.2/getting-started/download/)

   Esta forma tiene la ventaja de que esta versión puede estar cargada en la caché del navegador lo que hace que cargue mas rápido.

```html
 <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS" crossorigin="anonymous">
```

1b. Cargar localmente

```html
    <link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
```
La ventaja que presenta es que si se corta internet no voy a tener problemas porque está cargado localmente.

2. Incluir Jquery

```html
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/js/bootstrap.min.js" integrity="sha384-B0UglyR+jN6CkvvICOB2joaf5I4l3gm9GU6Hc1og6Ls7i6U/mkkaduKaBhlAXv9k" crossorigin="anonymous"></script>
```

Alternativamente podemos descargarlo y usarlo localmente

    <script src="jquery-3.3.1.min.js"></script>

3. Cargar JavaScript

Al contrario de la llamada a las hoja de estilos que van en en head, el llamado lo hacemos desde el footer

    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>

O localmente

    <script src="bootstrap/js/bootstrap.min.js"></script>


## Todo junto

```html
    <!DOCTYPE html>
    <html lang="en">
      <head>

        <title>Bootstrap Tutorial Sample Page</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
      </head>
    <body>
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
    </body>
    </html>
```

Alternativamente si estamos hosteando localmente
```html
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <title>Bootstrap Tutorial Sample Page</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
      </head>
    <body>
    <script src="jquery-3.3.1.min.js"></script>
    <script src="bootstrap/js/bootstrap.min.js"></script>
    </body>
    </html>
```

## Diseña tu landing page

1. Agregamos una barra de navegación

    1a. Usaremos la clase **navbar**, es uno de los elementos por defecto de Bootstrap, crea un elemento de navegación responsivo por defecto y colapsará automaicamente en pantallas mas pequeñas, también ofrece soporte para marcas, colores, espaciado y otros componentes.

    Agregamos el siguiente código luego de la etiqueta ```<body>```

    ```
      <nav class="navbar navbar-expand-md">
      <a class="navbar-brand" href="#">Logo</a>
      <button class="navbar-toggler navbar-dark" type="button" data-toggle="collapse" data-target="#main-navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="main-navigation">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Contact</a>
          </li>
        </ul>
      </div>
    </nav>
    ```
    Explicaciones:
    * navbar-expand-md - Muestra a qué punto la barra de navegación se expande desde vertical o ícono hamburguesa a una barra horizontal de todo el ancho, la seteamos a _medium_ que para bootstrap es cualquier cosa mayor a 768px.
    * navbar-brand - Se usa para la marca del sitio web, podemos incluir una imagen para el logo.
    * navbar-toggler - El botón expansivo para el menú colapsado. Este código ```data-toggle="collapse"``` define que será un menú hamburguesa, no un desplegable que es otra opción. Es importante definir un ```data-target``` que es un id CSS (definido por el #)  y envuento en un div con el mismo nombre alrededor del actual elemento navbar
    * navbar-toggler-icon - Permite agregar íconos de usuario para abrir el menú en pantallas mas pequeñas.
    * navbar-nav - La clase para el elemento que contiene todos los ítems del menú ```<ul>```, los elementos que contiene son nav-item y nav-link.



