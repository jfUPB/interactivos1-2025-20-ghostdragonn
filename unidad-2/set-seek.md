# Unidad 2

## 🔎 Fase: Set + Seek

### Actividad 01
**Describe detalladamente cómo funciona este ejemplo.**

**R/** Este programa hace que dos píxeles de la micro:bit parpadeen a diferentes ritmos. Cada píxel se maneja con una clase que controla su posición, estado (encendido o apagado) y tiempo de cambio. Al iniciar, se muestra el estado inicial y se guarda el tiempo actual. Luego, espera a que pase un intervalo para alternar su estado. Esto se repite continuamente en un bucle.

**¿Cuáles son los estados en el programa?**

**R/** 	"Init" y "WaitTimeout"

**¿Cuáles son los eventos/inputs en el programa?**

**R/** 	Paso del tiempo para que el pixel se apague o se encienda (utime.ticks_diff(utime.ticks_ms(),self.startTime) > self.interval:)

**¿Cuáles son las acciones en el programa?**

**R/** 
- Encender/apagar píxel
- Cambiar pixelState
- Actualizar startTime

### Actividad 02

**1. Escribe el código que soluciona este problema en tu bitácora.**

**Código:**
``` py
from microbit import *
import utime

class Pixel:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        self.brightness = 0

    def encender(self):
        self.brightness = 9
        display.set_pixel(self.x, self.y, self.brightness)

    def apagar(self):
        self.brightness = 0
        display.set_pixel(self.x, self.y, self.brightness)

class Semaforo:
    def __init__(self):
        # Nuevas posiciones (todas en la parte superior de la columna 2)
        self.rojo = Pixel(2, 0)
        self.amarillo = Pixel(2, 1)
        self.verde = Pixel(2, 2)
        self.estado = "Rojo"
        self.inicio = utime.ticks_ms()

    def actualizar(self):
        ahora = utime.ticks_ms()

        if self.estado == "Rojo":
            self.rojo.encender()
            self.amarillo.apagar()
            self.verde.apagar()
            if utime.ticks_diff(ahora, self.inicio) > 3000:
                self.estado = "Verde"
                self.inicio = ahora

        elif self.estado == "Verde":
            self.rojo.apagar()
            self.amarillo.apagar()
            self.verde.encender()
            if utime.ticks_diff(ahora, self.inicio) > 3000:
                self.estado = "Amarillo"
                self.inicio = ahora

        elif self.estado == "Amarillo":
            self.rojo.apagar()
            self.amarillo.encender()
            self.verde.apagar()
            if utime.ticks_diff(ahora, self.inicio) > 1000:
                self.estado = "Rojo"
                self.inicio = ahora

# Instancia del semáforo
semaforo = Semaforo()

# Bucle principal
while True:
    semaforo.actualizar()
```

**2. Identifica los estados, eventos y acciones en tu código.**

**Estados:** 
- Cuando solo está encendido el LED rojo  
- Cuando solo está encendido el LED verde  
- Cuando solo Solo está encendido el LED amarillo

**Eventos:**
Paso del tiempo de un color a otro

**Acciones**
- Encender un solo LED dependiendo del estado
- Actualizar el estado interno (self.estado) y el tiempo de inicio (self.inicio)



