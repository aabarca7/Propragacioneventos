# Propragacioneventos
ejemplo de eventos en js

Qué es un evento en Js
En JavaScript, la interacción con el usuario se consigue mediante la captura de los eventos que éste produce. Un evento es una acción del usuario ante la cual puede realizarse algún proceso (por ejemplo, el cambio del valor de un formulario, o la pulsación de un enlace).
Los eventos se capturan mediante los manejadores de eventos. El proceso a realizar se programa mediante funciones JavaScript llamadas por los manejadores de eventos
Ejemplo de evento:
<INPUT TYPE="text" onChange="CompruebaCampo(this)">
En este ejemplo, CompruebaCampo() es una función JavaScript definida en alguna parte del documento HTML (habitualmente en la cabecera del mismo). El identificador this es una palabra propia del lenguaje, y se refiere al objeto desde el cual se efectua la llamada a la función (en este caso, el campo del formulario).

preventDefault
Cancela el evento si este es cancelable, sin detener el resto del funcionamiento del evento, es decir, puede ser llamado de nuevo.
event.preventDefault()

stopPropagation
El método stopPropagation() de la interfaz Event evita la propagación adicional del evento actual en las fases de captura y bubbling.
event.stopPropagation();

propagación de eventos
El principio de propagación es simple.
Cuando un evento ocurre en un elemento, este primero ejecuta los manejadores que tiene asignados, luego los manejadores de su padre, y así hasta otros ancestros.
Una propagación de evento empieza desde el elemento objetivo hacia arriba. Normalmente este continúa hasta <html> y luego hacia el objeto document, algunos eventos incluso alcanzan window, llamando a todos los manejadores en el camino.
Pero cualquier manejador podría decidir que el evento se ha procesado por completo y detener su propagación.
El método para esto es event.stopPropagation().

fases de los eventos
El proceso de procesamiento de eventos tiene principalmente tres etapas: la etapa de captura, la etapa de destino y la etapa de burbujeo;
Fase de captura:Cuando realizamos algunas operaciones en un nodo del árbol DOM (por ejemplo, hacer clic, mover el mouse hacia arriba), se emitirá un evento. Este evento se emite desde la ventana y continúa pasando a través de los nodos de nivel inferior hasta el nodo de destino activado. El proceso antes de llegar al nodo objetivo es la fase de captura. El evento es recibido por el elemento de la página, paso a paso hasta el elemento específico.
Etapa objetivo:Cuando el evento continúa pasando al nodo objetivo, el evento finalmente se activa en el nodo objetivo, que es la fase objetivo. El elemento específico en sí.
Etapa burbujeante:El burbujeo de eventos significa que cuando el evento comienza, es recibido por el elemento más específico (es decir, el nodo donde ocurrió el evento), y luego se propaga a nodos menos específicos paso a paso. Al contrario de lo que ocurre con la captura, el elemento específico en sí mismo sube al elemento de página (El enlace de eventos que usamos normalmente es el principio de propagación de eventos.）
Evento burbujeante:Cuando se utiliza la propagación de eventos, el elemento secundario se activa primero y el elemento principal se activa más tarde.

Event Emitter y eventos en NodeJS
módulo de eventos proporciona un único objeto: events.EventEmitter. Core EventEmitter es activado por eventos y detector de eventos paquete de funciones.
EventEmitter Si se produce un error cuando se crea una instancia de un objeto, se disparará el evento "error". Al agregar un nuevo oyente, evento 'newListener' se activa cuando se retira el oyente, el evento 'removeListener' se dispara
Cada EventEmitter evento mediante un nombre de evento y una serie de parámetros, el nombre del evento es una cadena, expresada generalmente cierta semántica. Para cada evento, EventEmitter soporta varios detector de eventos.
Cuando se produce el evento, el evento para registrar detectores de eventos se denominan secuencialmente como argumento parámetro de evento de devolución de llamada.
