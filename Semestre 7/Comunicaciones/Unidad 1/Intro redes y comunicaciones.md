En torno a los años 1970 y 1980 se produjo una sinergia entre los campos de los computadores y las comunicaciones que desencadenó un cambio drástico en las tecnologías, productos y en las propias empresas que, desde entonces, se dedican conjuntamente a los sectores de los computadores y de las comunicaciones.

### Un modelo para las comunicaciones
Comenzaremos nuestro estudio considerando el modelo sencillo de sistema de comunicación, en la que se propone un diagrama de bloques.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagrama-general-bloques.png" width="600">
	<br>
	<em>Diagrama general de bloques</em>
</div>

El **objetivo principal de todo sistema de comunicaciones es intercambiar información entre dos entidades.** Debajo se muestra un ejemplo particular de comunicación entre una estación de trabajo y un servidor a través de una red telefónica pública.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="ejemplo-comunicacion.png" width="600">
	<br>
	<em>Diagrama general de bloques</em>
</div>

##### Los elementos clave en este modelo son los siguientes:
- **La fuente.** Este dispositivo genera los datos a transmitir. Ejemplos de fuentes pueden ser un teléfono o un computador personal.
- **El transmisor.** Normalmente los datos generados por la fuente no se transmiten directamente tal y como son generados. Al contrario, el transmisor transforma y codifica la información, generando señales electromagnéticas susceptibles de ser transmitidas a través de algún sistema de transmisión
- **El sistema de transmisión.** Puede ser desde una sencilla línea de transmisión hasta una compleja red que conecte a la fuente con el destino.
- **El receptor.** El receptor acepta la señal proveniente del sistema de transmisión y la transforma de tal manera que pueda ser manejada por el dispositivo de destino.
- **El destino.** Toma los datos del receptor.

Aunque el modelo presentado pueda **parecer aparentemente sencillo**, en realidad implica una gran **complejidad**. Para hacerse una idea de la magnitud de ella, la siguiente tabla lista algunas de las tareas claves que se deben realizar en un sistema de comunicaciones.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="tareas-en-sistemas-de-comunicacion.png" width="800">
	<br>
	<em>Tareas en los sistemas de comunicación</em>
</div>

#### Utilización del sistema de transmisión
Se refiere a la necesidad de hacer un uso eficaz de los recursos utilizados en la transmisión, los cuales se suelen compartir habitualmente entre una serie de dispositivos de comunicación.

**Para lograr esto se utilizan técnicas como multiplexación...**

<hr>
#### Multiplexación
Técnica que permite que múltiples señales o flujos de datos compartan un mismo medio físico de transmisión.

<hr>
#### Generación de la señal
La generación de la señal es una función del transmisor, que transforma los datos en una señal adecuada para la transmisión.

Las características de la señal, como su forma e intensidad, deben permitir:
- su correcta propagación a través del medio
- su correcta interpretación en el receptor como datos

<hr>
#### Implementación de la interfaz
Se refiere al establecimiento de un mecanismo que permite al dispositivo conectarse físicamente al sistema de transmisión. A través de esta interfaz, los datos pueden ser enviados en forma de señales al medio.

<hr>
#### Sincronización
Se refiere a la coordinación temporal entre el emisor y el receptor, de modo que el receptor pueda interpretar correctamente la señal recibida.

El receptor debe ser capaz de:
- determinar cuándo comienza y termina la señal
- identificar la duración de cada elemento de la señal

<hr>
#### Gestión del intercambio
Se refiere al conjunto de **reglas y procedimientos** que permiten **coordinar la comunicación** entre dos dispositivos durante un intercambio de datos.

Para que la comunicación sea posible, ambas partes deben cooperar y establecer convenciones respecto a:
- El establecimiento y finalización de la conexión
- El modo de transmisión (simultánea o por turnos)
- La cantidad y formato de los datos transmitidos
- Las acciones a realizar ante situaciones excepcionales, como errores

<hr>
#### Detección y corrección de errores
Se refiere al conjunto de procedimientos que permiten identificar y, en caso necesario, corregir errores que ocurren durante la transmisión de datos.

Estos errores se producen debido a la distorsión de la señal en el medio de transmisión. En sistemas donde la integridad de los datos es crítica, se requiere asegurar que la información recibida sea correcta.

<hr>
#### Detección y corrección de errores
Se refiere al conjunto de procedimientos que permiten identificar y, en caso necesario, corregir errores que ocurren durante la transmisión de datos.

Estos errores se producen debido a la distorsión de la señal en el medio de transmisión. En sistemas donde la integridad de los datos es crítica, se requiere asegurar que la información recibida sea correcta.

<hr>
#### Direccionamiento
Se refiere al mecanismo mediante el cual el sistema fuente identifica al destinatario de los datos en un medio de transmisión compartido.

Permite que, aunque múltiples dispositivos estén conectados al mismo medio, solo el destino indicado procese la información recibida.

<hr>
#### Encaminamiento
Se refiere al proceso de selección de la ruta que deben seguir los datos a través de la red para llegar al destino.

En redes donde existen múltiples caminos posibles, el sistema debe elegir una de las rutas disponibles.

<hr>
#### Recuperación
Se refiere a los mecanismos que permiten restablecer la comunicación o el estado del sistema cuando el intercambio de datos se ve interrumpido por un fallo.

El objetivo es:
- continuar la transmisión desde el punto de interrupción, o
- restaurar el estado previo al inicio del intercambio

<hr>
#### Formato de mensajes
Se refiere al acuerdo entre emisor y receptor sobre la forma en que los datos son representados e interpretados durante la comunicación.

Incluye aspectos como el código utilizado para representar la información y la estructura de los datos transmitidos.

<hr>
#### Seguridad
Se refiere al conjunto de mecanismos que garantizan que la comunicación se realice de forma confiable, asegurando:
- Que solo el destinatario autorizado reciba a los datos
- Que los datos no sean alterados durante la transmisión
- Que el origen de los datos sea auténtico

<hr>
#### Gestión de red
Se refiere a las funcionalidades necesarias para administrar el sistema de comunicación, permitiendo:
- configurar la red
- monitorizar su funcionamiento
- detectar y reaccionar ante fallos o sobrecargas
- planificar su crecimiento y evolución
