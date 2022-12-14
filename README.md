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
</code>
- / -
<code>
  <script defer src="functions.js"></script>
</code>


##Copia y pega el html en la pagina donde quieres integrar el slider:


Debes sustituir la url de las imágenes por las tuyas.

# No puede faltar el archivo style.css pega los siguiente estilos, si ya tienes un archivo de estilos puedes pegarlos allí.


En el archivo functions.js pega el siguiente código js que se creo anteriormente, si ya tienes un archivo de funciones debes colocarlo allí.

<code>
  if(document.querySelector('#container-slider')){
   setInterval('fntExecuteSlide("next")',5000);
  }
  //------------------------------ LIST SLIDER -------------------------
  if(document.querySelector('.listslider')){
     let link = document.querySelectorAll(".listslider li a");
     link.forEach(function(link) {
        link.addEventListener('click', function(e){
           e.preventDefault();
           let item = this.getAttribute('itlist');
           let arrItem = item.split("_");
           fntExecuteSlide(arrItem[1]);
           return false;
        });
      });
  }

  function fntExecuteSlide(side){
      let parentTarget = document.getElementById('slider');
      let elements = parentTarget.getElementsByTagName('li');
      let curElement, nextElement;

      for(var i=0; i<elements.length;i++){

          if(elements[i].style.opacity==1){
              curElement = i;
              break;
          }
      }
      if(side == 'prev' || side == 'next'){

          if(side=="prev"){
              nextElement = (curElement == 0)?elements.length -1:curElement -1;
          }else{
              nextElement = (curElement == elements.length -1)?0:curElement +1;
          }
      }else{
          nextElement = side;
          side = (curElement > nextElement)?'prev':'next';

      }
      //RESALTA LOS PUNTOS
      let elementSel = document.getElementsByClassName("listslider")[0].getElementsByTagName("a");
      elementSel[curElement].classList.remove("item-select-slid");
      elementSel[nextElement].classList.add("item-select-slid");
      elements[curElement].style.opacity=0;
      elements[curElement].style.zIndex =0;
      elements[nextElement].style.opacity=1;
      elements[nextElement].style.zIndex =1;
  }
</code>
  
## Listo, puedes probar en el navegador.
