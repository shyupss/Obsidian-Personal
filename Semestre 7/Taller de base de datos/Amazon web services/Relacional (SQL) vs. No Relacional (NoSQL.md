Las bases de datos relacionales y no relacionales difieren en sus garantías fundamentales y capacidades de escalado.
# Relacionales y el modelo ACID

Cumplen con los principios **ACID** para garantizar la integridad:

- **Atomicidad:** La transacción ocurre por completo o no ocurre nada.
- **Consistencia:** Los datos deben seguir reglas de validación y esquemas.
- **Aislamiento:** Las transacciones concurrentes no se afectan entre sí.
- **Durabilidad:** Los datos se guardan permanentemente tras finalizar la transacción, incluso ante fallos del sistema.
# No Relacionales y el modelo BASE

Cumplen con el modelo **BASE**, diseñado para escalabilidad masiva:

- **Básicamente Disponible (Basically Available):** Operaciones de lectura/escritura siempre disponibles.
- **Estado Suave (Soft-state):** No hay garantías de consistencia inmediata; el estado puede cambiar.
- **Consistencia Eventual (Eventually Consistent):** Los datos se vuelven consistentes con el tiempo.

---

| Característica     | Relacional (SQL)               | No Relacional (NoSQL)           |
| ------------------ | ------------------------------ | ------------------------------- |
| **Almacenamiento** | Tablas interconectadas (FK)    | Colecciones o pares clave-valor |
| **Esquema**        | Fijo (Estructurado)            | Flexible (Semi/No estructurado) |
| **Escalabilidad**  | Vertical (Aumento de potencia) | Horizontal (Aumento de nodos)   |
| **Interfaz**       | SQL                            | APIs basadas en objetos         |
| **Uso óptimo**     | OLTP y OLAP                    | OLTP (web/mobile apps)          |

