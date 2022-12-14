# Slider-Responsive
Slider Responsive con HTML, CSS y Javascript

A continuación se muestra como crear una Slider o Carrusel de Imagenes Responsive haciendo uso de HTML5, CSS3 y JavaScript puro.

![Ejemplo de vista](https://abelosh.com/wp-content/uploads/2020/08/slider_responsive-1-1024x519.jpg)

Para integrar el slider o carrousell de imagenes sigue los siguientes pasos:

- Crear un archivo style.css
- Crear un archivo functions.js

En el head de la página donde tendrás el slider, agrega la dirección del archivo style.css, como se muestra a continuación. (la ruta depende de la ubicación del archivo style.css).

<code> < link rel="stylesheet" href="style.css" > </code>


En el footer del archivo donde tendrás el slider, agrega las siguientes líneas de código.

- La primera línea corresponde a la librería fontawesome, el cual permite insertar iconos de forma gratuita, (Puedes descargar la librería para no consumir recursos de servidores externos).
- La segunda línea corresponde al archivo functions.js que se ha creado previamente, (Si ya tienes un archivo de funciones solo debes enlazarlo).

<code>
  <script defer src="https://use.fontawesome.com/releases/v5.0.6/js/all.js"></script>
  <script defer src="functions.js"></script>
