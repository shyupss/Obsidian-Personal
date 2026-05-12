> Un microservicio es una aplicación de pequeño tamaño que ejecuta su propio proceso y se comunica mediante mecanismos ligeros, generalmente una API de recursos HTTP.

Cada **microservicio es responsable de una funcionalidad completa del negocio**, se **despliega de forma independiente** y puede estar **desarrollado en diferentes lenguajes de programación** y tecnologías de almacenamiento.

Las características principales incluyen:
- **Poco acoplamiento:** Independencia entre los servicios.
- **Mantenibilidad:** Facilidad para realizar cambios sin afectar al sistema completo.
- **Independencia total:** Cada servicio es autónomo respecto al resto.
- **Especialización:** Cada componente implementa una arista específica del negocio (ej. gestión de usuarios).

---
# Comparativa: Monolitos vs. Microservicios

Históricamente, las aplicaciones se diseñaban como **monolitos**: grandes bloques de código difíciles de mantener y evolucionar.

En contraste, **la arquitectura de microservicios descompone la aplicación en servicios más pequeños e independientes que interactúan entre sí.**

> La decisión de migrar hacia microservicios depende del nivel de complejidad; para aplicaciones de baja complejidad, no se recomienda este diseño.

| Característica | Monolitos               | Microservicios           |
| -------------- | ----------------------- | ------------------------ |
| Estructura     | Bloque único y compacto | Componentes autónomos    |
| Despliegue     | Conjunto                | Independiente            |
| Escalabilidad  | Global                  | Por servicio (eficiente) |

---
# Ventajas de la Arquitectura de Microservicios

- Escalabilidad más eficiente e independiente.
- Posibilidad de realizar pruebas más concretas y específicas.
- Libertad tecnológica (diversidad de lenguajes y bases de datos).
- Desarrollos independientes y paralelos por diferentes equipos.
- Aumento de la tolerancia a fallos.
- Mejora sustancial de la mantenibilidad.

---
# Comunicación entre Microservicios

A diferencia de los monolitos, donde la comunicación es interna entre componentes, **los microservicios requieren mecanismos de propagación de información para informar eventos o desencadenar acciones en otros receptores.**

1. **Tipos de Comunicación:**
    - **Síncrona:** El emisor espera la respuesta del receptor (ej. HTTP o HTTPS). Requiere que los servicios tengan buen rendimiento y no sean excesivamente complejos.
    - **Asíncrona:** El emisor continúa su ejecución tras informar al receptor. Se basa en eventos (ej. RabbitMQ, Kafka o AMQP).
2. **Número de Receptores:**
    - **Uno a uno:** Comunicación directa entre un emisor y un receptor (tipo comando).
    - **Uno a varios:** El emisor informa a múltiples servicios sobre ciertos eventos a través de canales de suscripción.

