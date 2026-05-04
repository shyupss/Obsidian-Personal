Hay ***cuatro tipos diferentes de usuarios*** de un sistema de base de datos, diferenciados por la forma en que ellos esperan interactuar con el sistema.

*No todos los que usan una base de datos la usan de la misma forma.*
## Usuarios normales

Son los que usan la base de datos **sin saber realmente que existe**.

Ejemplo:
- alguien usando una app bancaria
- alguien comprando en una tienda online

Ellos no escriben SQL ni entienden la estructura. Solo interactúan con interfaces.

👉 Para ellos, la base de datos está completamente abstraída.
## Programadores de aplicaciones

Son los que escriben programas que interactúan con la base de datos.

Ejemplo:
- backend de una app
- sistema de gestión

Ellos sí usan SQL o APIs, pero:
- trabajan sobre el **esquema lógico**
- no se preocupan del almacenamiento físico

👉 Son los que conectan el sistema con los usuarios finales.
## Usuarios sofisticados

Estos sí interactúan directamente con la base de datos.

Ejemplo:
- analistas de datos
- ingenieros que escriben queries complejas

Usan SQL directamente para:
- consultas
- análisis
- reportes

👉 No construyen aplicaciones, pero sí trabajan directamente con los datos.
## Usuarios especializados

Son usuarios avanzados que trabajan con **aplicaciones complejas o no tradicionales**, donde una base de datos “normal” no es suficiente.

No se limitan a usar tablas simples o hacer consultas, sino que:
- trabajan con **datos complejos**
- desarrollan sistemas más avanzados (no solo CRUD)

👉 Usan la base de datos como parte de un sistema más grande y sofisticado.

*No trabajan con bases de datos “tradicionales”, sino que las extienden o las combinan con otras tecnologías.*
