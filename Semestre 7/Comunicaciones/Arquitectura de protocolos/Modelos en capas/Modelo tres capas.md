En términos muy generales, se puede afirmar que las comunicaciones involucran a tres agentes: ***aplicaciones, computadores y redes.*** Las aplicaciones se ejecutan en computadores que, generalmente, permiten múltiples aplicaciones simultáneas. Los computadores se conectan a redes y los datos a intercambiar se transfieren por la red de un computador a otro.

Por tanto, la transferencia de datos desde una aplicación a otra implica, en primer lugar, la obtención de los mismos y, posteriormente, hacerlos llegar a la aplicación destino en el computador remoto.

Teniendo esto presente, parece **natural estructurar las tareas de las comunicaciones en tres capas relativamente independientes**:
- La capa de acceso a la red.
- La capa de transporte.
- La capa de aplicación.

<hr>
### Capa de acceso a la red
Es la capa que conecta el computador con la red y se encarga de enviar y recibir datos a través de ella.

Esta capa se encarga de **entregar los datos a la red**, indicar a **qué computador deben llegar (dirección de destino)**, hacer uso de **servicios de la red** (por ejemplo, prioridades) y **manejar la interfaz de red.**

Las características del software de esta capa dependerán del tipo de red que se use. Así, se han desarrollado diferentes estándares para conmutación de circuitos, con mutación de paquetes, redes de área local y otros. De esta manera, se pretende separar las funciones que tienen que ver con el acceso a la red en una capa independiente.

Así, el resto del software de comunicaciones que esté por encima de la capa de acceso a la red no tendrá que ocuparse de las características específicas de la red que se use.

<hr>
### Capa de transporte
Sin importar qué tipo de aplicación esté enviando datos (como transferencia de archivos, correo, etc.), siempre **existe la necesidad común de que la información llegue correctamente al destino**: completa, sin errores y en el mismo orden en que fue enviada.

Como estos requisitos de fiabilidad no dependen de la aplicación específica, no tiene sentido que cada aplicación implemente sus propios mecanismos para lograrlos.

Por ello, se decide concentrar todas estas funciones en una capa intermedia común, llamada capa de transporte, que se encarga de garantizar la correcta entrega de los datos y puede ser reutilizada por todas las aplicaciones, simplificando así el diseño del sistema y evitando duplicación de funcionalidades.

<hr>
### Capa de aplicación
Esta capa es la encargada de implementar la lógica específica de cada servicio que utilizan los usuarios, es decir, es el nivel donde realmente “vive” cada aplicación (como transferencia de archivos, correo electrónico, etc.).

A diferencia de las capas inferiores, que ofrecen servicios generales (como transporte fiable o acceso a la red), aquí no existe una única lógica común, sino que cada tipo de aplicación requiere su propio módulo independiente, ya que cada una tiene objetivos, datos y reglas de funcionamiento distintas.

Por ejemplo, no es lo mismo cómo se organiza una transferencia de archivos que cómo funciona un sistema de correo. Por eso, esta capa no centraliza funciones como las anteriores, sino que permite que existan múltiples módulos especializados, todos apoyándose en las capas inferiores, pero manteniendo sus propias características y comportamiento.

<hr>

En general, para una arquitectura en capas no basta con que existan computadores conectados; también hay que saber **a qué computador** y **a qué aplicación dentro de ese computador** deben llegar los datos. Ahí aparecen los dos niveles de direccionamiento.

En la siguiente figura se muestra **tres computadores conectados a una red de comunicaciones**. Cada computador tiene las tres capas del modelo simple:
- acceso a la red
- transporte
- aplicación
Y arriba de la capa de aplicación aparecen varias aplicaciones numeradas. Eso significa que un mismo computador puede ejecutar **más de una aplicación al mismo tiempo**. La comunicación real no ocurre solo entre computadores, sino entre **aplicaciones que se ejecutan en computadores distintos**.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="protocolo-tres-capas.png" width="400">
	<br>
	<em>Redes y arquitecturas de protocolos.</em>
</div>

Para que la comunicación funcione correctamente, cada destino debe poder ser identificado de forma única. Si no hubiera direcciones, la red no sabría dónde entregar los datos, y aunque llegaran al computador correcto, ese computador no sabría a qué aplicación interna debe pasarlos.

Ahí aparece la idea de **dos niveles de direccionamiento**.

1. **Primer nivel: Dirección de red**
	Cada computador debe tener una **dirección de red**. Esa dirección permite que la red lleve los datos al computador correcto.
2. **Segundo nivel: Dirección de aplicación**
	Cada aplicación tiene una dirección única **dentro del propio computador**. Esa dirección no la usa la red, sino la capa de transporte, para entregar los datos al módulo de aplicación correcto.

### SAP (Service Access Point)
Un **SAP** o **puerto** es un identificador que permite distinguir a una aplicación dentro de un computador cuando usa los servicios de la capa de transporte.

Entonces, un SAP/puerto identifica un punto de comunicación, y normalmente está asociado a un único proceso en ese computador en ese instante

<hr>

Cuando una aplicación genera datos para enviarlos a otro sistema, esos datos por sí solos no son suficientes para que la comunicación funcione correctamente. No basta con “mandar información”; es necesario controlar cómo se envía, a quién va dirigida, en qué orden debe reconstruirse y cómo detectar si ocurrió algún error durante la transmisión.

Para lograr esto, cada capa del sistema añade información adicional llamada **información de control**, que viaja junto con los datos del usuario.

En este contexto, la capa de transporte cumple un rol fundamental. Primero recibe un bloque de datos desde la aplicación y, si es necesario, lo divide en partes más pequeñas para facilitar su manejo y transmisión.

Luego, a cada una de estas partes le agrega una **cabecera de transporte**, que contiene la información necesaria para que el sistema destino pueda procesar correctamente los datos, manejar errores, recuperar datos, etc.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="unidades-datos-de-los-protocolos.png" width="400">
	<br>
	<em>Unidades de datos de los protocolos.</em>
</div>

La combinación de los datos originales con esta cabecera forma lo que se denomina una **unidad de datos del protocolo (PDU)** de transporte.

La cabecera en cada PDU de transporte con tiene información de control que será usada por el protocolo de transporte par en el computador Y. La información que se debe incluir en la cabecera puede ser por ejemplo:
- **SAP destino:** cuando la capa de transporte destino reciba la PDU de transporte, deberá saber a quién van destinados los datos.
- **Número de secuencia:** ya que el protocolo de transporte está enviando una secuencia de PDU, éstas se numerarán secuencialmente para que, si llegan desordenadas, la entidad de transporte destino sea capaz de ordenarlas.
- **Código de detección de error:** la entidad de transporte emisora debe incluir un código obtenido en función del resto de la PDU. El protocolo de transporte receptor realiza el mismo cálculo y compara los resultados con el código recibido. Si hay discrepancia se concluirá que ha habido un error en la transmisión y, en ese caso, el receptor podrá descartar la PDU y adoptar las acciones oportunas para su corrección.

Cuando la capa de transporte ya ha preparado los datos (PDU de transporte), los entrega a la **capa de acceso a la red** para que sean enviados por la red. Esta capa añade su propia **cabecera**, formando la **PDU de red**, en un nuevo proceso de encapsulación.

En esta cabecera se incluye información clave como la **dirección del computador destino**, que permite a la red saber a dónde enviar los datos, y posibles **solicitudes de recursos** (por ejemplo, prioridad). Así, la capa de acceso a la red transforma los datos en una forma que la red puede transmitir correctamente.