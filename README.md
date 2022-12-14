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


Copia y pega el siguiente html en la pagina donde quieres integrar el slider:

<code> <!--
  <section id="container-slider">	
     <a href="javascript: fntExecuteSlide('prev');" class="arrowPrev"><i class="fas fa-chevron-circle-left"></i></a>
     <a href="javascript: fntExecuteSlide('next');" class="arrowNext"><i class="fas fa-chevron-circle-right"></i></a>
     <ul class="listslider">
       <li><a itlist="itList_0" href="#" class="item-select-slid"></a></li>
       <li><a itlist="itList_1" href="#"></a></li>
       <li><a itlist="itList_2" href="#"></a></li>
     </ul>
     <ul id="slider">
       <li style="background-image: url('https://cdn.pixabay.com/photo/2020/04/15/11/20/telework-5046230_1280.jpg'); z-index:0; opacity: 1;">
         <div class="content_slider" >
           <div>
             <h2>Emprendimiento empresarial</h2>
       <p>Descubra en qué consiste el emprendimiento empresarial por medio de 5 estrategias fundamentales.</p>
       <a href="#" class="btnSlider">Ver más</a>
     </div>
         </div>
       </li>
       <li style="background-image: url('https://cdn.pixabay.com/photo/2018/02/20/10/28/business-3167295_960_720.jpg'); ">
         <div class="content_slider" >
           <div>
             <h2>Negocios</h2>
       <p>Recursos, guías, herramientas y consejos para emprender, crear tu empresa o iniciar un negocio exitoso</p>
       <a href="#" class="btnSlider">Ver más</a>
     </div>
         </div>
       </li>
       <li style="background-image: url('https://cdn.pixabay.com/photo/2015/07/17/22/42/typing-849806_960_720.jpg'); ">
         <div class="content_slider" >
           <div>
             <h2>Estrategias de negocio</h2>
       <p>Las estrategias de negocio representan planes o métodos...</p>
       <a href="#" class="btnSlider">Ver más</a>
     </div>
         </div>
       </li>
    </ul>
  </section>
-->
</code>

Debes sustituir la url de las imágenes por las tuyas.

En el archivo style.css pega los siguiente estilos, si ya tienes un archivo de estilos puedes pegarlos allí.

<code>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  #container-slider
  {
      position: relative;
      display: block;
      width: 100%;
  }
  #slider {
      position: relative;
      display: block;
      width: 100%;
      height: 100vh;
      min-height: 500px;
  }
  #slider li {
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
      position: absolute !important;
      top: 0 !important;
      left: 0 !important;
      width: 100%;
      height: 100%;
      display: block;
      -webkit-transition: opacity 1s;
      -moz-transition: opacity 1s;
      -ms-transition: opacity 1s;
      -o-transition: opacity 1s;
      transition: opacity 1s;
      z-index: -1;
      opacity: 0;
  }
  #container-slider .arrowPrev, #container-slider .arrowNext{
      font-size: 30pt;
      color: rgba(204, 204, 204, 0.65);
      cursor: pointer;
      position: absolute;
      top: 50%;
      left: 50px;
      z-index: 2; 
  }
  #container-slider .arrowNext {
      left: initial;
      right: 50px !important;
  }
  .content_slider{
      padding: 15px 30px;
      color: #FFF;
      width: 100%;
      height: 100%;
  }
  .content_slider div{
      text-align: center;
  }
  .content_slider h2{
      font-family: 'arial';
      font-size: 30pt;
      letter-spacing: 1px;
      text-transform: uppercase;
      margin-bottom: 20px;
  }
  .content_slider p {
      font-size: 15pt;
      font-family: 'arial';
      color: #FFF;
      margin-bottom: 20px;
  }
  #slider li .content_slider{
      background: rgba(0, 0, 0, 0.50);
      padding: 10px 125px;
  }
  .content_slider{
      display: -webkit-flex;
      display: -moz-flex;
      display: -ms-flex;
      display: -o-flex;
      display: flex;
      justify-content: center;
      align-items: center;
  }
  .btnSlider{
      color: #FFF;
      font-size: 15pt;
      font-family: 'arial';
      letter-spacing: 1px;
      padding: 10px 50px;
      border: 1px solid #CCC;
      background: rgba(13, 13, 13, 0.55);
      border-radius: 31px;
      text-decoration: none;
      transition: .5s all;
  }
  .btnSlider:hover{
      background: #111;
      border: 1px solid #111;
  }
  .listslider {
      position: absolute;
      display: -webkit-flex;
      display: -moz-flex;
      display: -ms-flex;
      display: -o-flex;
      display: flex;
      justify-content: space-between;
      align-items: center;
      left: 50%;
      bottom: 5%;
      list-style: none;
      z-index: 2;
      transform: translateX(-50%);
  }
  .listslider li {
      border-radius: 50%;
      width: 10px;
      height: 10px;
      cursor: pointer;
      margin: 0 5px;
  }
  .listslider li a {
      background: #CCC;
      border-radius: 50%;
      width: 100%;
      height: 100%;
      display: block;
  }
  .item-select-slid {
      background: #FFF  !important;
  }

  @media screen and (max-width: 460px){
    .content_slider h2 {
        font-size: 15pt !important;
    }
    .content_slider p {
        font-size: 12pt !important;
    }
    #container-slider .arrowPrev, #container-slider .arrowNext{
      font-size: 20pt;
    }
    #container-slider .arrowPrev{
      left: 15px;
    }
    #container-slider .arrowNext{
      right: 15px !important;
    }
    #slider{
      height: 400px;
      min-height: 400px;
    }
    #slider li .content_slider{
      padding: 10px 35px;
    }
    .btnSlider{
      padding: 10px 30px;
        font-size: 10pt;
    }

  }
</code>

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
  
##Listo, puedes probar en el navegador.
