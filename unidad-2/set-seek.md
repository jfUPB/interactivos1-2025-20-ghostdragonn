# Unidad 2

## 🔎 Fase: Set + Seek

### Actividad 01
**Describe detalladamente cómo funciona este ejemplo.**

**R/** Este programa hace que dos píxeles de la micro:bit parpadeen a diferentes ritmos. Cada píxel se maneja con una clase que controla su posición, estado (encendido o apagado) y tiempo de cambio. Al iniciar, se muestra el estado inicial y se guarda el tiempo actual. Luego, espera a que pase un intervalo para alternar su estado. Esto se repite continuamente en un bucle.

**¿Cuáles son los estados en el programa?**

**R/** 	"WaitTimeout"

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

semaforo = Semaforo()

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

### Actividad 03
**Explica por qué decimos que este programa permite realizar de manera concurrente varias tareas.**

**R/** Por que escribimos el codigo de las tareas de tal manera que no bloquee la CPU.

**Identifica los estados, eventos y acciones en el programa.**

**R/** 
**Estados:**
- STATE_HAPPY.
- STATE_HAPPY: espera botón o tiempo para cambiar.
- STATE_SMILE: espera botón o tiempo para cambiar.

**Eventos:**
- Botón A presionado: button_a.was_pressed().
- Tiempo transcurrido: utime.ticks_diff(...) > interval.

**Acciones:**
- Mostrar una imagen (display.show(...)).
- Guardar el tiempo inicial (start_time = utime.ticks_ms()).
- Establecer el nuevo intervalo de duración del estado.
- Cambiar el estado (current_state = ...).
- STATE_SAD: espera botón o tiempo para cambiar.

**3. Describe y aplica al menos 3 vectores de prueba para el programa. Para definir un vector de prueba debes llevar al sistema a un estado, generar los eventos y observar el estado siguiente y las acciones que ocurrirán. Por tanto, un vector de prueba tiene unas condiciones iniciales del sistema, unos resultados esperados y los resultados realmente obtenidos. Si el resultado obtenido es igual al esperado entonces el sistema pasó el vector de prueba, de lo contrario el sistema puede tener un error.**

**Vector de prueba 1: Transición por tiempo desde INIT a SMILE**

- **Condiciones iniciales**: El sistema inicia en STATE_INIT.  
- **Evento**: No se presiona ningún botón. Se deja correr el programa.  
- **Resultado esperado**: El sistema entra en STATE_HAPPY mostrando una imagen de cara feliz.
Después de 1500 ms sin presionar botón, cambia a STATE_SMILE mostrando una imagen sonriente.
- **Resultado obtenido**: Funciona como se esperaba.

**Vector de prueba 2: Transición de HAPPY a SAD por botón**

- **Condiciones iniciales**: El sistema está en STATE_HAPPY.
- **Evento**: El usuario presiona el botón A antes de que pasen los 1500 ms.
- **Resultado esperado**: El sistema muestra una imagen triste.
Cambia a STATE_SAD y reinicia el contador de tiempo.
- **Resultado obtenido**: Funciona como se esperaba.

**Vector de prueba 3: Transición de SMILE a SAD por tiempo, y de SAD a HAPPY por botón**

- **Condiciones iniciales**: El sistema se encuentra en STATE_SMILE.
- **Evento**: No se presiona el botón. Luego, estando en STATE_SAD, se presiona el botón A.
- **Resultado esperado**: Después de 1000 ms, el sistema cambia a STATE_SAD y muestra una imagen triste.
Al presionar el botón A, pasa a STATE_SMILE.
- **Resultado obtenido**: Funciona como se esperaba.


