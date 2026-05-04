Es un servicio relacional de bases de datos propietario de Amazon, compatible con MySQL y PostgreSQL. Es hasta **5 veces más rápido** que MySQL estándar y **3 veces más rápido** que PostgreSQL.

- **Resiliencia:** Mantiene **6 copias** de los datos distribuidas en 3 Zonas de Disponibilidad (AZ).
- **Escalabilidad de lectura:** Permite hasta 15 réplicas de lectura.
- **Aurora Serverless:** Configuración bajo demanda que escala automáticamente y puede "pausarse" cuando no hay carga, eliminando costos de computación.
- **Clonación Rápida:** Crea copias de la base de datos para pruebas/desarrollo sin copiar todos los datos inicialmente (protocolo _copy-on-write_).
- **Backtrack:** Permite "rebobinar" la base de datos a un punto previo en el tiempo (hasta 72 horas) sin necesidad de restaurar un backup (solo MySQL).