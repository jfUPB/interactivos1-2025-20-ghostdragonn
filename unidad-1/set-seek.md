# Unidad 1

## 🔎 Fase: Set + Seek
## Actividad 01  

### ¿Qué es un sistema físico interactivo?  
R/ Un sistema físico interactivo es un sistema que interactúa con una o más personas en tiempo real. Estos sistemas detectan información del entorno, la procesan y generan una respuesta física o digital.

### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional? 
R/ Como tal, yo soy una persona muy creativa y artística, mi enfoque profesional es la moda y el arte en general, y me parecería muy bacano ver los sistemas físicos implementados en una prenda. Siento que puede abrir mucho camino a la creatividad y guiarme a crear prendas únicas. Ademas me gustaria implementarlo en mis comics e ilustraciones

## Actividad 02

### ¿Qué es el diseño/arte generativo?
R/ El diseño o arte generativo es un proceso creativo donde un artista produce obras mediante un conjunto reglas y cierta autonomía del sistema. No importa cómo se vea, sino que fue generada por un proceso automático. Ademas tiene cierta aleatoriedad lo que hace que el output siempre sea diferente.

### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional?
R/ Siento que seria bastante interesante crear diferentes versiones de 

## Actividad 03

En este sistemas físico interactivo identifica los inputs, outputs y el proceso.
[El enlace a mi programa en python](https://python.microbit.org/v/3)
[El enlace a mi programa en p5js](https://editor.p5js.org/ghostdragonn/sketches/lxbu33J0Q)

## Inputs
-botones 
-boton enviar amor
-vibraciones externas
-puerto serial

## Outputs
-display
-Microbit

## Proceso
El programa en java script del editor y el programa en python

## Actividad 04
[El enlace a mi programa en la web](https://editor.p5js.org/ghostdragonn/sketches/axSvdcGVQ)

## La imagen generada:
<img width="501" height="509" alt="image" src="https://github.com/user-attachments/assets/07182024-a18e-4837-a159-59d11d1e303d" />

## Código:

``` js
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background('#E0FCFF');
  noStroke (100);
  fill('#C7F8FC');
   rect(0, 25, 400, 300);
  
  fill('#B5F5FC')
  rect(0, 50, 400, 300); 
  
  fill('#A3EEF6')
  rect(0, 75, 400, 300); 
  
  fill ('#95E7EF');
  rect(0, 100, 400, 300); 
  
  fill ('#82DEE7');
  rect(0, 125, 400, 300); 
  
   fill ('#70D1DB');
  rect(0, 150, 400, 300);
  
    fill ('#73D5DE');
  rect(0, 150, 400, 300);
  
    fill ('#70D8E2');
  rect(0, 150, 400, 300);
  
      fill ('#70D8E2');
  rect(0, 150, 400, 300);
  
      fill ('#66D3DD');
  rect(0, 175, 400, 300);
  
      fill ('#5BCED9');
  rect(0, 200, 400, 300);
  
   fill ('#55C9D4');
  rect(0, 225, 400, 300);
  
  fill ('#4DC3CD');
  rect(0, 250, 400, 300);
  
    fill ('#41BCC7');
  rect(0, 275, 400, 300);
  
    fill ('#38B7C2');
  rect(0, 300, 400, 300);
  
   fill ('#2EB2BD');
  rect(0, 325, 400, 300);
  
  fill ('#E4FCFF80');
   circle(random(50,350), random(25,300), random(40,7))
  fill ('#C3F8FF80');
  
  circle (random(1,400),random(1,400),random(1,30))
  
 fill ('#EEDEC2');
  rect(0, 350, 400, 300);
  
  
 let baseX = width / 1.22;
  let baseY = height;

  let topX = 350;
  let topY = 150;

  // Puntos de control que curvan la alga
  let cx1 = 350 + 60;
  let cy1 = 300;

  let cx2 = 350 - 60;
  let cy2 = 230;

  stroke('#9DE081');    
  strokeWeight(6);         
  noFill();

  bezier(baseX, baseY, cx1, cy1, cx2, cy2, topX, topY); 

  let baseX2 = width / 1.5;
  let baseY2 = height ;

  let topX2 = 300;
  let topY2 = 170;

  // Puntos de control que curvan la alga
  let cx12 = 300 - 60;
  let cy12 = 320;

  let cx22 = 300 + 60;
  let cy22 = 230;

  stroke('#B7EF76');    
  strokeWeight(6);         
  noFill();

  bezier(baseX2, baseY2, cx12, cy12, cx22, cy22, topX2, topY2); 
  
   let baseX3 = width / 1.27; // donde se ubica en x abajo
  let baseY3 = height/1.02 ;

  let topX3 = 250; //
  let topY3 = 140; // alto

  // Puntos de control que curvan la alga
  let cx13 = 300 + 60;
  let cy13 = 320;

  let cx23 = 300 - 60;
  let cy23 = 230;

  stroke('#77E67C');    
  strokeWeight(6);         
  noFill();

 bezier(baseX3, baseY3, cx13, cy13, cx23, cy23, topX3, topY3); 
  
  let baseX4 = width / 1.8;
  let baseY4 = height;

  let topX4 = 200;
  let topY4 = 210;

  // Puntos de control que curvan la alga
  let cx14 = 200 + 60;
  let cy14 = 320;

  let cx24 = 200 - 60;
  let cy24 = 290;

  stroke('#77E67C');    
  strokeWeight(6);         
  noFill();

  bezier(baseX4, baseY4, cx14, cy14, cx24, cy24, topX4, topY4); 

  let baseX5 = width / 1.99;
  let baseY5 = height ;

  let topX5 = 200; // donde se ubica en x arriba
  let topY5 = 170;

  // Puntos de control que curvan la alga
  let cx15 = 200 - 60;
  let cy15 = 320;

  let cx25 = 200 + 60;
  let cy25 = 230;

  stroke('#B7EF76');    
  strokeWeight(6);         
  noFill();

  bezier(baseX5, baseY5, cx15, cy15, cx25, cy25, topX5, topY5); 
  
   let baseX6 = width / 1.6; // donde se ubica en x abajo
  let baseY6 = height ;

  let topX6 = 275; //
  let topY6 = 190; // alto

  // Puntos de control que curvan la alga
  let cx16 = 300 - 90; //izq
  let cy16 = 300;

  let cx26 = 300 + 60; // der
  let cy26 = 250;

  stroke('#9DE081');    
  strokeWeight(6);         
  noFill();
  
  
  let baseX7 = width / 6;
  let baseY7 = height ;

  let topX7 = 50; // donde se ubica en x arriba
  let topY7 = 170;

  // Puntos de control que curvan la alga
  let cx17 = 50 - 60;
  let cy17 = 320;

  let cx27 = 50 + 60;
  let cy27 = 230;

  stroke('#9DE081');    
  strokeWeight(6);         
  noFill();

  bezier(baseX7, baseY7, cx17, cy17, cx27, cy27, topX7, topY7); 
  

 bezier(baseX6, baseY6, cx16, cy16, cx26, cy26, topX6, topY6); 
  
  fill('#7755A6')
  noStroke (100);
 ellipse(120, 200, 60, 45)
  fill('#7755A6')
  noStroke();
  triangle(
    100, 200,   // punto donde se une al cuerpo
    60, 180,   // punta superior de la cola
    60, 220 )   // punta inferior de la cola
  
  
 fill('#F9688A');
  ellipse(112, 370, 60, 40);

  // Tubos individuales
  fill('#FF78A0');
  rect(80, 320, 15, 60, 10); // tubo 1
  ellipse(87.5, 320, 15, 10); // tapa tubo 1

  fill('#F9688A');
  rect(92, 310, 15, 70, 10); // tubo 2
  ellipse(99.5, 310, 15, 10); // tapa tubo 2

  fill('#FF78A0');
  rect(104, 330, 15, 50, 10); // tubo 3
  ellipse(111.5, 330, 15, 10); // tapa tubo 3

  fill('#F9688A');
  rect(116, 315, 15, 65, 10); // tubo 4
  ellipse(123.5, 315, 15, 10); // tapa tubo 4

  fill('#FF78A0');
  rect(128, 325, 15, 55, 10); // tubo 5
  ellipse(135.5, 325, 15, 10); // tapa tubo 5
  
  fill('#FFF0F0');
  circle(130,195,20)
  
  fill('#30323F'); // ojos pez morado
  circle(135,195,10)
  
  fill('#E2C059')
  noStroke (100);
 ellipse(280, 120, 60, 45)
  noStroke();
  triangle(
    300, 120,   // punto donde se une al cuerpo
    340, 100,   // punta superior de la cola
    340, 140 )   // punta inferior de la cola
  
  fill('#FFF0F0');
  circle(270,115,20)
  
  fill('#30323F'); // ojos pez naranja
  circle(265,115,10)

}
```
