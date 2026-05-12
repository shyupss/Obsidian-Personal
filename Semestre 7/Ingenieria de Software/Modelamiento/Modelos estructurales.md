Los modelos estructurales poseen una naturaleza **estática**.

> Su propósito principal es mostrar la configuración y el diseño del sistema, siendo herramientas esenciales durante la discusión y definición de la arquitectura de software.

---
# Diagramas de Clase

Los diagramas de clase representan los pilares del diseño orientado a objetos. En UML, estos pueden variar en su nivel de detalle según la fase del proyecto:
##### **Etapa Inicial:**
Se centra en el dominio del problema, identificando objetos esenciales y representándolos como clases conceptuales.
##### **Detalles de Clase:**
Una clase se representa mediante un rectángulo dividido en tres secciones:
- **Nombre de la clase:** Identificador único.
- **Atributos:** Propiedades o datos (ej. `nombre: String`, `teléfono: Int`).
- **Operaciones/Métodos:** Funciones o comportamientos (ej. `vender()`, `prescribir()`).
##### **Relaciones y Notación:**
- **Asociación:** Conexión entre clases, a menudo con multiplicidades (ej. `1` a `*`) y nombres de roles (ej. `dueño`, `comprado`).
- **Generalización (Herencia):** Representada por una flecha con punta de triángulo vacío que apunta hacia la superclase. Permite definir jerarquías donde las subclases heredan y agregan detalles específicos.
- **Restricciones:** Reglas adicionales (ej. `{xor}`).
- **Multiplicidades:** Definen cuántas instancias de una clase se relacionan con otra (ej. `0..1`, `3..6`, `1..*`).

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagramadeclase.png" width="300">
	<br>
	<em>Diagrama de clases</em>
</div>

---
# Diagramas de Componentes

Este diagrama ilustra la **relación estructural de los componentes** de un sistema de software.

> Es especialmente útil en sistemas complejos con múltiples piezas de software interactuando.
##### **Componentes:**
Piezas autónomas de un sistema.
##### **Interfaces:**
Los componentes se comunican a través de ellas. UML distingue entre _interfaces requeridas_ (lo que el componente necesita) e _interfaces provistas_ (lo que el componente ofrece).
##### **Conectores:**
Elementos que vinculan las interfaces para permitir la comunicación.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagramadecomponentes.png" width="280">
	<br>
	<em>Diagrama de componentes</em>
</div>

---
# Diagramas de Paquete

El diagrama de paquetes ofrece una visión de **alto nivel**, ***agrupando elementos del sistema en módulos lógicos.***

- **Propósito:** Visualizar la organización arquitectónica y la modularidad.
- **Dependencias:** Se representan mediante flechas discontinuas con la etiqueta `<<uses>>` o `dependency`, indicando cómo un paquete requiere de otro para su funcionamiento.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagramadepaquetes.png" width="350">
	<br>
	<em>Diagrama de paquetes</em>
</div>

