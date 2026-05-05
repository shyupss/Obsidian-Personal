La **capacidad del canal** se define como la velocidad máxima a la que se pueden transmitir los datos en una ruta de comunicación bajo condiciones específicas.

En el diseño de sistemas de comunicaciones, el objetivo primordial es maximizar esta velocidad utilizando de manera eficiente el ancho de banda disponible, el cual es un recurso escaso y costoso, sin exceder una tasa de errores tolerable.

---
# Factores Determinantes en la Transmisión

| Factor                       | Descripción                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Velocidad de transmisión** | La rapidez con la que se envían los datos, medida en bits por segundo (bps).                                           |
| **Ancho de banda $B$**       | El rango de frecuencias de la señal transmitida, limitado por el transmisor y el medio físico, medido en hercios (Hz). |
| **Ruido ($N$)**              | El nivel promedio de interferencias no deseadas en el camino de la transmisión.                                        |
| **Tasa de errores**          | La proporción de bits recibidos incorrectamente (un 1 por un 0, o viceversa).                                          |

---
# Ancho de Banda de *Nyquist*

El análisis de Nyquist se centra en las **limitaciones de velocidad impuestas exclusivamente por el ancho de banda en un *entorno ideal*.**
## Canal Exento de Ruido

> En un canal sin ruido, la limitación de la velocidad viene dada por la anchura del espectro de la señal. 

Nyquist estableció que si una señal tiene un **ancho de banda** $B$, la mayor **velocidad de transmisión de señal** que puede soportar es $2B$.

Esta restricción se debe a la **interferencia entre símbolos** provocada por la distorsión de retardo. Para señales binarias (dos niveles de tensión), la capacidad $C$ es: 
$$C=2B$$
## Señalización Multinivel

Es posible incrementar la velocidad de transmisión utilizando más de dos niveles de tensión. Si un elemento de señal representa más de un bit, se utiliza la fórmula generalizada:
$$C=2B \times log_2M$$
Donde $M$ es el número de señales discretas o niveles de tensión.

***Ejemplo:***
> Con un ancho de banda de 3.100 Hz y M=8 niveles, la capacidad teórica sería de 18.600 bps.

**Limitación:**
>Aumentar M complica la tarea del receptor, ya que debe distinguir entre niveles más próximos en presencia de ruido.

*Entonces, se envía **más información (bits) en menos tiempo (pulsos)** **usando diferentes niveles de energía **, lo que permite que la velocidad de transmisión sea mayor para un mismo ancho de banda.*

---
# Fórmula para la Capacidad de Shannon

Mientras que Nyquist considera canales ideales, Shannon integra el ruido y la tasa de errores en su formulación.
## Relación Señal-Ruido (SNR)

La **SNR** es el cociente entre la **potencia de la señal** ($S$) y la **potencia del ruido** ($N$) ($SNR=\frac{S}{N}$), generalmente medida en el receptor. Se expresa comúnmente en decibelios (dB):
$$SNR_{db}=10 \times log_{10}(SNR)$$
*Una SNR alta significará una señal de alta calidad y, por tanto, la necesidad de un número reducido de repetidores.*

> **Si se incrementa la velocidad de transmisión de los datos, entonces habrá más bits durante el intervalo de duración del ruido y, por tanto, habrá un mayor número de errores.**
## El Límite Teórico de Shannon

La capacidad máxima teórica de un canal (capacidad libre de errores) se calcula mediante:
$$C=B \times log_2(1+SNR)$$
*La fórmula de Shannon representa el máximo límite teórico que se puede conseguir. Sin embargo, **en la práctica, se consiguen velocidades mucho menores.***

> Shannon demostró que **si la velocidad real es menor que C**, **existe teóricamente un código que permite una transmisión sin errores.**

***Estar por debajo del límite C es el requisito para poder aspirar a no tener errores, pero no es una garantía, porque todavía no tenemos el código perfecto y el ruido real es mucho más agresivo que el de la fórmula!!!***

---
# El Cociente $E_b​/N_0​$

Para sistemas de comunicación digital, el parámetro $E_b​/N_0​$​ **(energía de la señal por bit sobre densidad de potencia de ruido por hercio)** es más preciso que la SNR para medir el rendimiento.
## Definición y Parámetros

Se define como la relación entre la energía de la señal por bit y la densidad de potencia del ruido por hercio: $$\frac{E_b}{N_0}​​ = \frac{S/R}{N_0} = \frac{S}{kTR}$$donde:
- $S$ = **Potencia de la señal.**
- $R$ = **Velocidad de transmisión (bps).**
- $k$ = **Constante de Boltzmann.**
- $T$ = **Temperatura absoluta**

***En decibelios:*** 
$$(\frac{E_b}{N_0})_{dB}​​ = S_{dBW}-10logR+228,6_{dBW}-10logT$$
## Relación con la Tasa de Error

La tasa de error por bit es una función decreciente de $E_b​/N_0​$​. Si se aumenta la velocidad $R$, la duración del bit disminuye, lo que hace que el mismo nivel de ruido afecte a más bits.

Por lo tanto, para mantener una tasa de error constante **al aumentar la velocidad, se debe aumentar proporcionalmente la potencia de la señal.**
## Relación con la Eficiencia Espectral

La eficiencia espectral $(C/B)$ se puede relacionar con $E_b​/N_0$​ mediante una derivación de la fórmula de Shannon:
$$\frac{E_b}{N_0} = \frac{B}{C}(2^{C/B}-1)$$
Este parámetro permite comparar cuán cerca está un esquema de modulación real del límite teórico de Shannon.

> Por ejemplo, para obtener una eficiencia espectral de 6 bps/Hz, se requiere un $E_b/N_0$​ mínimo de $10,21dB$.