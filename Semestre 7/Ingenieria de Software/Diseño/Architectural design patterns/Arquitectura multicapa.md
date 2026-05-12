**Multi-Layer Architecture** y como su propio nombre indica, refleja **la separación lógica en capas de un sistema de software.**

> Las capas en esta arquitectura están organizadas de forma jerárquica unas encima de otras y las dependencias siempre van hacia el interior.

Es decir, una capa concreta dependerá solamente de capas inferiores pero nunca de las superiores.

***Las capas mas comunes son de: Presentación, Aplicación, Dominio de negocio y acceso o persistencia de datos.***
## Capas

> Una capa ofrece un conjunto de servicios (“interface” o API). Dichos servicios pueden ser accedidos por programas que residen en la capa superior.

*La encapsulación de la implementación de los servicios de la capa puede ser de 2 modos, **estricto y no estricto:***
- **Estricto:** Los programas en la Capa 1 solo pueden acceder a servicios de la Capa 2 (inmediatamente inferior).
- **No Estricto:** Los programas en la Capa 1 pueden saltar capas y acceder directamente a la Capa 3 o inferiores.
#### **Capa de Presentación**
Es la encargada de ***gestionar la interacción que tiene el cliente con nuestra aplicación.*** Actúa como mediador.
#### **Capa de Aplicación**
Contiene los casos de uso que implementan la lógica de negocio. Es decir, el conjunto de reglas sobre las que se rige nuestra aplicación (establecidas por la organización).
#### **Capa de dominio**
Contiene las entidades del negocio.
#### **Capa de datos**
Su tarea principal es la persistencia y recuperación de los datos.

---

***Se explicó una arquitectura basada en cuatro capas, pero dependiendo de la organización y de las necesidades del negocio pueden haber variaciones.***

---

|Dimensión|Descripción|
|---|---|
|**Cuándo se usa**|Al construir sobre sistemas existentes; cuando el desarrollo se reparte en varios equipos responsables de funcionalidades específicas; cuando se requiere seguridad multinivel.|
|**Ventajas**|Permite sustitución de capas completas (si se mantiene la interfaz). Posibilidad de incluir facilidades redundantes (ej. autenticación en cada capa) para aumentar confiabilidad.|
|**Desventajas**|Dificultad para lograr una separación limpia; a veces es necesario interactuar con capas no adyacentes. El rendimiento puede verse afectado por los múltiples niveles de interpretación de una solicitud.
