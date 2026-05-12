CQRS es un patrón de arquitectura cuyo acrónimo significa **Segregación de Responsabilidad de Consultas y Comandos**.

> Su premisa fundamental es la separación técnica de los modelos utilizados para la lectura de datos de aquellos utilizados para la escritura o actualización de los mismos. 

*Aunque esta separación aporta un valor significativo en escenarios específicos, se reconoce que introduce una complejidad adicional que debe ser evaluada cuidadosamente.*

---
# Modelos de Consulta y Comando

La idea central se basa en la _Command Query Separation_, dividiendo las operaciones en dos categorías:
- **Consultas (Query Model):** Se encargan de devolver un resultado basado en el estado del sistema sin provocar efectos secundarios (operaciones de solo lectura).
- **Comandos (Command Model):** Tienen como objetivo cambiar el estado del sistema. Por definición, estas operaciones no deben devolver un valor.

---
# Integración con otros Patrones Arquitectónicos

CQRS **no es un patrón aislado**; se integra naturalmente con otros enfoques:

- **Interfaces basadas en tareas:** Permite alejarse del modelo CRUD tradicional hacia interfaces de usuario más específicas.
- **Programación basada en eventos:** Encaja con servicios que se comunican mediante _Event Collaboration_ y aprovechan el _Event Sourcing_ (Abastecimiento de eventos).
- **Domain-Driven Design (DDD):** Es adecuado para dominios complejos donde se aplica el diseño impulsado por el dominio y el concepto de _Bounded Context_.
- **Optimización de lectura:** En dominios que requieren mucha lógica en la actualización, se pueden usar patrones como _Eager Read Derivation_ para simplificar las consultas.

---
# Criterios de Aplicación y Escalabilidad

El uso de CQRS debe limitarse a partes específicas de un sistema (un _Bounded Context_ determinado) y no aplicarse a la totalidad del mismo a menos que sea estrictamente necesario. Sus principales beneficios se observan en:

1. **Dominios complejos:** Donde la lógica de negocio dificulta el manejo unificado de datos.
2. **Escalabilidad independiente:** Permite separar la carga de lectura y escritura, escalando cada una según la demanda específica del sistema.