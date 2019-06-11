# Bootstrap

## Qu� es?

Es un framework para front-end, ayuda a construir sitios mobile responsive mas r�pido y f�cil.

Fue creado por Twitter por un peque�o grupo de desarrolladores para crear interfaces web consistentes, el proyecto fue creciendo hasta que decidieron hacerlo p�blico en 2011. Est� entre las herramientas mas usadas para desarrollo web, entre otras cosas, es el segundo proyecto con mas estrellas en Github.com

En programaci�n, un framework podr�a verse como una librer�a. Contiene herramientas, partes y una funcionalidad existente que podemos usar para realizar tareas est�ndares de manera r�pida y f�cil.  En el caso de Bootstrap, esas tareas est�ndar son crear patrones de dise�o tales como formularios, menus, columnas, bottones y otros componentes �tiles para desarrollar nuestros sitios web.

Nos ayuda al ofrecer un gran n�mero de clases que podemos aplicar a los elementos HTML para crear los componentes que necesitemos. Podemos dise�ar p�ginas complejas desde el est�ndar de HTML y adaptarla a nuestra medida. Adem�s viene con funcionalidad adicional y plugins de Jquery que preveen funcionalidad adicional tal como carruseles, botones, tooltips y mas.


## Configuraci�n

Existen dos posibilidades para cargar Bootstrap:

1. De manera remota

2. Descargo y lo uso localmente.

### Crear una p�gina HTML

Como primer paso crearemos una p�gina HTML como base para Bootstrap. 

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

1a. Cargar a trav�s de la CDN de Bootstrap.

   Como Bootstrap consiste en hojas de estilos y scripts, pueden ser cargados en el head de mi documento HTML, en la web de [Bootstrap](https://getbootstrap.com/docs/4.2/getting-started/download/)

   Esta forma tiene la ventaja de que esta versi�n puede estar cargada en la cach� del navegador lo que hace que cargue mas r�pido.

```html
 <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS" crossorigin="anonymous">
```

1b. Cargar localmente

```html
    <link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
```
La ventaja que presenta es que si se corta internet no voy a tener problemas porque est� cargado localmente.

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

## Dise�a tu landing page

### 1. Agregamos una barra de navegaci�n

1. Usaremos la clase **navbar**, es uno de los elementos por defecto de Bootstrap, crea un elemento de navegaci�n responsivo por defecto y colapsar� automaicamente en pantallas mas peque�as, tambi�n ofrece soporte para marcas, colores, espaciado y otros componentes.

  Agregamos el siguiente c�digo luego de la etiqueta ```<body>```

  ```html
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

  * navbar-expand-md - Muestra a qu� punto la barra de navegaci�n se expande desde vertical o �cono hamburguesa a una barra horizontal de todo el ancho, la seteamos a _medium_ que para bootstrap es cualquier cosa mayor a 768px.
  * navbar-brand - Se usa para la marca del sitio web, podemos incluir una imagen para el logo.
  * navbar-toggler - El bot�n expansivo para el men� colapsado. Este c�digo ```data-toggle="collapse"``` define que ser� un men� hamburguesa, no un desplegable que es otra opci�n. Es importante definir un ```data-target``` que es un id CSS (definido por el #)  y envuento en un div con el mismo nombre alrededor del actual elemento navbar
  * navbar-toggler-icon - Permite agregar �conos de usuario para abrir el men� en pantallas mas peque�as.
  * navbar-nav - La clase para el elemento que contiene todos los �tems del men� ```<ul>```, los elementos que contiene son nav-item y nav-link.
  * Si quisiera agregarle colores a nuestra navbar, con agregarle las clases ```bg-dark navbar-dark``` alcanza

### 2. Incluyendo CSS a medida
  
  Podemos incluir CSS en la medida que lo necesitemos creando un archivo que contendr� todos los cambios y llam�ndolo desde nuestra p�gina.
  
  ```<link rel="stylesheet" type="text/css" href="main.css">```

### 3. Crear un contenedor para el contenido
  
  Luego de la barra de navegaci�n, agregamos un container para el contenido de la p�gina.

  ```html
    <header class="page-header header container-fluid">
    </header>
  ```
  
  La clase container-fluid es otra clase por defecto de Bootstrap,aplic�ndola a un div aplica mas c�digo CSS por detr�s, el sujifo ```-fluid``` hace que se estire todo el ancho, tambi�n existe un ```container``` que tiene anchos fijos aplicados, as� siempre habr� espacio en ambos lados de la pantalla.

### 4. Background image y JavaScript a medida

  Vamos a incluir una imagen de fondo para nuestro header, para eso usaremos un poco de Jquery para que la imagen ocupe todo el ancho.

  Necesitamos crear un archivo ```main.js``` y llamarlo antes de ```</body>```

  ```html
   <script src="js/main.js"></script>
   ```

  Lo que resta es configurar una imagen de fondo desde ```main.css```

  ```css
    /*main.css*/
      .header {
      background-image: url('img/header-background.jpg');
      background-size: cover;
      background-position: center;
      position: relative;
    }
  ```

### 5. Agregar una cubierta (overlay)
  
  Para hacerlo mas estilizado, agregaremos la clase overlay sobre nuestra imagen en ```custom.css```

  ```html
      <div class="overlay"></div>
  ```

  ```css
      .overlay {
      position: absolute;
      min-height: 100%;
      min-width: 100%;
      left: 0;
      top: 0;
      background: rgba(0, 0, 0, 0.6);
    }
  ```

### 6. Incluir un t�tulo para la p�gina y un texto
  
  Probablemente queramos agregar un t�tulo y un contenido a esta p�gina.

```html
    <div class="description">
      <h1>Welcome to the Landing Page!</h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque interdum quam odio, quis placerat ante luctus eu. Sed aliquet dolor id sapien rutrum, id vulputate quam iaculis. Suspendisse consectetur mi id libero fringilla, in pharetra sem ullamcorper.</p>
    </div>
```

  Luego agregamos lo siguiente a nuestras hojas de estilos
```css
  .description {
      left: 50%;
      position: absolute;
      top: 45%;
      transform: translate(-50%, -55%);
      text-align: center;
    }
    .description h1 {
      color: #6ab446;
    }
    .description p {
      color: #fff;
      font-size: 1.3rem;
      line-height: 1.5;
    }
```

fuente

[https://websitesetup.org/bootstrap-tutorial-for-beginners/](https://websitesetup.org/bootstrap-tutorial-for-beginners/)
