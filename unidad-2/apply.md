# Unidad 2


## 🛠 Fase: Apply

### Actividad 04
Construye un diagrama detallado de la máquina de estados, incluyendo estados, eventos, transiciones y acciones.  

<img width="486" height="811" alt="image" src="https://github.com/user-attachments/assets/71309621-4e39-4840-b656-7fd99216f3a1" />

### Actividad 05
**1).** La definición de los vectores de prueba básicos que permiten verificar el correcto funcionamiento del programa.  
**2).**  
**a.** Construye un diagrama detallado de la máquina de estados, incluyendo estados, eventos, transiciones y acciones.    
**b.** El código que implementa la bomba temporizada.  

**a. Vectores de Prueba**  

**Prueba de configuración del tiempo:** Se presiona el botón A varias veces mientras está en el estado SETTING y se verifica que el tiempo aumente progresivamente desde cero. Esta prueba confirma que la lógica de incremento funciona y que el tiempo se almacena correctamente.  

**Transición a estado armado:** Luego de establecer un tiempo, se presiona el botón B para pasar a ARMED. Se valida que el micro:bit muestre el ícono de bomba y que, tras un segundo, comience la cuenta regresiva. Esto confirma que la transición entre SETTING y COUNTDOWN_LOOP ocurre correctamente.

**Cuenta regresiva decreciente:** Durante COUNTDOWN_LOOP, se observa que el tiempo disminuye en intervalos de un segundo y que los números se muestran en pantalla. Esta prueba asegura que el decremento funciona correctamente.

**Explosión al llegar a cero:** Una vez que el tiempo llega a cero, se valida que el estado cambie a EXPLOTED y se muestre la imagen de explosión (ícono triste). Después de 2 segundos, debe volver a IDLE.

**Ciclo completo:** Desde IDLE hasta EXPLOTED y de regreso a IDLE, se prueba toda la secuencia para asegurar que el sistema pueda reiniciarse correctamente después de cada ciclo.

**b. Código:**
``` py
from microbit import *

estado = "IDLE"
tiempo = 0

while True:
    if estado == "IDLE":
        display.show(Image.HEART)
        if button_a.was_pressed():
            estado = "SETTING"
            tiempo = 0

    elif estado == "SETTING":
        display.scroll(str(tiempo))
        if button_a.was_pressed():
            tiempo += 1
        elif button_b.was_pressed():
            estado = "ARMED"

    elif estado == "ARMED":
        display.show(Image.SKULL)
        sleep(1000)
        estado = "COUNTDOWN_LOOP"

    elif estado == "COUNTDOWN_LOOP":
        if tiempo > 0:
            display.scroll(str(tiempo))
            sleep(1000)
            tiempo -= 1
        else:
            estado = "DETONATED"

    elif estado == "DETONATED":
        display.show(Image.SAD)
        sleep(2000)
        estado = "IDLE"

```
