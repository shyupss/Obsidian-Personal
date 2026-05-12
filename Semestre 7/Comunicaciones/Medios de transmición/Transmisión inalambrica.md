En los medios no guiados, la transmisión y recepción de datos se realiza mediante el uso de una **antena**. La señal se propaga a través de la atmósfera, el espacio exterior o el agua.

Las características de la transmisión inalámbrica están determinadas principalmente por el ancho de banda de la señal emitida y la **direccionalidad**:

- **Frecuencias bajas:** Las señales suelen ser **omnidireccionales**, propagándose en todas direcciones desde la antena.
- **Frecuencias altas:** Es posible concentrar la energía en un **haz direccional**, lo que requiere una alineación precisa entre el emisor y el receptor.

---
# Antenas

Una antena es un conductor eléctrico utilizado para radiar o captar energía electromagnética. Existe una propiedad de **reciprocidad**: las características de una antena (como su ganancia o eficiencia) son idénticas tanto para la transmisión como para la recepción.
### Antena Isotrópica

Es un concepto ideal de referencia. Se trata de un punto en el espacio que radia potencia de manera uniforme en todas las direcciones posibles. Su diagrama de radiación es una esfera perfecta.
### Antena Parabólica de Reflexión

Utilizada frecuentemente en microondas terrestres y satelitales. Se basa en las propiedades geométricas del paraboloide:

- Las ondas originadas en el **foco** de la parábola se reflejan en trayectorias paralelas al eje, creando un haz concentrado.
- En la recepción, las ondas paralelas al eje que inciden sobre la parábola se concentran exactamente en el foco.
- A mayor diámetro de la antena, mayor es la direccionalidad del haz resultante.
### Ganancia de una Antena

La ganancia no implica un aumento de potencia total, sino una medida de la **direccionalidad**.

> Se define como la **potencia de salida en una dirección específica comparada con la potencia de una antena isotrópica ideal (en cualquier dirección).**

Un concepto relacionado con la *ganancia* de una antena es el **área efectiva**.

El área efectiva de una antena está relacionada con su tamaño físico y con su geometría. La relación entre la ganancia de una antena y su área efectiva viene dada por:
$$G=\frac{4\pi A_e}{λ^2}=\frac{4\pi A_ef^2}{c^2}$$
_Donde_ $f$ _es la frecuencia,_ $λ$ _la longitud de onda y_ $c$ _la velocidad de la luz._

| Tipo de Antena      | Área Efectiva (Ae​) | Ganancia (G) |
| ------------------- | ------------------- | ------------ |
| Isotrópica Ideal    | $λ^2/4π$            | $1$          |
| Parabólica (Área A) | $0,56\times A$      | $7A/λ^2$     |

---
# Micro-ondas Terrestres
### Descripción Física y Aplicaciones

Utilizan antenas parabólicas (típicamente de 3 metros de diámetro) situadas a gran altura para evitar obstáculos. Se basan en enlaces punto a punto concatenados para cubrir largas distancias.

- **Telecomunicaciones de larga distancia:** Alternativa a la fibra óptica y el cable coaxial. 
- **Bypass:** Permite a empresas conectar sus redes locales directamente con proveedores de larga distancia sin usar la red telefónica local.
- **Sistemas celulares:** Interconexión de estaciones base.
### Características de Transmisión

Operan en un rango de **1 a 40 GHz**. A mayor frecuencia, mayor ancho de banda y velocidad.
- **Atenuación:** Varía con el cuadrado de la distancia $(L=10log(4πd/λ)^2)$.
- **Factores adversos:** La lluvia causa atenuación significativa por encima de los $10[GHz]$. La congestión del espectro es un problema creciente, forzando el uso de bandas superiores ($11[GHz]$, $18[GHz]$ y $22[GHz]$).

---
# Microondas por Satélite

## Configuraciones y Órbita Geoestacionaria

**Un satélite** actúa como una estación repetidora de microondas. Recibe señales en una banda (canal ascendente), las amplifica y las retransmite en otra banda (canal descendente).

Para ser eficaz, el satélite debe permanecer en una **órbita geoestacionaria** a aproximadamente **35.863 km** sobre el Ecuador. Esto permite que mantenga una posición fija respecto a las estaciones terrestres.
### Aplicaciones y Tecnología VSAT

1. **Difusión de TV:** Su naturaleza de multidifusión lo hace ideal.
2. **Telefonía de larga distancia:** Enlaces internacionales de alta capacidad.
3. **Redes Privadas (VSAT):** Los terminales de pequeña abertura (_Very Small Aperture Terminal_) permiten a empresas establecer redes privadas de bajo coste conectando múltiples estaciones pequeñas a un concentrador central.
### Bandas de Frecuencia y Características

El rango óptimo de operación está entre 1 y 10 GHz.

- **Banda 4/6 GHz:** (Ascendente 5.9-6.4 GHz / Descendente 3.7-4.2 GHz). Está saturada.
- **Banda 12/14 GHz:** Permite receptores más pequeños y baratos, pero es sensible a la atenuación por lluvia.
- **Banda 20/30 GHz:** Ofrece mayor ancho de banda pero sufre una atenuación atmosférica superior.

***Propiedad crítica:** Debido a la distancia, existe un **retardo de propagación** de aproximadamente **1/4 de segundo** por salto (estación-satélite-estación), lo que afecta a conversaciones telefónicas y protocolos de control de flujo.*

---
# Ondas de Radio

A diferencia de las microondas, las ondas de radio en el rango de **30 MHz a 1 GHz** son **omnidireccionales**.

> Las ondas de radio no necesiten antenas parabólicas ni necesitan que dichas antenas estén instaladas sobre una plataforma rígida para estar alineadas.

- **Aplicaciones:** Radio FM, TV UHF/VHF y redes de datos locales.
- **Propagación:** La ionosfera es transparente a estas frecuencias, por lo que la comunicación es mediante trayectoria visual (LOS).
- **Ventajas:** Menos sensibles a la atenuación por lluvia que las microondas.
- **Desventajas:** Susceptibles a **interferencias por multitrayectorias** debido a reflexiones en la superficie terrestre u otros objetos.

---
# Infrarrojos

Las señales pueden seguir tres trayectorias principales dependiendo de su frecuencia:

1. **Superficial (Ground Wave):** Hasta 2 MHz. Sigue la curvatura de la tierra (ej. Radio AM).
2. **Aérea (Sky Wave):** De 2 a 30 MHz. Se refleja/refracta en la ionosfera, permitiendo saltos de miles de kilómetros (ej. Radio de onda corta).
3. **Trayectoria Visual (Line of Sight - LOS):** Por encima de 30 MHz. La comunicación requiere que las antenas se "vean" directamente.