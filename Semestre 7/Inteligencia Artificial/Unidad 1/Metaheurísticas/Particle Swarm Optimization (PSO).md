**PSO** es una metaheurística de optimización **bioinspirada**, esto significa que busca soluciones óptimas o cercanas al óptimo para un problema, pero no se garantiza el óptimo exacto.

Está inspirado en la naturaleza, en este caso se inspira en enjambres de pájaros y bancos de peces, donde muchos individuos simples interactúan y generan **comportamiento colectivo inteligente**.

En breves palabras: "Un conjunto de partículas se mueven intentando llegar a zonas atractivas del espacio de búsqueda".

El desplazamiento de la partícula depende de:
	Su inercia (rapidez, dirección)
	La mejor solución que ha encontrado
	La mejor solución encontrada globalmente
### Historia
PSO fue propuesto en 1995 por **James Kennedy** y **Russell Eberhart**, donde intentaban modelar el comportamiento social. Luego se convirtió en un algoritmo de optimización muy usado.
### Conceptos principales
#### Partículas
El algoritmo trabaja con un conjunto de partículas, donde cada una representa una **solución posible al problema**.
#### Espacio de búsqueda
Es el conjunto de puntos $(x, y) \in \mathbb{R}^2$, al cual nos referimos como dominio de la función objetivo.
#### Función de evaluación (fitness)
La **fitness function** es la función que usa el algoritmo para evaluar qué tan buena es una solución.
	A veces, la función fitness es una transformación de la función objetivo, por ejemplo cuando el algoritmo maximiza fitness, pero el problema es minimizar costos, la función puede ser $fitness=\frac{1}{1+costo}$, así $menor costo \rightarrow mayor fitness$.

#### Movimiento de las partículas
Cada partícula tiene una posición $x_i$ y velocidad $v_i$. La velocidad indica la dirección y rapidez.

Entonces, la partícula se mueve así:
	$nueva$  $posición$ $=$ $posición + velocidad$ 
	$x_i(t) = x_i (t-1)+v_i (t)$
#### Inteligencia del enjambre
Cada partícula usa tres fuentes de información:
	1. **Inercia**
		La partícula tiende a seguir moviéndose como venía, es decir "mantiene parte de su velocidad anterior"
	2. **Mejor posición personal $pBest$**
		La mejor solución que ella misma encontró: $p_i$
	3. **Mejor posición global $gBest$**
		La mejor solución encontrada por cualquier partícula: $p_g$

#### Ecuación de velocidad
La velocidad se actualiza combinando esas tres fuerzas.
**Conceptualmente:**
	$v$ $=$ $inercia+atracción$ $personal+atracción$ $social$

Y esta ecuación tiene dos formas, una incluye una variable $w$ llamada "peso", y la otra tiene dos factores de aprendizaje ($C_1; C_2$).
##### Con factores de aprendizaje
$v_i(t)=v_i(t-1)+p_1C_1(p_i-x_i(t-1))+p_2C_2(p_g-x_i(t-1))$
##### Con peso ($w$) asociado a la inercia
$v_i(t)=v_i(t-1)w+p_1(p_i-x_i(t-1))+p_2(p_g-x_i(t-1))$
#### Algoritmo Particle Swarm Optimization
**Particle Swarm Optimization (PSO)** busca el óptimo de una función usando un **enjambre de partículas** que se mueven por el espacio de búsqueda.

Cada partícula:
	Representa una solución candidata
	Tiene posición y velocidad
	Recuerda su mejor solución encontrada
	
	Conoce la mejor solución del grupo

El enjambre se mueve iterativamente hacia zonas prometedoras.

Algorithm:
```
Random initialization of the whole swarm;
Repeat
	Evaluate f(x_i);
	For all paricles i:
		Update velocities:
			v_i = ...;
		Move to the new position: x_i(t) = ...;
		IF f(x_i) < f(pBest) THEN pBest = x_i;
		IF f(x_i) < f(gBest) THEN gBest = x_i;
		Update(x_i, v_i);
	EndFor
Until stopping criteria
```