> Los términos **analógico y digital** corresponden respectivamente, por lo general, a **continuo y discreto.** 

Estos dos términos se aplican con frecuencia en el marco de las comunicaciones en al menos tres contextos diferentes: datos, señalización y transmisión.

Para comprender la transmisión de datos, es imperativo distinguir entre cuatro conceptos que a menudo se confunden pero que operan en niveles diferentes:
- **Dato:** Cualquier entidad capaz de transportar información.
- **Señal:** Representación eléctrica o electromagnética de los datos.
- **Señalización:** El acto físico de propagación de las señales a través de un medio adecuado.
- **Transmisión:** Comunicación de datos mediante la propagación y el procesamiento de las señales.
---
# DATOS Analógicos y Digitales

La distinción principal entre datos analógicos y digitales reside en la continuidad de sus valores.
##### **Datos Analógicos:**
Toman valores en un intervalo continuo. Ejemplos comunes incluyen el sonido (voz y música) y valores capturados por sensores de presión o temperatura.
##### **Datos Digitales:**
Toman valores discretos, como números enteros o cadenas de texto.

---
# SEÑALES Analógicas y Digitales

En un sistema de comunicaciones, los datos se propagan de un punto a otro mediante señales electromagnéticas.
#### ***Señal analógica***
Es una onda electromagnética que varía continuamente y que, según sea su espectro, puede propagarse a través de una serie de medios; por ejemplo, a través de un medio guiado como un par trenzado, un cable coaxial, un cable de fibra óptica, o a través de medios no guiados, como la atmósfera o el espacio.
#### ***Señal digital***
Una señal digital es una secuencia de pulsos de tensión que se puede transmitir a través de un medio conductor; por ejemplo, un nivel de tensión positiva constante puede representar un 0 binario y un nivel de tensión negativa constante puede representar un 1.

| Característica  | Señal Analógica                                       | Señal Digital                                                |
| --------------- | ----------------------------------------------------- | ------------------------------------------------------------ |
| **Definición**  | Onda electromagnética que varía continuamente.        | Secuencia de pulsos de tensión constantes.                   |
| **Medios**      | Par trenzado, cable coaxial, fibra óptica, atmósfera. | Medios conductores (principalmente).                         |
| **Ventajas**    | Menor atenuación inicial en distancias cortas.        | Más económica y menos susceptible a interferencias de ruido. |
| **Desventajas** | Sensible al ruido acumulativo.                        | Sufre una atenuación más pronunciada (redondeo de pulsos).   |
## Relación entre Datos y Señales

No existe una correspondencia exclusiva entre el tipo de dato y el tipo de señal. **Un dato analógico puede ser transportado por una señal digital y viceversa.**
#### **Datos Analógicos en Señales Analógicas:**
> La señal ocupa el mismo espectro que los datos (ej. telefonía convencional).
#### **Datos Digitales en Señales Digitales:**
> Se usan niveles de tensión para representar valores binarios (ej. conexión directa entre PC).
#### **Datos Digitales en Señales Analógicas:**
> Requiere un **módem**.
#### **Datos Analógicos en Señales Digitales:**
> Requiere un **codec**.
### Componentes de Conversión: Módem y Codec

**Módem (Modulador-Demodulador):**
> Convierte pulsos digitales en una señal analógica **mediante la modificación de una frecuencia portadora.**

**Codec (Codificador-Decodificador):**
> Toma una señal analógica (como la voz) y la aproxima mediante una cadena de bits para su transmisión digital, permitiendo luego su reconstrucción en el destino.

---
# TRANSMISIÓN Analógica y Digital

Tanto las señales analógicas como las digitales se pueden transmitir si se emplea el medio de transmisión adecuado.

*La transmisión se define por cómo el sistema trata las señales mientras viajan por el medio.*
## Tratamiento de Señales: Amplificadores vs. Repetidores

#### **Transmisión Analógica:**
> Se enfoca en propagar la señal sin importar su contenido. Para cubrir distancias largas, emplea **amplificadores**. Sin embargo, el amplificador no distingue entre la señal útil y el ruido, por lo que amplifica ambos, distorsionando la información de manera acumulativa.

*Los datos analógicos, como la voz, se puede tolerar una pequeña distorsión, ya que en ese caso los datos siguen siendo inteligibles.*
#### **Transmisión Digital:**
> Es dependiente del contenido. Para superar la atenuación, utiliza **repetidores**. El repetidor recibe la señal degradada, recupera el patrón original de unos y ceros (lo regenera) y retransmite una señal limpia. Esto evita la acumulación de ruido.

***Si una señal analógica transporta datos digitales, se utilizan **repetidores** en lugar de amplificadores para evitar que el ruido se acumule.*
## Ventajas de la Transformación Digital

La industria se ha decantado por la transmisión digital por cinco razones fundamentales:

- **Tecnología Digital:** La integración a gran escala (LSI/VLSI) ha reducido drásticamente los costes y el tamaño de los circuitos
- **Integridad de los Datos:** El uso de repetidores permite mantener la calidad de la información a distancias mayores y sobre medios de menor calidad.
- **Utilización de la Capacidad:** Facilita la multiplexación (especialmente la división en el tiempo), lo que permite aprovechar el gran ancho de banda de la fibra óptica y los satélites de forma económica.
- **Seguridad y Privacidad:** Las técnicas de cifrado se aplican de forma nativa y sencilla a los datos digitales.
- **Integración:** Al tratar todas las señales (voz, vídeo, datos) como flujos de bits idénticos, se logra una economía de escala en el procesamiento de la información.