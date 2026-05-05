En cualquier sistema de comunicaciones, la señal recibida difiere de la señal transmitida debido a diversas adversidades en el medio de transmisión. 

En las **señales analógicas**, estas dificultades degradan la calidad de la información, afectando potencialmente la inteligibilidad. En las **señales digitales**, los defectos introducen bits erróneos (transformando ceros en unos y viceversa). 

El éxito de la transmisión depende de la calidad de la señal y las características del medio, siendo imperativo para el diseñador paliar los efectos de la atenuación, la distorsión de retardo y el ruido.

---
# Atenuación

La atenuación es el decaimiento de la energía de la señal a medida que aumenta la distancia a través de cualquier medio de transmisión. En medios guiados, esta reducción es generalmente exponencial, expresándose habitualmente en decibelios (dB) por unidad de longitud. En medios no guiados, la atenuación es una función más compleja de la distancia y las condiciones atmosférica.
## Consideraciones Fundamentales

Para garantizar una comunicación efectiva, el sistema debe abordar tres factores críticos respecto a la atenuación:
##### **Energía suficiente:**
La señal recibida debe poseer la energía necesaria para que la circuitería electrónica del receptor pueda detectarla adecuadamente.
##### **Relación Señal/Ruido:**
La señal debe mantener un nivel significativamente superior al ruido para ser recibida sin errores.
##### **Dependencia de la Frecuencia:**
La atenuación no es constante; habitualmente es una función creciente de la frecuencia.
## Distorsión de Atenuación

Este fenómeno es **especialmente relevante en señales analógicas.** Debido a que la **atenuación varía según la frecuencia**, las distintas componentes de una señal compleja se ven reducidas en diferentes proporciones, lo que resulta en una señal recibida distorsionada.

En señales digitales, este problema es menor, ya que la mayor parte de la energía se concentra en torno a la frecuencia fundamental o velocidad de transmisión (bps).
## Técnicas de Mitigación

1. **Amplificadores y Repetidores:** Se utilizan para realzar la energía de la señal periódicamente. *En enlaces punto a punto, la energía inicial debe ser alta pero no excesiva para evitar la saturación de la circuitería.*
2. **Ecualización:** Para suavizar los efectos de la atenuación en una banda de frecuencias, se emplean técnicas que ecualizan la línea. *En telefonía, se utilizan **bobinas de carga** que modifican las propiedades eléctricas de la línea o amplificadores que potencian más las frecuencias altas que las bajas para "aplanar" la respuesta del canal.*

---
# Distorsión de Retardo

La distorsión de retardo es un **fenómeno exclusivo de los medios guiados**, causado por el hecho de que la *velocidad de propagación de la señal varía según la frecuencia*.
##### ***Naturaleza del Fenómeno***
Para una señal limitada en banda, la **velocidad de propagación tiende a ser máxima** cerca de **la frecuencia central** y *disminuye al acercarse a los extremos de la banda*. 
> *Esto provoca que las diferentes componentes en frecuencia de una misma señal lleguen al receptor en instantes de tiempo distintos, resultando en desplazamientos de fase entre ellas.*
##### ***Interferencia entre Símbolos***
Este retardo variable es crítico para la transmisión de datos digitales. Los componentes de un bit pueden desplazarse temporalmente hasta invadir la posición de bits adyacentes, provocando **interferencia entre símbolos**.
> *Este factor es una de las **limitaciones primordiales para la velocidad máxima de transmisión en un canal**. Al igual que con la atenuación, se pueden emplear técnicas de ecualización para compensar este efecto.*

---
# Ruido

El ruido se define como las **señales no deseadas que se insertan en el sistema de comunicación** *en cualquier punto entre el emisor y el receptor*. Es el factor limitante más importante de las prestaciones de un sistema de comunicación.
#### ***Ruido Térmico (Ruido Blanco)***
Se origina por la agitación térmica de los electrones y está presente en todos los dispositivos electrónicos y medios de transmisión.

- **Características:** Se distribuye uniformemente en el espectro de frecuencias.
- **Inevitabilidad:** No se puede eliminar, imponiendo un límite superior teórico a las prestaciones del sistema.

> Es especialmente crítico en comunicaciones satelitales debido a la debilidad de la señal recibida.

***Formulación:***
La densidad de potencia del ruido $(N_0​)$ en un ancho de banda de $1[Hz]$ es:$$N_0=kT(W/Hz)$$donde:
- $N_0$ : **Densidad de potencia del ruido,** en vatios por 1 Hz de ancho de banda.
- $k$ : Constante de Boltzmann $(1,38 \times 10^{-23} J/K)$.
- $T$ : Temperatura absoluta, en Kelvin's.

> El ruido total $(N)$ en un ancho de banda $B$ es: $N=kTB$
#### ***Ruido de Intermodulación***

Ocurre cuando señales de diferentes frecuencias comparten el mismo medio de transmisión.

- **Causa:** Se produce por no linealidades en el transmisor, receptor o sistema de transmisión. Un sistema ideal es lineal $(salida = entrada × constante)$, pero las sobrecargas o fallos de funcionamiento crean comportamientos no lineales.
- **Efecto:** Aparecen señales a frecuencias que son suma, diferencia o múltiplos de las frecuencias originales (ej. $f1​+f2​$), las cuales pueden interferir con señales legítimas en esas frecuencias.
#### ***Diafonía (Crosstalk)***

Esto lo ha podido experimentar todo aquel que al usar un teléfono haya oído otra conversación; se trata, en realidad, de un **acoplamiento no deseado entre las líneas que transportan las señales.**

- **Mecanismo:** Ocurre por **acoplamiento eléctrico** entre pares de cables cercanos o por la **captación de energía dispersa en antenas de microondas** (a pesar de su direccionalidad).

> Su magnitud suele ser igual o inferior al ruido térmico.
#### ***Ruido Impulsivo***

A diferencia de los anteriores, es no continuo y consiste en pulsos irregulares de corta duración y gran amplitud.

> Se generan por una gran diversidad de causas, por ejemplo, por perturbaciones electromagnéticas exteriores producidas por tormentas atmosféricas o por fallos y defectos en los sistemas de comunicación.

**Este ruido no tiene mucha transcendencia para los datos analógicos.** 
*Por ejemplo, la transmisión de voz se puede perturbar mediante chasquidos o crujidos cortos, sin que ello implique pérdida significativa de inteligibilidad*

**Pero es una de las fuentes principales de error en la comunicación *digital* de datos**.
*Por ejemplo, un pico de energía con duración de 0,01 s no inutilizaría datos de voz, pero podría corromper aproximadamente 560 bits si se transmitieran a 56 kbps.*