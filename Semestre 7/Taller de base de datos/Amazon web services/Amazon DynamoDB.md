Base de datos NoSQL de clave-valor, completamente gestionada y sin servidor (_serverless_), diseñada para latencias de un solo dígito de milisegundo a cualquier escala.

- **Estructura:** Las tablas contienen **Items** (filas) compuestos por atributos. Los Items tienen un tamaño máximo de **400 KB**.
- **Claves Primarias:**
    - **Simple:** Basada solo en una Clave de Partición (PK).
    - **Compuesta:** Basada en una Clave de Partición (PK) y una Clave de Sorteo (SK).
#### Capacidad y Consistencia

- **Modos de Capacidad:**
    - _Provisionada:_ Para tráfico predecible (se definen WCU y RCU).
    - _On-Demand:_ Para tráfico variable o desconocido; escala instantáneamente.
- **Modelos de Consistencia de Lectura:**
    - _Eventual (por defecto):_ Costo 50% menor, puede no reflejar el cambio más reciente.
    - _Fuertemente Consistente:_ Devuelve el dato más actualizado.
    - _Transaccional:_ Soporte ACID para operaciones complejas (doble costo).

Índices en DynamoDB

| Característica         | Local Secondary Index (LSI)             | Global Secondary Index (GSI)             |
| ---------------------- | --------------------------------------- | ---------------------------------------- |
| **Clave de Partición** | Debe ser la misma que la tabla base.    | Puede ser diferente.                     |
| **Clave de Sorteo**    | Diferente a la de la tabla base.        | Puede ser diferente.                     |
| **Restricciones**      | Máximo 5 por tabla; se crean al inicio. | Hasta 20; se crean en cualquier momento. |
| **Consistencia**       | Soporta Fuertemente Consistente.        | Solo Consistencia Eventual.              |

_Nota: AWS recomienda usar GSIs por defecto a menos que se requiera consistencia fuerte._