Imaginemos que tenemos un problema de optimización: 
$$\max_{x \in \mathcal{X}} f(x)$$
donde:
- $\mathcal{X}$ puede ser enorme, discreto o no estructurado.
- $f(x)$ puede ser:
	- no diferenciable
	- desconocido
	- evaluable solo por simulación

En problemas de optimización complejos, especialmente multimodales, los métodos basados en gradiente o búsqueda local no garantizan encontrar el óptimo global, ya que operan mejorando iterativamente una única solución dentro de su vecindad, lo que los hace susceptibles a quedar atrapados en óptimos locales. En contraste, el modelo evolutivo propone trabajar con una población de soluciones que evoluciona mediante selección y variación, permitiendo explorar múltiples regiones del espacio de búsqueda simultáneamente.

### La inspiración biológica de Darwin
La idea central es simple pero poderosa: en la naturaleza, los organismos compiten por sobrevivir. Los que mejor se adaptan a su entorno tienen más descendencia, y sus características se propagan. Con el tiempo, la especie "mejora" en relación a su entorno.

La clave para la computación es esta equivalencia:
$$evolución = mejora continua = optimización$$
Antes de Darwin, Lamarck ya había propuesto que los organismos cambian según las "circunstancias" del entorno. Pero fue Darwin (con el viaje del HMS Beagle entre 1831–1836) quien formalizó la idea de selección natural: los más aptos sobreviven y se reproducen.

Luego Gregor Mendel descubrió que los rasgos se heredan por genes dominantes y recesivos, lo que explica el mecanismo de transmisión de características. Cuando combinamos evolución darwiniana con genética mendeliana, obtenemos el modelo sobre el que se basan los Algoritmos Evolutivos.

### Paralelo entre computación y naturaleza

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="paralelo_naturaleza_computacion.svg" width="600">
	<br>
	<em>Paralelo entre computación y naturaleza</em>
</div>

### El ciclo del algoritmo evolutivo

El AE propuesto por John Holland en 1975 como Algoritmo Genético sigue un ciclo bien definido. Es el corazón del modelo evolutivo:

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="ciclo_algoritmo_evolutivo.svg" width="600">
	<br>
	<em>Propuesta de base: Algoritmo genético</em>
</div>

### Aplicaciones de los algoritmos evolutivos

**Antena NASA ST5 (2005):** La forma de la antena fue diseñada por un AE, no por ingenieros. El resultado tiene una forma irregular que ningún humano habría propuesto, pero que maximiza la eficiencia de señal. Es el primer objeto diseñado por evolución artificial que llegó al espacio.

**Criaturas virtuales de Karl Sims (1994):** Se evolucionaron criaturas en un mundo simulado. Nadie les dijo cómo moverse — el fitness era simplemente "¿qué tan lejos se desplazó?". Emergieron comportamientos de locomoción sorprendentes, nunca anticipados por los investigadores.

**Diseño de parques eólicos:** Los algoritmos evolutivos optimizan la disposición de turbinas considerando el efecto estela entre generadores (una turbina "roba" viento a las que están detrás), la dirección predominante del viento y la eficiencia total del parque.

**Neuroevolución:** Una de las aplicaciones más actuales — usar AEs para diseñar automáticamente la arquitectura de redes neuronales profundas, en lugar de que lo haga un ingeniero a mano (AutoML evolutivo de Google, 2018).

