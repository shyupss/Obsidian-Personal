---

---
## Introducción

La ingeniería está muy asociada a la fabricación de artefactos eficientes, donde la eficiencia puede depender de distintos parámetros:
	1. Capacidad de carga.
	2. Grosor de vigas.
	3. Elección de materiales.
	4. Etc... 

Donde la correcta elección de estos parámetros es materia de la optimización que realizamos.
## Métodos basados en gradiente

Acá la idea es encontrar la dirección de mayor cambio, sea máx. o mín., y avanzar en esa sentido. Entonces desde un punto cualquiera, iteraríamos varias veces hasta obtener una buena solución.
#### Limitaciones de métodos basados en gradiente

Lamentablemente no se garantiza que desde cualquier punto, encontremos el máximo o mínimo global, ya que guían por su vecindad.
## Optimización local y global

**Espacio de búsqueda**: 
	Es el conjunto de puntos $(x, y) \in \mathbb{R}^2$, al cual nos referimos como dominio de la función objetivo.
**Vecindad**: 
	Conjunto de puntos cercanos a un punto $\vec{x} = (x, y, z)$. 
	Una vecindad puede ser distinta para cada punto.
#### Límites para métodos tradicionales

Si la función **no es continua, no es diferenciable, es desconocida o no existe explícitamente**, entonces **no se puede calcular el gradiente**, por lo que **los métodos de optimización basados en gradiente no pueden aplicarse**.

Entonces, se utilizan **heurísticas y metaheurísticas**, que pueden optimizar **sin conocer la forma exacta de la función** y con **menos restricciones sobre el espacio de búsqueda**.
## Multimodalidad

Una función se dice que es multimodal cuando tiene muchos mínimos o máximos locales.
	Esto implica que algoritmos basados en gradiente pueden quedarse atrapados en algún valle.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="rastrigin.png" width="400">
	<br>
	<em>Función Rastrigin</em>
</div>

*Hay funciones de este tipo:* ***Schwefel***, ***Griewank***, ***Ackley***, ***Levy***, etc...

## Heurísticas
*Proviene del griego heuriskein ("hallar", "inventar")*

Son métodos computacionales utilizados en optimización, se basan en una idea “razonable” que la mayor parte de las veces arroja buenos resultados.

Se pueden ver como atajos mentales, o como una regla práctica empírica que utilizamos para tomar decisiones y resolver problemas rápidamente.

## Metaheurísticas

La MH son heurísticas de alto nivel, muchas veces estocásticas, y aplicables a diversos problemas, ya que se desenvuelven bien en espacios de búsqueda grandes y complejos.

Estas exigen pocas condiciones de los espacios de búsqueda y pueden operar con poco conocimiento sobre los problemas, pero no aseguran la convergencia hacia el óptimo global.

Las metaheurísticas constituyen una amplia familia de algoritmos genéricos utilizados para resolver problemas de distinta naturaleza, y muchas de ellas se inspiran de proceso naturales (Bio-inspiradas).

[[Particle Swarm Optimization (PSO)]]