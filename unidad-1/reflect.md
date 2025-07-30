# Unidad 1

## 🤔 Fase: Reflect

### Actividad 07

**1). Basándote en los ejemplos que vimos de sistemas físicos interactivos al iniciar el curso, describe las tres características que definen a un sistema físico interactivo.**

**R/** sensores, procesamiento e interactividad.

**2). Explica el modelo input-process-output de Patrick Hübner usando como ejemplo el sistema que construiste con micro:bit y p5.js en la Actividad 06. ¿Cuál fue el input, cuál fue el proceso y cuál fue el output?**

**R/**  
**Input:** Son los datos de entrada, en el caso de la actividad 06, si el botón es presionado o no, se envía información constantemente desde el micro:bit, pasan por el serial hasta llegar al computador.

**Output:** Es lo que se muestra o lo que se genera después de haber recogido y procesado todos los dato, en le caso de la actividad 06 no muestran dentro del canvas en p5js como el círculo se mueve de un lado a otro al ser oprimidos los botones del micro:bit.

**Proceso:** Es el encargado de recoger los inputs y como su nombre lo dice, procesarlos para darle salida a los outputs. En el caso de la actividad 06

**3). ¿Cuál es la función de la línea uart.write('A') en el código del micro:bit y qué función en p5.js se encarga de “escuchar” ese mensaje?**

**R/** No me acuerdo

**4). ¿Cuál es la diferencia fundamental entre el arte/diseño tradicional y el arte/diseño generativo?**

**R/**  Que el arte tradicional es hecho por una persona y el arte/ diseño generativo esta hecho por medio de códigos y además tiene cierta autonomía en el sistema

**5). Imagina que quieres que un círculo en p5.js cambie a un color aleatorio cada vez que sacudes el micro:bit. Describe qué tendrías que programar en el micro:bit y qué tendrías que programar en p5.js para lograrlo.**

**R/** No sabría como hacerlo

### Parte 2: reflexión sobre tu proceso (Metacognición)

**1). ¿Qué fue más desafiante para ti en esta unidad: la parte conceptual (entender qué es un sistema físico interactivo) o la parte técnica (hacer que el micro:bit y p5.js se comunicaran)? ¿Por qué?**

**R/** La parte técnica, ya que se me dificulta entender el código, de a poquitos he ido entendiendo más y más, pero igual todavía se me cuesta.

**2). Describe el momento “¡Aha!” que tuviste cuando lograste que una acción en el micro:bit (presionar un botón, saucudirlo) tuviera un efecto visible en el canvas de p5.js por primera vez. ¿Qué fue lo que entendiste en ese instante?**

**R/** Me acuerdo que en la primera actividad no me funcionaba el programa ni mostraba la interfaz gráfica, estuve buscando que podría tener mal, hasta que me di cuenta que no había conectado bien el programa en p5js al micro:bit, ya que puse la biblioteca mal, cuando la pegue al programa se duplicaron unas cosas del código y no me di cuenta. Esto me ayudo a entender mejor como va el orden del código.

**3). Al inicio de la unidad te pregunté: “¿Este curso para qué me sirve?”. Después de experimentar y construir tu primer prototipo, ¿Cómo ha cambiado o se ha vuelto más concreta tu respuesta a esa pregunta?**

**R/** Se ha vuelto más concreta, me parece muy interesante todo este tema, ya que hay muchas oportunidades creativas y siento que me serviría mucho para mi perfil profesional, ya que se enfoca más en el arte y lo creativo.

**4). El tutorial de la Actividad 05 te llevó paso a paso. ¿Cómo te sentiste con ese método de aprendizaje? ¿Te dio seguridad o preferirías haberlo intentado por tu cuenta desde el principio?**

**R/** Me pareció el método correcto, yo entiendo más cuando me explican paso a paso, y ya después intentarlo yo misma, siento que me da más claridad en todo.

### Actividad 08

Para la realización de esta actividad tuve como compañero a Luis Enrique Rojas Machado.

**En mi código:** la micro:bit únicamente envía un dato ("A" o "B") cuando uno de los botones es presionado. Esto significa que el círculo solo se mueve en el momento exacto en que se detecta la pulsación, produciendo un movimiento discreto y por saltos. Cada vez que se presiona un botón, el círculo avanza o retrocede 10 unidades. El código en p5.js simplemente reacciona a ese evento puntual, sin mantener un estado constante ni dar retroalimentación visual adicional.

**Código de mi compañero:** implementa una lógica más completa. La micro:bit está enviando datos constantemente: "A" si se presiona el botón A, "N" si se presiona B y "0" si no se presiona ningún botón. Esto le permite al programa en p5.js saber en todo momento si debe mover el círculo hacia la izquierda, hacia la derecha o mantenerlo quieto. Además, se incluye una variable de dirección (dir) que hace posible un movimiento constante mientras el botón esté presionado, y también se cambia el color del círculo para indicar hacia dónde se está moviendo o si está detenido (rojo, verde o gris respectivamente). Esto proporciona una experiencia interactiva más rica y continua.

Los dos códigos son diferentes porque usan enfoques distintos para resolver el mismo problema de controlar un círculo con una micro:bit, en mi código, los datos solo se envían cuando se presiona un botón. Es decir, si no hay pulsación, no se envía nada. Mientras que en el código de mi compañero, se envían datos todo el tiempo: "A" si se presiona el botón A, "N" si se presiona B, y "0" si no se presiona ningún botón.

De su solución aprendí sobre la variable dir y su funcionamiento, y que hubiera sido mejor implementar en mi código que siempre y cuando los botones sean presionados el círculo se mueve.

### Actividad 09

Responde a las siguientes preguntas. Tu honestidad es el recurso más valioso para la mejora del curso.

**Continuar:** ¿Qué actividad, video o ejemplo de esta unidad te resultó más inspirador o te ayudó más a entender el potencial de los sistemas físicos interactivos?

**R/** Explorar todas las diferentes funciones que tiene p5js para crear arte generativo, me pareció muy chévere y se me hizo más fácil de entender que las otras actividades

**Dejar de hacer:** ¿Hubo alguna parte que te pareció demasiado abstracta, muy rápida o confusa? ¿Hay algo que crees que podríamos cambiar para que sea más claro?

**R/** En general tengo más problemas entendiendo como funciona el código con el micro:bit, lo he estado entendiendo más, pero igual me falta.

**Empezar a hacer:** ¿Qué te genera más curiosidad ahora? ¿Te gustaría explorar más sensores del micro:bit (luz, temperatura), crear visualizaciones más complejas en p5.js o ver más ejemplos de proyectos artísticos?

**R/** Crear visualizaciones más complejas en p5.js

**Balance, inspiración vs. técnica:** ¿Cómo sentiste el equilibrio entre ver los videos inspiradores de la Actividad 01 y la parte técnica de conectar las herramientas en las actividades 03-06?

**R/** Me gusta, ya que me permite ver todas las posibilidades que se tiene para cada trabajo, además de que me genera más interés en el tema.

**Comentario adicional:** ¿Hay algo más que quieras compartir sobre tu experiencia en esta unidad introductoria?

**R/** Pues en general me ha sorprendido mucho el curso, porque no se compara a lo que me imaginaba que iba a ser antes de la primera clase, y me ha interesado bastante.
