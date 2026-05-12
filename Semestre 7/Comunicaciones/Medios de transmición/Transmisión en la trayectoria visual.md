# Pérdida en el Espacio Libre

La pérdida en el espacio libre es la causa principal de atenuación en comunicaciones inalámbricas, especialmente en enlaces satelitales. 

> Se produce porque la señal se dispersa en un área cada vez mayor a medida que se aleja de la fuente.
### Definición y Modelado Matemático

Para una **antena isotrópica ideal** (que radia por igual en todas las direcciones), la pérdida se define como el cociente entre la potencia radiada $(P_t​)$ y la potencia recibida $(P_r​)$:
$$\frac{P_t}{P_r}=\frac{(4\pi d)^2}{λ^2}=\frac{(4\pi d f)^2}{c^2}$$
En decibelios $(dB)$, la fórmula se expresa como:
$$L_{dB}=20log(f)+20log(d)-147,56$$
donde:
- f: Frecuencia en Hercios.
- d: Distancia en metros.
- c: Velocidad de la luz (≈3×108 m/s).
### Impacto de la Ganancia de la Antena

En sistemas reales, las antenas tienen una **ganancia ($G$)** que depende de su **área efectiva (**$A_e​$**)**. La relación fundamental es:
$$$$
En decibelios $(dB)$, la fórmula se expresa como:
$$L_{dB}=20log(f)+20log(d)-10log(A_tA_r)+169,54$$

---
# Absorción Atmosférica

La atmósfera introduce pérdidas adicionales debido a la interacción de las ondas con las moléculas de gas y partículas de agua:

- **Vapor de agua:** Presenta un pico de absorción significativo cerca de los **22 GHz**.
- **Oxígeno:** Presenta un pico de absorción en torno a los **60 GHz**.
- **Precipitaciones:** La lluvia y la niebla provocan la dispersión (_scattering_) de las ondas de radio. Este efecto es crítico para frecuencias superiores a **10 GHz**. En zonas de alta pluviosidad, es necesario acortar la distancia entre repetidores o utilizar bandas de frecuencia más bajas.

---
# Interferencias por Multitrayectorias

En la transmisión LOS, el receptor puede captar no solo la señal directa, sino también múltiples versiones de la misma señal reflejada en obstáculos (suelo, edificios, accidentes topográficos) o en la propia atmósfera (por refracción).

- **Efectos:** Las señales reflejadas llegan con diferentes retardos. Dependiendo de la fase, pueden causar un **realce** o una **cancelación** de la señal total recibida.

- **Contextos críticos:**
    - **Comunicaciones fijas:** Generalmente controlables, excepto cuando la trayectoria pasa sobre superficies de agua en movimiento.
    - **Comunicaciones móviles:** Es un problema de suma importancia debido a la abundancia de obstáculos y la variabilidad del entorno.

---
# Fenómenos de Refracción

La refracción ocurre porque la velocidad de las ondas electromagnéticas cambia según la densidad del medio.

1. **Variación de densidad:** El índice de refracción disminuye con la altura en condiciones normales.
2. **Comportamiento:** Como la señal viaja más lento cerca de la Tierra que en alturas mayores, la onda se desvía gradualmente hacia la superficie terrestre.
3. **Anomalías:** Condiciones meteorológicas inusuales pueden alterar este perfil de velocidad, provocando que la señal se desvíe de tal forma que no llegue a la antena receptora, incluso si existe una línea de visión geométrica clara.

---

|Fenómeno|Causa Principal|Efecto en la Señal|
|---|---|---|
|**Pérdida en Espacio Libre**|Dispersión geométrica|Atenuación logarítmica con la distancia.|
|**Absorción Atmosférica**|Resonancia de moléculas (H2​O,O2​)|Atenuación en bandas específicas (22 GHz, 60 GHz).|
|**Multitrayectorias**|Reflexión en obstáculos|Desvanecimiento o distorsión de la señal.|
|**Refracción**|Cambios de densidad del aire|Curvatura de la trayectoria; puede causar pérdida de enlace.|
