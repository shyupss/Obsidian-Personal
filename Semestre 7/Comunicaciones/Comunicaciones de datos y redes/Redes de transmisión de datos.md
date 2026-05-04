### Problemas de conexión directa
Muchas veces no es práctico conectar dispositivos mediante enlaces **punto a punto**, ya que:
- **Gran distancia**: no es viable usar enlaces dedicados entre dispositivos muy alejados.
- **Gran número de dispositivos**: el número de conexiones crece rápidamente y se vuelve impracticable.
### Solución $\rightarrow$ Usar redes de comunicación
Utilizar una **red de comunicación**, donde cada dispositivo se conecta a la red en lugar de conectarse directamente con todos los demás.
### Clasificación de redes  
Las redes se clasifican tradicionalmente en:  
- **WAN (Wide Area Network)**: Redes de **gran cobertura** geográfica.
- **LAN (Local Area Network)**: Redes de **alcance local**.

> Esta clasificación es cada vez menos estricta, pero sigue siendo útil para el estudio.
## Redes WAN (Wide Area Network)
Las redes WAN son aquellas que cubren grandes áreas geográficas y utilizan, total o parcialmente, infraestructura de telecomunicaciones proporcionada por terceros.
### Características  
- requieren el uso de redes de acceso público  
- emplean circuitos de proveedores de telecomunicaciones  
- están formadas por dispositivos de conmutación interconectados
### Funcionamiento  
La información se transmite a través de una serie de nodos intermedios, los cuales:  
- encaminan los datos hacia el destino  
- no interpretan el contenido de la información  
- permiten la transmisión de nodo en nodo hasta el destino final
### Tecnologías de implementación  
Tradicionalmente, las WAN se han basado en:  
- **Conmutación de circuitos**  
- **Conmutación de paquetes**  
  
Actualmente también se utilizan tecnologías como:  
- **Frame Relay**  
- **ATM (Asynchronous Transfer Mode)**S

> En una WAN los datos no viajan directamente, sino a través de nodos de conmutación.

<hr>
### Conmutación de circuitos
La conmutación de circuitos es una técnica en la que se establece un camino dedicado entre el origen y el destino antes de transmitir los datos, reservando los recursos durante toda la comunicación.
#### Funcionamiento  
1. **Establecimiento de conexión**  
	Se crea un camino extremo a extremo entre los dispositivos.  
2. **Transmisión**  
	Los datos se envían de forma continua a través del circuito establecido.  
3. **Liberación**  
	Se finaliza la conexión y se liberan los recursos utilizados.
#### Características  
- Camino fijo entre origen y destino  
- Recursos reservados durante toda la comunicación  
- Transmisión continua y sin interrupciones  
- No requiere decisiones de encaminamiento durante la transmisión
#### Ventajas  
- Comunicación estable  
- Latencia constante  
- No hay pérdida ni desorden de datos
#### Desventajas  
- Uso ineficiente del canal  $\rightarrow$ Si la conexión se establece pero no se usa, el canal estará ocupado.
- Los recursos permanecen ocupados aunque no haya transmisión  
- Baja flexibilidad frente a cambios en la red

<hr>
### Conmutación de paquetes
La conmutación de paquetes es una técnica en la que los datos se dividen en unidades llamadas paquetes, los cuales se transmiten a través de la red sin un camino fijo, siendo reenviados de nodo en nodo hasta alcanzar el destino.
#### Funcionamiento  
1. **División de datos**
	El mensaje se divide en múltiples paquetes.
2. **Transmisión**  
	Cada paquete se envía de forma independiente a través de la red.
3. **Conmutación en nodos**  
	En cada nodo, el paquete:  
	- se recibe completamente  
	- se almacena temporalmente  
	- se retransmite al siguiente nodo
4. **Entrega**  
	Los paquetes llegan al destino, donde se reconstruye el mensaje original.
#### Características  
- No requiere establecimiento previo de conexión  
- No hay reserva de recursos  
- Los paquetes pueden seguir rutas distintas  
- Utiliza el mecanismo de **store-and-forward**  
- Uso eficiente del medio de transmisión
#### Ventajas  
- Uso eficiente de los recursos  
- Alta flexibilidad  
- Permite múltiples comunicaciones simultáneas
#### Desventajas  
- Latencia variable  
- Posible pérdida de paquetes  
- Posible desorden en la llegada de datos

<hr>
### Frame relay
Frame Relay es una técnica de conmutación de paquetes optimizada que reduce el control de errores y el procesamiento en los nodos intermedios, delegando estas funciones a los sistemas finales para mejorar la velocidad de transmisión.
#### Contexto  
Las redes de conmutación de paquetes tradicionales fueron diseñadas en entornos con altas tasas de error, por lo que incorporaban:  
- detección y corrección de errores en la red  
- información redundante en los paquetes  
- procesamiento en cada nodo
#### Motivación  
Con la mejora de los medios de transmisión:  
- la tasa de errores disminuyó  
- el control de errores en la red se volvió innecesario  
- el procesamiento adicional reducía la eficiencia
#### Funcionamiento
Frame Relay simplifica la red mediante:  
- eliminación de la mayor parte del control de errores en los nodos intermedios
- reducción de la información redundante
- disminución del procesamiento en la red

