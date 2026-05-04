...
## La Naturaleza de las Tablas InnoDB

Una revelación fundamental es que **las tablas InnoDB son índices**. No son estructuras separadas; la tabla misma es un índice B-tree organizado por la clave primaria (_Primary Key_).

## Estructura del Clustered Index

En InnoDB, la clave primaria se denomina **índice agrupado (clustered index)**.

- Los registros de la tabla se almacenan en los **nodos hoja** (leaf nodes) de la estructura del índice.
- Cada registro incluye los datos de las columnas y metadatos internos para el bloqueo de filas y aislamiento de transacciones.
- Debido a esta estructura, las búsquedas por clave primaria son extremadamente rápidas y eficientes.

### Índices Secundarios

Cualquier índice que no sea la clave primaria es un índice secundario. A diferencia del índice agrupado:

- Sus nodos hoja no contienen la fila completa.
- Almacenan los valores de las columnas del índice y el **valor de la clave primaria** correspondiente.