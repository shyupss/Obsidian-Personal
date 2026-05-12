
En los sistemas de transmisión de datos, los medios no guiados utilizan una antena para radiar energía electromagnética a través de la atmósfera, el espacio o el agua. A diferencia de los medios guiados, donde el material físico impone las limitaciones, en la transmisión inalámbrica la calidad está determinada principalmente por el ancho de banda de la señal y la direccionalidad de la antena.

| Rango de Frecuencia    | Denominación   | Características de Propagación                |
| ---------------------- | -------------- | --------------------------------------------- |
| 1 GHz a 40 GHz         | Microondas     | Haces altamente direccionales; punto a punto. |
| 30 MHz a 1 GHz         | Ondas de Radio | Aplicaciones omnidireccionales.               |
| 3 x 10¹¹ a 2 x 10¹⁴ Hz | Infrarrojos    | Conexiones locales; no atraviesan paredes     |

---

> Toda señal radiada por una antena puede seguir tres trayectorias fundamentales para alcanzar su destino: la **superficial**, la **aérea** o la **trayectoria visual (LOS)**. La elección del modo de propagación predominante depende intrínsecamente de la frecuencia de la señal y de las condiciones atmosféricas.

# Propagación Superficial de Ondas (Ground Wave)

La propagación superficial (GW) se caracteriza por seguir el contorno de la superficie terrestre. Este modo es **predominante** para frecuencias de hasta **2 MHz**.

- **Mecanismo físico:** La onda electromagnética induce una corriente en la superficie terrestre. Esta interacción frena el frente de onda cerca del suelo, provocando que este se curve hacia abajo y se adapte a la curvatura del planeta.
- **Difracción:** Este fenómeno también contribuye a que la onda pueda sortear obstáculos y seguir la superficie.
- **Alcance:** Permite alcanzar grandes distancias, superando la línea del horizonte visual.
- **Aplicación típica:** El ejemplo más representativo es la radio comercial AM.}

---
# Propagación Aérea de Ondas (Sky Wave)

Utilizada frecuentemente por radioaficionados y emisiones internacionales (como la BBC), la propagación aérea (SW) permite comunicaciones a distancias de miles de kilómetros mediante un efecto de "salto".

- **Mecanismo físico:** La señal se emite hacia la atmósfera superior y se refleja (o refracta) en la **ionosfera**, una capa de aire ionizado situada a gran altura.
- **Refracción:** Aunque se describe como una reflexión, técnicamente la ionosfera refracta la señal de vuelta hacia la Tierra.
- **Saltos:** La onda puede desplazarse dando múltiples saltos entre la ionosfera y la superficie terrestre, lo que permite la recepción en puntos muy alejados del transmisor.

---
# Propagación en la Trayectoria Visual (Line of Sight - LOS)

Para frecuencias superiores a **30 MHz**, los modos superficial y aéreo pierden eficacia. En este rango, las comunicaciones dependen de la trayectoria visual directa entre antenas.
### El Fenómeno de la Refracción

La refracción es fundamental en LOS. Ocurre porque la velocidad de **las ondas electromagnéticas depende de la densidad del medio.**

- **Velocidad de la luz (c)**: En el vacío es de aproximadamente $3×108[m/s]$. En otros medios (aire, agua, cristal), la velocidad es menor.
- **Desviación:** Cuando una onda pasa de un medio menos denso a uno más denso, su velocidad cambia y su trayectoria se desvía hacia el medio más denso.
- **Refracción atmosférica:** En condiciones normales, la densidad de la atmósfera disminuye con la altura. Esto hace que las ondas de radio viajen más lentamente cerca de la Tierra que a mayores alturas, provocando que la señal se curve suavemente hacia la superficie terrestre.
### Línea de Visión Óptica vs. Línea de Visión de Radio

Debido a la refracción, las ondas de radio pueden llegar más lejos que la luz visible (horizonte óptico).

##### **Línea de visión óptica (d):**
La distancia al horizonte se define como $d=3,57\sqrt{h}$  donde $d$ es la distancia en kilómetros y $h$ la altura de la antena en metros.
##### **Línea de visión efectiva o de radio:**
Se ajusta mediante un factor $K$ que compensa la refracción. Un valor estándar aceptado es $K=4/3$. La fórmula resulta en: $d=3,57\sqrt{Kh}$
##### **Distancia máxima entre dos antenas $k_1$ y $k_2$ ($d_{max}$​):** 
$$d_{max}=3,57(\sqrt{Kh_1}+\sqrt{Kh_2})$$
Donde h1​ y h2​ son las alturas de las antenas transmisora y receptora.