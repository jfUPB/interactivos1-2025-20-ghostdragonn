# Unidad 1

## 🛠 Fase: Apply

## Actividad 05:
Este sistema fisico interactivo esta conectado a la microbit mediante el serial, que al iniciar crea un a interfaz grafica sencilla: un lienzo y boton para desconectar y conectar la microbit. Una vez conectada, el programa revisa constantemente si hay datos disponibles enviados desde la microbit. Si recibe la letra "A", cambia el color de un rectángulo al centro de la pantalla a rojo; si recibe "N", lo cambia a verde.

# Actividad 06:

[El enlace a mi programa en python](https://python.microbit.org/v/3)

```
# Imports go at the top
from microbit import *

uart.init(baudrate=115200)
display.show(Image.ANGRY)

while True:
    if button_a.is_pressed():
        uart.write('A')
    if button_b.is_pressed():
        uart.write('B')
        
    sleep(100)
```

[El enlace a mi programa en p5js](https://editor.p5js.org/ghostdragonn/sketches/NzqqO_Ttzi)

```
let port;
  let connectBtn;
  let connectionInitialized = false;
 let x = 200;

  function setup() {
    createCanvas(400, 400);
    background(220);
    port = createSerial();
    connectBtn = createButton("Connect to micro:bit");
    connectBtn.position(80, 300);
    connectBtn.mousePressed(connectBtnClick);
  }

  function draw() {
    background(220);

    if (port.opened() && !connectionInitialized) {
      port.clear();
      connectionInitialized = true;
    }
    
    
    circle( x , height / 2 , 60);

     if (port.availableBytes() > 0) {
      let dataRx = port.read(1);
      if (dataRx == "A") {
       x += 10;
      } else if (dataRx == "B") {
      x -= 10;
      }
    }

    if (!port.opened()) {
      connectBtn.html("Connect to micro:bit");
    } else {
      connectBtn.html("Disconnect");
    }
  }

  function connectBtnClick() {
    if (!port.opened()) {
      port.open("MicroPython", 115200);
      connectionInitialized = false;
    } else {
      port.close();
    }
  }
```
