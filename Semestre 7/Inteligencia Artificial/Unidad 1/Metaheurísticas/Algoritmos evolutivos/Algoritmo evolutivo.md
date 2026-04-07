### ¿Cómo funciona un algoritmo evolutivo?

Un **algoritmo evolutivo** es una metaheurística poblacional que mantiene un conjunto de soluciones candidatas y las mejora iterativamente mediante operadores inspirados en la evolución biológica, como selección, cruzamiento y mutación.

### Algoritmo genético

Un algoritmo genético es una implementación particular de un algoritmo evolutivo.  
  
Mientras que los algoritmos evolutivos definen un marco general basado en población, selección y variación, los algoritmos genéticos especifican cómo se representan las soluciones y cómo se aplican los operadores evolutivos.  
  
En particular, los algoritmos genéticos clásicos utilizan:  
- Representación binaria de las soluciones  
- Selección basada en fitness  
- Cruzamiento (crossover)  
- Mutación  

**Sea de ejemplo la función multimodal:
$$f(x)=21.5+x_1\sin(4\pi x_1)+x_2\sin(20\pi x_2)$$
y:
$$Dom(f) = \{ (x_1, x_2): x_1\in[3.0, 12.1] \land x_2\in[4.1, 5.8]\}$$
Se describirán los siguientes pasos de un algoritmo genético.**
### Paso 1: Encoding

Antes de escribir una sola línea de código del AE, hay que tomar una decisión fundamental: **¿Cómo represento una solución posible como una estructura de datos?** Esta decisión determina qué operadores de cruzamiento y mutación son válidos, qué tan precisa es la búsqueda, y qué tan fácil es implementar el algoritmo.

La codificación clásica de los Algoritmos Genéticos usa strings binarios: `000...0` representa el valor mínimo del rango y `111...1` el máximo. Los AE's más generales admiten reales, permutaciones, árboles, o cualquier estructura de datos que tenga sentido para el problema.

La idea es mapear cada variable real a un string de bits. Con n bits puedes representar $2^n$ valores distintos en el rango.
### Paso 2: Evaluación

Cada individuo se decodifica y se evalúa con la función objetivo. El resultado es su **fitness**: un número que indica qué tan buena es esa solución. Todo el algoritmo gira en torno a este valor.

### Paso 3: Criterio de término.

El criterio de término es la condición que el algoritmo evalúa en cada generación para decidir si seguir iterando o detenerse y entregar la solución final.

Las condiciones de término más comunes suelen ser:

- **Número máximo de generaciones:** Se define un tope de iteraciones de antemano, por ejemplo 200 generaciones. Es el criterio más simple y garantiza que el algoritmo siempre termina, pero no asegura que la solución encontrada sea buena.

- **Número máximo de evaluaciones de fitness:** Similar al anterior, pero en vez de contar generaciones se cuenta cuántas veces se evaluó la función f(x). Es útil cuando la evaluación es costosa computacionalmente.

- **Calidad de la solución:** Si el mejor individuo alcanza un valor de fitness considerado suficientemente bueno (por ejemplo, un error menor a 0.001), el algoritmo se detiene. Requiere saber de antemano qué tan buena debe ser la solución.

- **Sin mejora por N generaciones (estancamiento):** Si el mejor individuo no ha mejorado después de cierta cantidad de generaciones, se asume que el algoritmo convergió y se detiene. Es útil para detectar convergencia prematura.
### Paso 4: Selección

La selección responde a: **¿Quién tiene derecho a reproducirse?** La idea central es que los mejores deben reproducirse más, pero no de forma tan extrema que todos los demás desaparezcan (eso destruiría la diversidad). Hay dos métodos principales para la selección.
#### Roulotte Wheel

Imaginemos una ruleta de casino donde cada individuo ocupa un sector proporcional a su fitness. Se "gira" la ruleta (se genera un número aleatorio entre 0 y la suma total de fitness) y el sector donde cae determina el individuo seleccionado.

La mecánica exacta es: se suman todos los fitness de la población para obtener un total. Luego para cada selección se genera un número aleatorio entre 0 y ese total. Se recorren los individuos sumando sus fitness de forma acumulativa, y el primero cuya suma acumulada supera al número aleatorio es el elegido.

Un individuo con fitness 38 en una población donde la suma total es 100 tendrá un 38% de probabilidad de ser elegido. Uno con fitness 2 tendrá solo un 2%. Esto es intuitivo pero tiene problemas importantes: si hay un individuo muy superior al resto, monopoliza casi toda la ruleta y la población converge hacia él rápidamente. Y si un individuo tiene fitness 0 o negativo, directamente nunca puede ser seleccionado.
#### Tournament Selection (k-torneo)

En lugar de calcular probabilidades globales, se elige un subgrupo de K individuos completamente al azar de la población, se comparan sus fitness entre sí, y el que tenga el mayor fitness dentro de ese grupo gana el torneo y pasa a reproducirse.

Lo brillante de este método es que el sesgo no depende de los valores absolutos del fitness sino de las diferencias relativas. Si K=3, los tres individuos elegidos para el torneo compiten entre sí — el mejor de los tres gana, sin importar cuánto mejor sea que el resto de la población. Esto evita el problema de dominancia de la ruleta.

