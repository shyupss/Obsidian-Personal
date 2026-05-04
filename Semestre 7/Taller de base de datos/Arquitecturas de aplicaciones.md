En el entorno informático actual, la mayoría de los usuarios no se encuentran físicamente junto al sistema de bases de datos, sino que interactúan con él a través de redes. Esta dinámica establece una distinción fundamental entre las **máquinas cliente**, donde reside el usuario, y las **máquinas servidor**, donde se ejecuta el sistema gestor de bases de datos (SGBD).

Las aplicaciones de bases de datos se categorizan principalmente en dos modelos estructurales:
### Arquitectura de Dos Capas

En este modelo, la aplicación se divide directamente entre el cliente y el servidor:

- **Componente Cliente:** Reside en la máquina del usuario. Este componente invoca la funcionalidad del sistema de bases de datos en el servidor.
- **Interacción:** Se realiza mediante instrucciones de un lenguaje de consultas. Para facilitar esta comunicación, se emplean estándares de interfaces de programas de aplicación (API) como:
    - **ODBC (Open Data Base Connectivity):** Estándar de Microsoft para el lenguaje C.
    - **JDBC (Java Data Base Connectivity):** Estándar para el lenguaje Java.
### Arquitectura de Tres Capas

Este modelo añade un nivel intermedio para gestionar aplicaciones más complejas y de gran escala:

- **Cliente (Frontal):** La máquina cliente actúa simplemente como una interfaz (generalmente mediante formularios) y no realiza llamadas directas a la base de datos.
- **Servidor de Aplicaciones:** Es el intermediario que recibe las peticiones del cliente, procesa la **lógica de negocio** (acciones y condiciones del programa) y se comunica con el SGBD para acceder a los datos.
- **Sistema de Bases de Datos:** El nivel final donde se almacenan y gestionan los datos.

| Característica                 | Arquitectura de Dos Capas    | Arquitectura de Tres Capas                   |
| ------------------------------ | ---------------------------- | -------------------------------------------- |
| **Ubicación de la Aplicación** | En la máquina cliente.       | En el servidor de aplicaciones.              |
| **Acceso a la BD**             | Directo desde el cliente.    | A través del servidor de aplicaciones.       |
| **Lógica de Negocio**          | Distribuida en los clientes. | Centralizada en el servidor de aplicaciones. |
| **Uso Ideal**                  | Aplicaciones más simples.    | Grandes aplicaciones y entornos Web.         |
