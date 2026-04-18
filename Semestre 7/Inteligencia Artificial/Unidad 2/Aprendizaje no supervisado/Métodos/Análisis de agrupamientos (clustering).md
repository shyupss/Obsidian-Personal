***Clustering*** es un tipo de problema cuyo objetivo es ***descubrir grupos en los datos observados***, tales que los ***datos dentro de un mismo grupo son mas parecidos*** que aquellos en los ***otros grupos.***

Para esto, se requiere:
- Una función de ***similaridad (distancia)*** entre datos.
- Una función de ***pérdida*** para evaluar el agrupamiento efectuado.
- Un <u>algoritmo</u> para ***optimizar*** la función de pérdida.

---
# Distancia entre datos

Los resultados del agrupamiento depende de la elección de la **distancia** o medida de la **desimilaridad**.

Esto dependerá normalmente del contexto en el cual se encuentren los datos de estudio.

También depende de la naturaleza de las características observadas: Cuantitativas, ordinales, categóricas.

---
# Desimilaridad en base a características

Habitualmente los datos $x_i$ contienen valores de ciertas **características*** $x_{ij},j=1,...,p$.

Una elección común de desimilaridad es la **distancia euclidiana**:
$$D(x_i, x_{i'})=\|{x_i-x_{i'}}\|=\sqrt{\sum_{j=1}^p(x_{ij}-x_{i'j})^2}$$
Los agrupamientos definidos a partir de la distancia euclidiana son ***invariantes a traslaciones y rotaciones*** del espacio de características. *No así al escalamiento de los datos.*

Una manera de estandarizar los datos es realizar una traslación y escalamiento de manera que todos tengan media 0 y varianza 1.

---

Clustering, consiste en ***encontrar una partición de los datos*** que **optimice** una función de pérdida basada en una ***medida de similitud***.

Sin embargo, este problema **no tiene una solución analítica directa**, por lo que se requiere el uso de **algoritmos iterativos de optimización**.

Para resolver clustering existen distintos enfoques, pero todo dependerá de como se modele la similitud entre los datos.

---
# K-means

K-means es un algoritmo de **agrupamiento (clustering)**, y su objetivo es descubrir grupos naturales en los datos, donde los elementos dentro del mismo grupo se parecen entre sí y se diferencian de los de otros grupos.
## ¿Que resolvemos?

Imagina que tienes cientos de puntos en un plano y quieres separarlos en K grupos. No se sabe de antemano a qué grupo pertenece cada punto (no hay etiquetas, por eso es _aprendizaje no supervisado_). K-means lo hace automáticamente.
## La idea central

Cada grupo se representa con un **prototipo** $\mu_k$ (su "centro" o media). Cada punto se asigna al prototipo más cercano. Entonces, el algoritmo busca los prototipos y asignaciones que minimicen esta función de pérdida:
$$J=\sum_{i=1}^n\sum_{k=1}^Kr_{ik}\|x_i-\mu_k\|^2$$
donde
- $r_{ik}=1$ si el punto $i$ pertenece al grupo $k$, y $0$ si no.
- $\|x_i-\mu_k\|^2$ es el cuadrado de la distancia desde un dato hasta su prototipo.

Esta función también se conoce como la ***dispersión dentro de los grupos***.
## El algoritmo: pasos E y M

El algoritmo alterna entre dos pasos iterativamente hasta converger.
### Paso 0: Inicialización

Antes de que el algoritmo arranque, necesitas decidir **cuántos grupos quieres** (el valor de $K$). Luego se colocan $K$ prototipos $\mu_1, \mu_2, \mu_3, ..., \mu_k$ en posiciones iniciales. La forma más común es **escoger K puntos al azar** del conjunto de datos como prototipos iniciales.

***¿Por qué importa esto?*** Porque K-means es sensible al punto de partida. Si los prototipos iniciales están mal ubicados, el algoritmo puede converger a una solución mala (mínimo local). Por eso en la práctica se corre varias veces y se elige la mejor.

### Paso E: Asignación (Expectation)

Con los prototipos fijos en su posición actual, **cada punto $x_i$ se asigna al prototipo más cercano**. Matemáticamente:
- Para cada punto $i$ calculamos la distancia euclidiana a ***todos*** los $K$ prototipos.
- Se le asigna el grupo $k$ cuyo prototipo esté más cerca.
- Esto se traduce en colocar $r_{ik}=1$ para ese k (para ese grupo), y en $r_{ik}=0$ para los demás.

Lo que ocurre geométricamente es que el espacio se divide en K **regiones de Voronoi**: zonas donde todos los puntos están más cerca del mismo prototipo. Cada punto cae en exactamente una región.
### Paso M: Actualización (Maximization)

Con las asignaciones de grupo fijas, ahora se recalculas los prototipos. Para cada grupo $k$:
- Se reúnen todos los puntos que fueron asignados a ese grupo (donde $r_{ik}=1$).
- Se calcula la media aritmética de esos puntos en cada dimensión.
- Ese valor medio se convierte en el nuevo prototipo $\mu_k$

Para esto, la formula de $\mu_k$ es:
$$\mu_k=\frac{\sum_ir_{ik}x_i}{\sum_ir_{ik}}$$
El denominador es simplemente el ***número de puntos en el grupo k***. Esto **minimiza J** respecto a los prototipos (con asignaciones fijas), porque la media es el punto que minimiza la suma de distancias al cuadrado.
### Paso de convergencia. ¿Terminamos?

Después de cada par E+M se verifica si algo cambió. Si ningún punto cambió de grupo respecto a la iteración anterior, el algoritmo **convergió** y se detiene. Si algo cambió, se vuelve al Paso E.

La convergencia está **garantizada** porque hay un número finito de posibles asignaciones y J nunca aumenta entre iteraciones. Pero ojo: el algoritmo puede quedar atrapado en un **mínimo local**, no necesariamente el global.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="kmeans_flowchart_simple.svg" width="500">
	<br>
	<em>Algoritmo K-means.</em>
</div>

## ¿Cómo escogemos K?

