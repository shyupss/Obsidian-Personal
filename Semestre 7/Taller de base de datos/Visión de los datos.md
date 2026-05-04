La **abstracción** de datos permite separar la representación de los datos en tres niveles (físico, lógico y de vista), ocultando la complejidad del almacenamiento y permitiendo independencia entre niveles. Esto facilita el desarrollo, mantenimiento y evolución de sistemas de bases de datos.

Entonces, la **abstracción de datos** consiste en:
> Ocultar los detalles internos de almacenamiento y representar los datos a ***distintos niveles*** según el usuario.

---
---
# Los 3 niveles de abstracción
## Nivel físico

Es el nivel más bajo.

Describe **cómo se almacenan realmente los datos en el hardware**:
- Archivos
- Bloques en disco
- Índices
- Estructuras como B+trees

Aquí estamos hablando en términos de **implementación**.

---
## Nivel lógico

Acá, se definen qué datos existen y cómo se relacionan, pero sin decir cómo se almacenan.
Este nivel es el corazón conceptual de la base de datos.

*Cuando se diseña un esquema o escribes tablas en SQL se trabaja en este nivel, aunque no se note.*

Aquí aparecen ***conceptos*** como:
- Tablas (relaciones)
- Atributos
- Relaciones entre entidades
- Restricciones
- etc.

---
## Nivel de vistas

La **capa de vistas** es la forma en que el sistema muestra los datos a cada usuario, pero sin enseñarle toda la base de datos.

*Distintos usuarios no necesitan ver lo mismo.*

Por ende, un usuario ve solo una **parte específica o una forma simplificada** de los datos. Esa “vista” puede:
- **ocultar información innecesaria**
- **mostrar solo ciertos atributos**
- **incluso combinar datos de varias tablas**

---
---
# Ejemplares y esquemas

En una base de datos cambia en el tiempo conforme la información se inserta y borra.
### Ejemplar
> **El contenido real de la base de datos en un momento específico**
### Esquema
> La estructura o diseño de la base de datos