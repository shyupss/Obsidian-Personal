### ¿Qué ocurre si el transmisor y receptor tienen velocidades de reloj ligeramente diferentes? ¿Cómo se resuelve en protocolos reales?

Si las velocidades de reloj del transmisor y receptor son distintas, entonces se producirá un ***desfase progresivo en la interpretación de bits***.

Para que esto no pase, en protocolos reales se aplican mecanismos de sincronización, control de flujo. Por ejemplo, una secuencia de start/stop bits (para determinar cuando comienza, termina), clock recovery, etc.
#### Para nuestro caso de estudio

Tenemos dos arduinos en comunicación, uno emisor y otro receptor, donde si ambos tiempos de reloj coinciden no hay problema, pero hay dos casos que vale la pena analizar.

**Caso 1 - Emisor más rápido que receptor:**  Si el emisor tiene un timer más rápido, entonces las duraciones de los puntos, rayas y espacios serán menores, lo que puede generar errores luego en la decodificación. Esto se puede mitigar en cierta parte usando rangos de tolerancia para clasificar cada input más grande.

Es importante notar también que, aunque el emisor transmita información en menos tiempo, no hay problemas de velocidad, ni de flujo de datos, ya que no existe alguna transmisión continua ni buffers intermedios. Por ende no es necesario aplicar mecanismos de control de flujo de datos, sino mecanismos de sincronización temporal para la correcta interpretación.

**Caso 2 - Receptor más rápido que emisor:**  En caso de que el receptor tenga un timer más rápido, este mide duraciones más cortas. Esto lleva a que las rayas se puedan confundir con puntos, o los espacios entre letras con espacio entre símbolos. 

El tipo de problema es de sincronización, similar al caso anterior. Por ende la forma de mitigarlo sería similar, se podrían utilizar rangos de tolerancia mas grandes para clasificar las señales.

---
### ¿Cuántos bits por segundo transmite este sistema usando la constante de tiempo definida?

(ustedes saben cabros)

---
### Seguridad

**Este sistema transmite en texto plano a través de un canal eléctrico. Cualquier persona con acceso físico al cable puede leer la señal con un multímetro o un osciloscopio. Discutir: *¿Qué se necesitaría agregar para que la comunicación fuera confidencial?* Introducir el concepto de cifrado como capa adicional sobre la codificación.**

Un cifrado, es una técnica para ocultar información mediante propiedades, llaves, secuencia de pasos, etc. Es útil para cuando se quiere que el únicamente el destino conozca cierto mensaje recibido.

Entonces para que la comunicación sea lo más confidencial posible, se debería de agregar un mecanismo de ***cifrado*** para que la información que viaja mediante el cable que comunica ambos dispositivos no contenga la información en "crudo", sino que solo pueda ser interpretada por el receptor deseado.

Sin embargo, si se obtiene la clave la información se puede recuperar. Entonces también es necesario un ***mecanismo de gestión de claves***. Esto se puede hacer mediante ***claves compartidas (cifrado simétrico)*** o por medio de ***criptografía de llave pública***, así solamente las partes legítimas que pertenezcan a la comunicación podrán descifrar el mensaje.

Por ende, aun que una persona quiera interferir en la comunicación o extraer información del medio, no sabría interpretarla correctamente, así mantenemos la confidencialidad.
#### Para nuestro caso de estudio

Tenemos una comunicación del tipo ***Simplex***, en el cual la comunicación entre los arduinos se realiza mediante símbolos ASCII ('.', '-', ' ', '/') a través de comunicación serial. Entonces la información viaja sin cifrar, por ende es directamente interpretable.

Para buscar confidencialidad, sería necesario cifrar la información antes de enviarla, y que esta al llegar con el receptor, haga el proceso de decodificación. Como son dos dispositivos concretos, se podría usar una clave en común para el cifrado, y aplicar alguna operación reversible (como XOR) con aquella clave.

De esta forma, el mensaje enviado mediante el cable, aun que sea interceptado por algún externo, estará oculto, manteniendo la privacidad de la comunicación. 

---
### ¿Es este sistema síncrono o asíncrono? ¿Por qué?

Este sistema es ***asíncrono***, ya que no existe ningún reloj compartido entre el transmisor y el receptor. La información se transmite mediante eventos (pulsaciones), por lo que el receptor interpreta la información sin tener ninguna referencia temporal fija.

---
### Relaciona este experimento con el modelo OSI: ¿en qué capa opera el código Morse?****

Para este experimento, el código morse correspondería a la ***capa de aplicación***, ya que no se encarga de la transmisión física de la señal, sino de como se estructura y codifica el mensaje que será transmitido.