El parámetro K controla directamente la presión selectiva. Con K=2 en una población de 10, hay bastante azar — el individuo seleccionado es el mejor de solo dos, así que individuos mediocres pueden ganar torneos frecuentemente. Con K=7 o K=8, casi siempre gana el mejor de la población porque es muy probable que esté en ese grupo grande.

### Paso 5: Cruzamiento

Con los padres seleccionados, se genera descendencia. El "cruzamiento de un punto" es el más simple: se elige un punto de corte al azar, y los dos hijos son las combinaciones cruzadas de los dos padres.

La probabilidad de que el cruce ocurra (típicamente entre 0.2 a 0.8) se decide antes de operar. Si el número aleatorio supera esa probabilidad, simplemente los hijos son copias exactas de los padres — no hay cruce. Esto preserva soluciones buenas tal como están.

Existen otros tipos de cruzamiento aparte de el de punto, pero dependerá de la codificación y el problema a resolver.
### Paso 6: Mutación

La mutación opera **después** del cruzamiento, sobre los hijos ya generados. Para codificación binaria, se recorre cada bit del cromosoma individualmente y se elige una **probabilidad de mutación** (pm). Si se cumple, el bit se invierte: 0 → 1 ó 1 → 0.

Existen otras formas de realizar la mutación, pero al igual que el cruzamiento dependerá de la codificación y el problema a resolver.
### Paso 7: Reinserción

Una vez que los individuos han pasado por cruzamiento y mutación, se genera una **población secundaria** (los "hijos"). El paso de reinserción decide cómo esta nueva generación reemplaza a la anterior. Existen dos estrategias principales:

**Generacional:** Los hijos simplemente reemplazan a todos los padres. La población se renueva completamente en cada ciclo. Esto favorece la **exploración**, porque constantemente se están introduciendo individuos nuevos al espacio de búsqueda.

**Steady State:** Los hijos deben _competir_ con sus padres para quedarse en la población. Solo sobreviven si son mejores. Esto aumenta progresivamente la **explotación**, es decir, el algoritmo se va concentrando cada vez más en las mejores soluciones encontradas. El riesgo aquí es quedar atascado en un óptimo local.
### Paso 8: Volver al paso 2.

#### **Exploración vs Explotación**
Es el concepto transversal más importante. Básicamente toda decisión de diseño del algoritmo (tamaño del torneo, probabilidad de mutación, estrategia de reinserción) afecta este balance. Explorar = buscar amplio, explotar = refinar lo bueno.

***Una estrategia útil es explorar al principio y explotar al final.***
#### Lidiando con el azar
La aleatoriedad de los AE dificulta el debug y la evaluación. 
Tips prácticos: 
- **Fijar o registrar la semilla aleatoria** cuando aparece un error, para poder reproducirlo exactamente.
- **No usar siempre la misma semilla**, porque eso solo muestra un caso particular y no el comportamiento general del algoritmo. 
- **Usar el gráfico de convergencia** como herramienta principal de evaluación del comportamiento general.
#### **Gráficas de convergencia**
Son la herramienta de diagnóstico principal. Muestran el fitness del mejor individuo y el promedio a lo largo de las generaciones.
##### Exceso de explotación 
Es el problema más documentado en la literatura de algoritmos evolutivos. Ocurre cuando la presión selectiva es demasiado alta: los mejores individuos dominan la reproducción tan rápido que la diversidad genética de la población colapsa en pocas generaciones. Una vez que todos los individuos son casi idénticos, el cruzamiento no genera soluciones nuevas (cruzar copias de lo mismo produce lo mismo), y la mutación —con probabilidad baja— no alcanza para escapar.

**Señales en el gráfico:** best y average convergen rápido y se aplanan completamente. La brecha entre ambas casi desaparece, lo que indica homogeneidad total en la población.

##### Exceso de exploración
El caso opuesto: la aleatoriedad destruye el progreso acumulado más rápido de lo que la selección puede aprovecharlo. Esto ocurre con probabilidades de mutación muy altas, poblaciones que se renuevan completamente en cada generación sin ningún mecanismo de elitismo, o tamaños de torneo demasiado pequeños (K=2 en poblaciones grandes).

Deb (2001) lo describe como el caso donde el algoritmo se comporta prácticamente como una búsqueda aleatoria: puede encontrar buenas soluciones de vez en cuando, pero no las retiene ni las refina sistemáticamente.

**Señales en el gráfico:** ambas curvas oscilan de forma ruidosa sin una tendencia clara de descenso sostenido. El best mejora un poco pero no de forma asintótica.

##### Búsqueda balanceada
Eiben & Smith (2003) en su libro _Introduction to Evolutionary Computing_ describen este patrón como el equilibrio entre exploración (mantener diversidad) y explotación (presionar hacia las mejores zonas). Las características clave son que el best mejora continuamente de forma asintótica (mejoras grandes al inicio, pequeñas al final), y el average mantiene distancia con el best, indicando que la población sigue siendo diversa.

Una estrategia práctica respaldada por la literatura es el enfriamiento de la presión selectiva: comenzar con K pequeño en el torneo (más exploración) e irlo aumentando a medida que avanzan las generaciones (más explotación).