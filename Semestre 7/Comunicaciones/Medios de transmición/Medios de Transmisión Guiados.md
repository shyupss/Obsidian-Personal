Los medios guiados se evalúan en función de su capacidad de transmisión (velocidad o ancho de banda) y su configuración (punto a punto o multipunto). A continuación, se detallan los tres medios más utilizados.

---
# Par Trenzado

Es el medio de transmisión más económico y el de uso más extendido a nivel global.

> Consiste en dos conductores de cobre aislados, entrelazados en forma de espiral. El trenzado tiene como objetivo fundamental reducir las interferencias electromagnéticas (diafonía) entre pares adyacentes. 

> En cables multipar, se utilizan diferentes pasos de torsión para minimizar el acoplamiento. El grosor del conductor varía entre 0,4 mm y 0,9 mm.
### Aplicaciones (Par Trenzado)

- **Telefonía:** Constituye el "bucle de abonado" que conecta el terminal con la central local y las conexiones internas a centrales privadas (PBX).
- **Redes de Área Local (LAN):** Soporta velocidades desde 10 Mbps hasta 1 Gbps (aunque esta última con limitaciones de distancia).
- **Comunicaciones Digitales:** Conexiones a conmutadores digitales a 64 Kbps y enlaces de larga distancia de hasta 4 Mbps.
### Características de Transmisión (Par Trenzado)

- **Señales Analógicas:** Requiere amplificadores cada 5-6 km. Ancho de banda de hasta 1 MHz.
- **Señales Digitales:** Requiere repetidores cada 2-3 km.
- **Limitaciones:** Alta susceptibilidad a interferencias, ruido impulsivo y acoplamiento con campos electromagnéticos externos (como líneas de potencia). Presenta una fuerte dependencia de la atenuación con la frecuencia.
### Variantes: UTP y STP

- **UTP (Unshielded Twisted Pair):** Par trenzado sin apantallar. Es el más barato y sencillo de instalar, común en telefonía y redes preinstaladas en edificios.
- **STP (Shielded Twisted Pair):** Par trenzado apantallado con malla metálica. Reduce las interferencias externas y ofrece mejores prestaciones a altas velocidades, pero es más costoso y difícil de manipular.
### Categorías y Estándares (EIA-568-A)

| Tipo/Categoría | Frecuencia Máxima | Aplicación Típica                                                    |
| -------------- | ----------------- | -------------------------------------------------------------------- |
| **Tipo 3**     | 16 MHz            | Calidad telefónica, hasta 16 Mbps en LAN.(paso de trenza 7,6-10 cm). |
| **Tipo 4**     | 20 MHz            | Uso limitado.                                                        |
| **Tipo 5**     | 100 MHz           | Calidad de datos, hasta 100 Mbps (paso de trenza 0,6-0,85 cm).       |
### Comparativa de Prestaciones de Pares Trenzados (EIA-568-A)

| Frecuencia (MHz) | Atenuación UTP Tipo 5 (dB/100m) | Diafonía UTP Tipo 5 (dB) |
| ---------------- | ------------------------------- | ------------------------ |
| 1                | 2,0                             | 62                       |
| 16               | 8,2                             | 44                       |
| 100              | 22,0                            | 32                       |
Existen alternativas de altas prestaciones como el **Tipo 6** (hasta 200-250 MHz) y el **Tipo 7 o SSTP*
(Shielded-Screen Twisted Pair), que utiliza apantallamiento individual por par para alcanzar frecuencias de 600 MHz a 1200 MHz.

---
# Cable Coaxial

Diseñado para operar en rangos de frecuencia superiores al par trenzado, permitiendo mayores velocidades y distancias.

> **Consta de dos conductores:** un cable interior central rodeado por un conductor cilíndrico exterior. Ambos están separados por un material aislante (dieléctrico) o anillos aislantes. El conjunto se protege con una cubierta exterior. Su diámetro oscila entre 1 cm y 2,5 cm.

### Aplicaciones (Cable Coaxial)

