En el ámbito de las bases de datos, una **transacción** se define como una colección de diversas operaciones que constituyen una única unidad lógica de trabajo.

El objetivo del sistema de gestión de transacciones es garantizar que la base de datos mantenga su integridad incluso ante fallos del sistema o accesos simultáneos.
### Propiedades Fundamentales (Atomicidad, Consistencia y Durabilidad)

Para que una transacción sea considerada válida y segura, el sistema debe cumplir con requisitos específicos que aseguren la corrección de los datos:

- **Atomicidad:** Es el requisito de "todo o nada". Una transacción debe ejecutarse en su *totalidad o no ejecutarse en absoluto.* Si ocurre un fallo a mitad de un proceso (como una transferencia bancaria donde se descuenta el dinero de una cuenta pero no se abona en la otra), el sistema debe ser capaz de restaurar los datos al estado previo.
- **Consistencia:** La ejecución de una transacción debe preservar la corrección de la base de datos. Si la base de datos era consistente antes de iniciar la transacción, debe seguir siéndolo al finalizar.
- **Durabilidad:** Una vez que una transacción se completa con éxito, los cambios realizados deben persistir en el sistema, incluso si ocurre un fallo de hardware o una caída del sistema inmediatamente después.
### Responsabilidades en la Gestión

La preservación de estas propiedades recae en dos actores principales:

1. **El Programador:** Es responsable de definir adecuadamente las transacciones para que preserven la consistencia. Por sí mismos, los subprogramas individuales (como solo cargar una cuenta) no son transacciones porque dejan la base de datos en un estado inconsistente temporalmente.
2. **El SGBD:** A través del **componente de gestión de transacciones**, el sistema asegura la atomicidad y la durabilidad. Incluye un sistema de recuperación de fallos que detecta anomalías y restaura la base de datos. Además, cuenta con un **gestor de control de concurrencia** para supervisar la interacción entre transacciones que ocurren simultáneamente, evitando anomalías en los datos.