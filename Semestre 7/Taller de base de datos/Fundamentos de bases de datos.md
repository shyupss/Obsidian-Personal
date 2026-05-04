# Sistema gestor de base de datos

Un sistema gestor de bases de datos (***SGBD***) consiste en una colección de datos interrelacionados y un conjunto de programas para acceder a dichos datos.

La colección de datos, normalmente denominada ***base de datos***, contiene información relevante para una empresa. *El objetivo principal de un SGBD es proporcionar una forma de almacenar y recuperar la información de una base de datos de manera que sea tanto práctica como eficiente.*
#### ***Los sistemas están diseñados para manejar:***
- Grandes volúmenes de información
- Datos compartidos por múltiples usuarios
- Necesidad de acceso concurrente
- Riesgo de fallos o accesos no autorizados
#### ***Por eso, un SGBD debe garantizar:***
- Persistencia (los datos no se pierden)
- Consistencia
- Seguridad
- Correctitud en acceso concurrente

---
---
# Sistemas de archivos vs SGBD

- **Antes** los usuarios no interactuaban directamente, y todo pasaba por programas o intermediarios.
- **Hoy** en día, los usuarios pueden tener acceso a las bases de datos a través de cajeros automáticos, interfaces telefónicas, webs (Internet), etc.

***Antes de los SGBD***, se usaban **sistemas de archivos tradicionales**:
- Datos almacenados en archivos del sistema operativo
- Programas específicos para cada tarea

El tema es que, ***para cada nueva necesidad ⇒ nuevo programa + nuevos archivos.***

--- 

Un SGBD surge para resolver las limitaciones de los sistemas de archivos tradicionales, proporcionando una forma estructurada, eficiente y segura de almacenar, acceder y manipular grandes volúmenes de datos compartidos.

*El problema central no es almacenar datos, sino gestionarlos correctamente bajo condiciones de escala, concurrencia y cambio.*