1. **Distribución de TV:** CATV (Community Antenna Television), capaz de transportar cientos de canales a decenas de kilómetros.
2. **Telefonía a larga distancia:** Puede transportar más de 10.000 canales de voz simultáneos mediante multiplexación FDM.
3. **Enlaces de computadores:** Conexiones de alta velocidad a corta distancia (entrada/salida).
4. **LAN de alta velocidad.**
### Características de Transmisión (Cable Coaxial)

- **Rendimiento:** Respuesta en frecuencia superior al par trenzado; espectro analógico hasta 500 MHz.
- **Inmunidad:** Menos susceptible a interferencias y diafonía gracias a su construcción apantallada.
- **Limitaciones:** Atenuación, ruido térmico y ruido de intermodulación (este último en sistemas FDM).
- **Repetidores:** En transmisión digital, requiere repetidores aproximadamente cada 1 km.

---
# Fibra Óptica

Representa uno de los avances más disruptivos, ofreciendo capacidades y velocidades de transmisión órdenes de magnitud superiores a los medios basados en cobre.
### Descripción Física (Fibra Óptica)

> Medio flexible y delgado (2 a 125 µm). Se compone de tres secciones:

1. **Núcleo:** Una o varias fibras de cristal (silicio ultrapuro) o plástico.
2. **Revestimiento:** Cristal o plástico con propiedades ópticas distintas al núcleo para confinar la luz mediante reflexión.
3. **Cubierta:** Capa exterior de plástico para protección contra humedad, abrasión y aplastamiento.
### Aplicaciones y Ventajas Diferenciales

- **Mayor Capacidad:** Velocidades de cientos de Gbps en decenas de kilómetros.
- **Menor Tamaño y Peso:** Significativamente más ligera y delgada que el cobre.
- **Atenuación Menor:** Constante en un gran intervalo y mucho más baja que en coaxial o par trenzado.
- **Aislamiento Electromagnético:** No le afectan campos exteriores, no radia energía (privacidad) y es difícil de interceptar.
- **Mayor Separación entre Repetidores:** Típicamente decenas de kilómetros (hasta cientos experimentalmente).
### Características de Transmisión y Modos de Propagación

La luz se propaga mediante **reflexión total** dentro del núcleo. Existen tres modos principales:
##### **Multimodo de Índice Discreto:**
Múltiples rayos de luz siguen diferentes caminos, causando dispersión temporal de los pulsos. Adecuado para distancias cortas.
##### **Multimodo de Índice Gradual:**
El índice de refracción del núcleo varía gradualmente. La luz periférica viaja más rápido y sigue trayectorias helicoidales, compensando la longitud del camino y permitiendo que la luz llegue al receptor casi al mismo tiempo que los rayos axiales. Común en LAN.
##### **Monomodo:**
El núcleo se reduce al orden de magnitud de la longitud de onda de la luz, permitiendo un solo camino (rayo axial). Elimina la distorsión multimodo. Ideal para larga distancia (telefonía y TV por cable).
# Fuentes de Luz y Ventanas de Transmisión

Se utilizan dos tipos de dispositivos semiconductores:

- **LED (Light Emitting Diode):** Económico, mayor vida útil, opera en rangos de temperatura amplios.
- **ILD (Injection Laser Diode):** Funcionamiento tipo láser, más eficaz y soporta mayores velocidades de transmisión.

La transmisión se realiza en la zona infrarroja del espectro (por debajo del espectro visible) en cuatro "ventanas" principales:

| Ventana (Longitud de Onda) | Frecuencia Aproximada | Tipo de Fibra   |
| -------------------------- | --------------------- | --------------- |
| 820 a 900 nm               | 33 THz                | Multimodo (LAN) |
| 1280 a 1350 nm (Banda S)   | 222-234 THz           | Monomodo        |
| 1528 a 1561 nm (Banda C)   | 192-196 THz           | Monomodo (WDM)  |
| 1561 a 1620 nm (Banda L)   | 185-192 THz           | Monomodo (WDM)  |
_Nota técnica: Aunque la frecuencia de la señal no cambia, la longitud de onda dentro de la fibra es inferior a la longitud de onda en el vacío debido a que la velocidad de propagación en la fibra es aproximadamente $2,04×10^8 [m/s]$._