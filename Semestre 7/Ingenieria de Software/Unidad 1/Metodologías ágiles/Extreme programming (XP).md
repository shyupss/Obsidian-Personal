XP se basa en los principios de simplicidad, comunicación, retroalimentación continua y valentía. Utilizamos 12 prácticas para llevas a cabo XP.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="XP.png" width="200">
	<br>
	<em>XP approach</em>
</div>

## 1. Planning game

El usuario tendrá que escribir sus necesidades, definiendo las actividades que realizará en el sistema. Se crea un documento llamado historias de usuario. Entre 20 y 80 historias se consideran suficientes para formar el llamado plan de liberación, el cual define de forma específica los tiempos de entrega de la aplicación para recibir retroalimentación por parte del usuario. Por regla general, cada historia de usuario toma de una a tres semanas de desarrollo.  

Deben ser una constante las reuniones periódicas durante esta fase de planificación. Estas pueden ser a diario, con todo el equipo de desarrollo para identificar problemas, proponer soluciones y señalar puntos a los que se le debe dar más importancia por dificultad o por su punto crítico.

***Se definen historias de usuario para calcular los tiempos de entrega de la aplicación (plan de liberación). Se hacen reuniones periódicas constantemente donde se discuten y solucionan problemas además de señalar puntos críticos.***

## 2. Small releases

Entregas pequeñas: colocar un sistema sencillo en producción rápidamente que se actualiza de forma rápida y constante permitiendo que el verdadero valor de negocio del producto sea evaluado en un ambiente real. Estas entregas no pueden pasar las 2 o 3 semanas como máximo.

## 3. Metaphor

Acá, los programadores desarrollan una metáfora al inicio del proyecto que define una historia de cómo funciona el sistema completo. La metáfora expresa la visión evolutiva del proyecto que define el alcance y propósito del sistema.

Además, se usan tarjetas CRC (Clase, responsabilidad y colaboración). Cada una representa una clase, define sus responsabilidades y las colaboraciones entre otras clases.

## 4. Simple design

El mayor valor de negocio es entregado por el sistema más sencillo que cumpla los requerimientos. Se enfoca en proporcionar un sistema que cubra las necesidades inmediatas del cliente, ni más ni menos. Permite eliminar redundancias y rejuvenecer diseños obsoletos de forma sencilla

## 5. Testing

Se tiene que establecer un período de pruebas de aceptación del programa (llamado también período de caja negra) donde se definirán las entradas al sistema y los resultados esperados de estas entradas. Es muy recomendable **automatizar** estas pruebas para poder hacer varias simulaciones del sistema en funcionamiento.

## 6. Refactoring

Permite a los equipos de programadores XP mejorar el diseño del sistema a través de todo el proceso de desarrollo. Los programadores evalúan continuamente el diseño y recodifican lo necesario. La finalidad es mantener un sistema enfocado a proveer el valor de negocio mediante la minimización del código duplicado y/o ineficiente.

## 7. Pair programming

Programación en parejas: uno de los principios más radicales y en el que la mayoría de gerentes de desarrollo pone sus dudas. Requiere que todos los programadores XP escriban su código en parejas, compartiendo una sola máquina.

## 8. Collective code ownership

Un código con propiedad compartida. Nadie es el propietario de nada, todos son el propietario de todo. Este método difiere en mucho a los métodos tradicionales en los que un simple programador posee un conjunto de código. Los defensores de XP argumentan que mientras haya más gente trabajando en una pieza, menos errores aparecerán.

## 9. Continuous integration

Permite al equipo hacer un rápido progreso implementando las nuevas características del software. En lugar de crear builds (o versiones) estables de acuerdo a un cronograma establecido, los equipos de programadores XP pueden reunir su código y reconstruir el sistema varias veces al día. Esto reduce los problemas de integración comunes en proyectos largos y estilo cascada.

***Ningún código permanece sin implementar por mas de dos horas -- Kent beck***

***Debería ser capaz de caminar con una notebook cargada con solo un sistema operativo, y al usar el repositorio, obtener todo lo que necesito para compilar y ejecutar el producto. -- Martín Fowler***

## 10. 40 hours work week

La programación extrema sostiene que los programadores cansados escriben código de menor calidad. Minimizar las horas extras y mantener los programadores frescos, generará código de mayor calidad.

## 11. On site client

Se le dará poder para determinar los requerimientos, definir la funcionalidad, señalar las prioridades y responder las preguntas de los programadores. Esta fuerte interacción cara a cara con el programador disminuye el tiempo de comunicación y la cantidad de documentación, junto con los altos costes de su creación y mantenimiento.

## 12. Coding Standard

Define la gestión del código compartido, así como las reglas para escribir y documentar el código y la comunicación entre diferentes piezas de código desarrolladas por diferentes equipos. Los programadores las han de seguir de tal manera que el código en el sistema se vea como si hubiera estado escrito por una sola persona.

---
# ¿Cuándo se debería implementar XP?

**Para gestionar un equipo más pequeño**. Debido a su naturaleza altamente colaborativa, la programación extrema funciona mejor en equipos pequeños de menos de diez personas.

**Si estás constantemente en contacto con tus clientes.** La programación extrema incorpora los requisitos de los clientes a lo largo del proceso de desarrollo y también se basa en ellos para las pruebas y aprobaciones.

**Si trabajas con un equipo flexible que pueda aceptar el cambio *(sin resentimientos)*.** Dada su propia naturaleza, la programación extrema a menudo requerirá que todo el equipo deseche todo su arduo trabajo. Algunas reglas también permiten que algunos miembros del equipo realicen cambios en cualquier momento, lo que supondría un problema si los demás compañeros del equipo se lo toman como algo personal.

**Si dominas los aspectos técnicos de la codificación.** La programación extrema no es para principiantes ya que necesitas poder trabajar e implementar cambios rápidamente.