Las funciones de control de errores se trasladan principalmente a los sistemas finales.
#### Características  
- basado en conmutación de paquetes  
- menor procesamiento en la red  
- mayor velocidad de transmisión  
- mejor aprovechamiento del ancho de banda
#### Ventajas  
- alta eficiencia  
- mayor velocidad  
- menor sobrecarga en la red
#### Desventajas  
- menor control de errores dentro de la red  
- dependencia de los sistemas finales para garantizar la integridad

<hr>
### ATM (Asynchronous Transfer Mode)
ATM es una técnica de conmutación basada en celdas de tamaño fijo que combina características de la conmutación de paquetes y de circuitos, permitiendo una transmisión eficiente y con comportamiento predecible mediante el uso de canales virtuales.
#### Contexto  
ATM surge como una evolución de:  
- conmutación de paquetes  
- retransmisión de tramas (Frame Relay)  

Su objetivo es mejorar la eficiencia y velocidad de transmisión en redes de alta capacidad.
#### Característica principal  
A diferencia de otras técnicas:  
- utiliza **celdas de tamaño fijo**  
- reduce el procesamiento en los nodos intermedios

> Frame Relay → tramas variables  
> ATM → celdas fijas
### Funcionamiento
- los datos se dividen en celdas de tamaño fijo  
- las celdas se transmiten a través de la red  
- los nodos intermedios las encaminan con mínimo procesamiento  
- el control de errores se delega principalmente a los sistemas finales
#### Canales virtuales
Un canal virtual es una conexión lógica establecida entre dos extremos en una red ATM, que define un camino preconfigurado por el cual se transmiten las celdas.
#### Características  
- alta velocidad de transmisión (Mbps a Gbps)  
- bajo procesamiento en la red  
- uso de celdas de tamaño fijo  
- comportamiento similar a conmutación de circuitos
#### Ventajas    
- alta eficiencia  
- baja latencia  
- transmisión predecible  
- adecuado para aplicaciones en tiempo real
#### Desventajas  
- mayor complejidad conceptual  
- menor flexibilidad que packet switching puro

<hr>
## Redes LAN (Local Area Network)
Una LAN (Local Area Network) es una red de comunicación que conecta dispositivos en un área geográfica reducida, generalmente bajo una misma administración, permitiendo el intercambio de información a alta velocidad.
### Características  
- cobertura geográfica limitada (edificio o conjunto de edificios)  
- propiedad privada (misma entidad que los dispositivos)  
- gestión local de la red  
- altas velocidades de transmisión
### Implicaciones  
- el usuario es responsable de la configuración y administración de la red  
- requiere inversión en infraestructura y mantenimiento  
- permite un mayor control sobre el funcionamiento de la red
### Tipos de LAN  
##### LAN conmutadas  
- basadas en conmutadores (switches)  
- ejemplo: Ethernet  
##### LAN inalámbricas  
- utilizan tecnologías inalámbricas  
- ejemplo: WiFi  
##### Otras tecnologías  
- LAN ATM  
- Fiber Channel

<hr>
### Redes inalámbricas
Las redes inalámbricas son redes de comunicación que utilizan medios de transmisión no guiados, como ondas electromagnéticas, para conectar dispositivos sin necesidad de cableado físico.
#### Ámbitos de uso  
- **LAN inalámbricas**: redes locales (ej: WiFi)  
- **WAN inalámbricas**: redes de gran cobertura (ej: redes móviles)
#### Ventajas
- alta movilidad  
- facilidad de instalación  
- flexibilidad en la conexión

<hr>
### Redes de área metropolitana (MAN)
Una MAN (Metropolitan Area Network) es una red que cubre un área geográfica intermedia, como una ciudad, proporcionando alta capacidad de transmisión a un costo relativamente bajo.
#### Contexto
Las MAN surgen como una solución intermedia entre LAN y WAN, cuando las tecnologías tradicionales de WAN no resultan adecuadas para ciertas necesidades de capacidad en áreas urbanas.
#### Características
- cobertura metropolitana (ciudades o áreas urbanas)  
- alta capacidad de transmisión  
- menor costo en comparación con soluciones WAN tradicionales  
- pueden utilizar infraestructura pública o privada
#### Tecnologías utilizadas
Las MAN emplean tecnologías adaptadas a entornos urbanos, tales como:  
- **Redes inalámbricas**: permiten cubrir grandes áreas sin necesidad de cableado  
- **Ethernet metropolitano (Metro Ethernet)**: extensión de tecnologías LAN para operar a escala urbana
#### Uso típico
Las MAN están orientadas a organizaciones que requieren alta capacidad dentro de una ciudad, tales como:
- empresas con múltiples sedes  
- instituciones públicas  
- universidades