Es un servicio gestionado que permite **crear instancias** de bases de datos utilizando SQL.

**AWS gestiona el hardware subyacente,** el parcheo del sistema operativo y de la base de datos, además de las copias de seguridad.

- **Motores compatibles:** PostgreSQL, MySQL, MariaDB, Oracle, Microsoft SQL Server y Aurora.
- **Límite de instancias:** Hasta 40 instancias por cuenta.
- **Almacenamiento:** Según el motor, puede escalar desde 20 GiB hasta 64 TiB, con un IOPS de hasta 80,000.
## Alta Disponibilidad (Multi-AZ)

Despliega una instancia **Primaria** en una Zona de Disponibilidad (AZ) y una **Standby** en otra AZ diferente dentro de la misma región.

- **Replicación Sincrónica:** Los datos se escriben en ambas instancias simultáneamente.
- **Failover Automático:** En caso de fallo de la AZ o mantenimiento, el endpoint (CNAME) se redirige a la instancia Standby (tiempo estimado: 60-120 segundos).
## Read Replicas (Réplicas de Lectura)

Utilizan replicación **asincrónica** para descargar la carga de lectura de la instancia primaria.

- Permite hasta 5 réplicas por instancia.
- Pueden ser **Cross-Region** (en diferentes regiones geográficas).
- Se pueden promover a instancia Primaria para mejorar el RTO.