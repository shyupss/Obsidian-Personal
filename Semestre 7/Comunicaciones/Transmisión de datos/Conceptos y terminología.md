La transmisión de datos se define como la comunicación entre un emisor y un receptor a través de un medio físico. El éxito de esta comunicación depende de la calidad de la señal y de las características del propio medio.

---
---
# Terminología utilizada en transmisión de datos.

## Medios de Transmisión (Guiados y No Guiados)
El medio es el camino físico por el cual se propagan las ondas electromagnéticas:
##### *Medios Guiados:*
Las ondas se confinan en un camino físico específico.
> Ejemplos: pares trenzados, cables coaxiales y fibras ópticas.
##### *Medios No Guiados (Inalámbricos):*
Las ondas se transmiten sin confinamiento físico, propagándose a través del aire, el mar o el vacío.
## Configuraciones de Enlace
##### *Enlace Directo:*
Camino de transmisión donde la señal ***viaja del emisor al receptor sin dispositivos intermedios,*** *exceptuando amplificadores o repetidores* (utilizados para aumentar la energía de la señal).
##### *Configuración Punto a Punto:*
Un enlace directo compartido exclusivamente por dos dispositivos.
##### *Configuración Multipunto:*
El medio de transmisión es compartido por más de dos dispositivos.
## Modos de Transmisión

La capacidad de flujo de datos se clasifica según la direccionalidad y simultaneidad:

|Modo|Descripción|Definición ANSI (EE.UU.)|Definición UIT-T|
|---|---|---|---|
|**Simplex**|La señal viaja en una sola dirección. Una estación siempre es emisora y la otra receptora.|Simplex|Half-Duplex|
|**Half-Duplex**|Ambas estaciones pueden transmitir y recibir, pero **no simultáneamente**.|Half-Duplex|Simplex|
|**Full-Duplex**|Ambas estaciones pueden transmitir y recibir **simultáneamente**.|Full-Duplex|Duplex|

---
---
# Frecuencia, Espectro y Ancho de Banda

Para caracterizar los sistemas de transmisión, las señales electromagnéticas deben analizarse tanto en el dominio del tiempo como en el de la frecuencia.

---
## Conceptos en el Dominio Temporal

Una señal es una función del tiempo que puede ser:

**Analógica:**
> La intensidad varía suavemente, sin saltos o discontinuidades.

**Digital:**
> La intensidad se mantiene constante durante un intervalo y luego cambia abruptamente a otro valor constante.
### Señales Periódicas y la Onda Seno

Una señal $s(t)$ es periódica si repite un patrón en el tiempo, cumpliendo la condición $s(t+T)=s(t)$ para todo $t$, donde $T$ es el periodo. La señal periódica fundamental es la onda seno, definida por: $$s(t)=Asen(2πft+ϕ)$$Los tres parámetros clave que definen esta señal son:
##### Amplitud (A):*
Valor máximo de la señal (generalmente en voltios).
##### Frecuencia (f):*
Rapidez con la que se repite la señal (en Hz, o ciclos por segundo). Se relaciona con el periodo como $T=\frac{1}{f}$.
##### Fase (ϕ):
Medida de la posición relativa de la señal dentro de un periodo.
### Longitud de Onda (λ)

Es la distancia física que ocupa un ciclo de la señal. Se relaciona con la velocidad de propagación $(v)$ y la frecuencia $(f)$ mediante la expresión: $$λ=v⋅T=\frac{v}{f}​$$
En el vacío, $v$ es igual a la velocidad de la luz $(c≈3×108[m/s])$

---
## Conceptos en el Dominio de la Frecuencia

**Para cada señal hay una función en el dominio del tiempo** $s(t)$ que determina la amplitud de la señal en cada instante del tiempo. Igualmente, hay una **función $S(f)$, en el dominio de la frecuencia, que especifica las amplitudes de pico de las frecuencias constitutivas de la señal.**

En la práctica, las señales no son ondas seno puras, sino que están compuestas por múltiples frecuencias.
#### **Análisis de Fourier:**
Demuestra que cualquier señal electromagnética está constituida por una colección de señales analógicas periódicas (ondas seno) con diferentes amplitudes, frecuencias y fases.
#### **Frecuencia Fundamental:**
Cuando todas las componentes de frecuencia son múltiplos enteros de una frecuencia base, esta se denomina frecuencia fundamental.
#### **Espectro:**
El conjunto de frecuencias que constituyen una señal.
#### **Ancho de Banda Absoluto:**
La anchura total del espectro (diferencia entre la frecuencia más alta y la más baja).
#### **Ancho de Banda Efectivo (o simplemente Ancho de Banda):**
Banda estrecha donde se concentra la mayor parte de la energía de la señal.
#### **Componente Continua (dc):**
Es una componente de frecuencia cero (f=0). Si una señal la contiene, su amplitud media será distinta de 0.

---
# Relación entre Velocidad de Transmisión y Ancho de Banda

Existe una relación intrínseca entre la velocidad a la que se envían los datos y el ancho de banda necesario. Aunque una señal digital (como una onda cuadrada) tiene teóricamente un ancho de banda infinito, los sistemas de transmisión reales son limitados.
## Aproximación de Ondas Digitales

Una onda cuadrada puede aproximarse sumando armónicos impares de su frecuencia fundamental f. Cuantos más armónicos se incluyan, más se parecerá la señal resultante a la onda cuadrada original y menor será la distorsión.

seguir...