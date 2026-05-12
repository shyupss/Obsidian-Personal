El patrón de diseño MVC es una de las arquitecturas de software más utilizadas en el desarrollo de aplicaciones.

> MVC propone la construcción de tres componentes distintos que son el modelo, la vista y el controlador, es decir, por un lado **define componentes para la representación de la información, y por otro lado para la interacción del usuario.**

## Componentes del Sistema

#### **El Modelo:**
Es el núcleo de la aplicación. **Representa los datos y la lógica de negocio.** Se encarga de gestionar todos los accesos a la información, incluyendo consultas y actualizaciones.

Además, implementa los privilegios de acceso definidos en las especificaciones y mantiene la integridad de los datos.

*En una arquitectura robusta, el modelo interactúa directamente con la base de datos para realizar la persistencia.*
#### **La Vista:**
**Es la interfaz que presenta el modelo al usuario en un formato adecuado para la interacción.** Su función es puramente representativa; recibe los datos procesados y los renderiza de forma dinámica para que el usuario final pueda visualizarlos.
#### **El Controlador:**
**Actúa como intermediario entre la vista y el modelo.** 

> Su responsabilidad es responder a los eventos (usualmente acciones del usuario como clics o entradas de teclado) e invocar peticiones al modelo.

**El controlador gestiona el flujo de las solicitudes, pero nunca debe manejar la lógica de datos de forma directa.**

*También puede enviar comandos a la vista para modificar la forma en que se presenta la información.*

---
# Flujo de Interacción y Arquitectura

El flujo típico de una operación en MVC sigue esta secuencia:

1. El **Usuario** realiza una solicitud (Request).
2. El **Controlador** recibe la solicitud y gestiona el flujo.
3. El **Controlador** solicita datos al **Modelo** (Fetch Data).
4. El **Modelo** interactúa con la **Base de Datos** y devuelve los datos al controlador.
5. El **Controlador** envía los datos procesados a la **Vista** (Fetch Presentation).
6. La **Vista** responde visualmente al usuario.

---

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="modelo-vistacontrolador.png" width="300">
	<br>
	<em>Modelo vista controlador</em>
</div>

---

| Característica    | Detalle                                                                                                                                                                                   |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cuándo se usa** | Cuando existen múltiples formas de ver e interactuar con los datos, o cuando se desconocen los requerimientos futuros de interacción y presentación.                                      |
| **Ventajas**      | Permite que los datos cambien independientemente de su representación. Soporta múltiples vistas para los mismos datos, donde los cambios en una se reflejan automáticamente en las demás. |
| **Desventajas**   | Puede introducir código adicional y una complejidad innecesaria cuando el modelo de datos y las interacciones del sistema son simple                                                      |
