El diseño arquitectónico se interesa por entender cómo debe organizarse un sistema y cómo tiene que diseñarse la estructura global de ese sistema.

> Un modelo arquitectónico describe la forma en que se organiza un sistema como un conjunto de componentes en comunicación.

*“Un sistema mal diseñado es como una pizzería donde el cocinero también atiende el teléfono, cobra, maneja la moto y habla con los clientes en redes sociales.”*
#### ¿Por qué importa la arquitectura?

> No se trata solo de que el software funcione, sino de que soporte crecimiento, cambios, errores y evite el caos.

---
# Niveles de abstracción de la arquitecturas de software

### La arquitectura en pequeño
Se interesa por la arquitectura de ***sistemas individuales***. En este nivel, uno **se preocupa por la forma en que el sistema individual se separa en componentes.**

> Ejemplos: MVC, Arquitectura de capas, Arquitectura cliente-servidor, Arquitectura de tubería y filtro, Pizarra, Peer-to-peer, etc.
### La arquitectura en grande
Se interesa por la arquitectura de ***sistemas empresariales complejos que incluyen otros sistemas***, *programas y componentes de programa.*

> Ejemplos: Sistemas distribuidos, Microservicios, Serverless, orientada a servicios.

---
# ¿Qué entendemos por patrones de diseño?

Un patrón de diseño resulta ser una solución a un problema de diseño. Para que una solución sea considerada un patrón debe poseer ciertas características.

- **Haber comprobado su efectividad resolviendo problemas similares** en ocasiones anteriores.
- **Debe ser reutilizable,** lo que significa que es aplicable a diferentes problemas de diseño en distintas circunstancias

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="def.patrondediseño.png" width="500">
	<br>
	<em>Definición de patrón de diseño - Taylor, Medvidovic and Dashofy</em>
</div>

---
# No confundir

#### Patrones de diseño arquitectónico.
Aquellos que expresan un esquema organizativo estructural fundamental para sistemas de software. Origen: “Pattern-Oriented Software Architecture”
#### Patrones de diseño de software.
Abstracciones genéricas que ocurren a través de las aplicaciones que muestran objetos e interacciones abstractas y concretas. Origen: “Design Patterns: Elements of Reusable Object-Oriented Software”
#### Dialectos (idioms)
Patrones de bajo nivel específicos para un lenguaje de programación o entorno concreto.

---
# ¿Qué se busca al modelar una arquitectura?

**Alta cohesión** (única responsabilidad) y **Bajo acoplamiento** (mínima cantidad de dependencias)
### ¿Por qué buscamos eso?

La buena arquitectura es algo que sustenta la evolución y está profundamente entrelazada con la velocidad de incorporar nuevas funcionalidades y corregir problemas.

---
# ¿Qué queremos evitar? - Design Smells

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="design-smells.png" width="700">
	<br>
	<em>Design smells</em>
</div>
