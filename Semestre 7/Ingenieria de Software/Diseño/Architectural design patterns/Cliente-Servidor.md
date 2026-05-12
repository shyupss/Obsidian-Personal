La arquitectura cliente-servidor es un modelo de distribución de aplicaciones donde **las tareas se reparten entre los proveedores de recursos o servicios, llamados servidores, y los demandantes, llamados clientes.** 

*Es la base de las tecnologías web modernas para centralizar datos y distribuir la carga de procesamiento.*

|Tecnología|Cliente Ejemplo|Servidor Ejemplo|
|---|---|---|
|**Web**|Navegador Chrome|Apache / Nginx|
|**Correo**|Outlook|Servidor SMTP|
|**Bases de Datos**|PgAdmin|PostgreSQL|

---
# Estructura y Características

Este modelo se define frecuentemente como una especialización de máquina virtual de 2 capas:
#### **Capa 1 (Cliente):**
Aplicación o interfaz que solicita los recursos. Los clientes conocen la ubicación y existencia del servidor.
#### **Capa 2 (Servidor):**
Procesa las solicitudes y entrega los recursos. El servidor, por diseño, **no conoce la identidad de los clientes de forma persistente *antes* de la conexión.**
#### **Conexión:**
Se realiza a través de una red (**Internet** o Intranet).

En este sistema, múltiples clientes independientes pueden acceder al mismo servidor de manera simultánea. 

Un ejemplo a gran escala es un sistema de gestión de medios donde clientes acceden a servidores de catálogo, video, imagen y servidores web especializados, todos interconectados mediante internet.

---

| Característica    | Detalle                                                                                                                                                                                                                                                        |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cuándo se usa** | Cuando se requiere acceso a una base de datos compartida desde múltiples ubicaciones. Es ideal para sistemas donde la carga es variable, ya que los servidores pueden replicarse.                                                                              |
| **Ventajas**      | Los servidores pueden distribuirse a través de la red. Una funcionalidad (como un servicio de impresión) está disponible para todos los clientes sin necesidad de implementarse localmente en cada uno.                                                        |
| **Desventajas**   | Cada servicio es un punto único de falla (susceptible a ataques DoS o caídas). El rendimiento es impredecible porque depende tanto de la red como del sistema. Puede haber conflictos administrativos si los servidores pertenecen a distintas organizaciones. |