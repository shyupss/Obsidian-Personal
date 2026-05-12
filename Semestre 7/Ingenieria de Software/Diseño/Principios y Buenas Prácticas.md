
---
# Consistencia Eventual

> Es una estrategia para mantener la información actualizada en sistemas distribuidos o de microservicios.

**Cuando un microservicio modifica un dato, el cambio se propaga a todas las partes que lo manejan.**

A diferencia de un monolito con una única base de datos, **aquí puede haber momentos donde la información no sea consistente**, por lo que *se requieren mecanismos de recuperación (ej. Dead Letter Queue, histórico de eventos).

Se implementa comúnmente mediante modelos basados en eventos (AMQP, RabbitMQ, Kafka).

---
# El Principio ACID

Es el estándar de las bases de datos relacionales para garantizar transacciones confiables. Una transacción es una operación lógica que puede afectar múltiples tablas. Los términos son:

- **Atomicidad (Atomicity):** Las transacciones son "todo o nada". Si falla una parte, falla toda la operación.
- **Consistencia (Consistency):** Solo se guardan datos que respeten las reglas y restricciones definidas.
- **Aislamiento (Isolation):** Las transacciones concurrentes no se afectan entre sí; el resultado es el mismo que si fueran secuenciales.
- **Durabilidad (Durability):** Una vez confirmada la transacción, los datos persisten y no se pierden.

---
# Y.A.G.N.I (You Aren't Gonna Need It)

Este principio advierte contra la escritura de código basado en especulaciones de necesidades futuras ("podríamos necesitarlo algún día").

El desarrollo basado en especulación es riesgoso; se debe centrar el esfuerzo únicamente en lo necesario para cumplir con los requerimientos actuales, evitando "mega-soluciones" para problemas que podrían no ocurrir o cambiar.

---
# K.I.S.S (Keep It Simple Stupid!)

Principio acuñado por Kelly Johnson que aboga por la sencillez. Establece que cualquier sistema funciona mejor si se mantiene simple en lugar de complejo.

La meta es eliminar la complejidad innecesaria. Se cita a menudo la frase: *"Debemos olvidarnos de las pequeñas eficiencias, digamos el 97% del tiempo: la optimización prematura es la raíz de todos los males".*

---
# D.R.Y (Don’t Repeat Yourself) y D.I.E (Duplication Is Evil)

Ambos conceptos se resumen en: **no te repitas y la duplicación es el mal**. El código repetido es una fuente crítica de errores, ya que las actualizaciones o correcciones suelen aplicarse solo en una de las copias, dejando el sistema en un estado inconsistente y vulnerable a la reaparición de fallos.

---
# The Boy Scout Rule

Inspirada en la regla de los Boy Scouts de dejar el campamento más limpio de como se encontró.

> En software, implica que si un desarrollador encuentra código que puede mejorarse, debe hacerlo independientemente de quién sea el autor original.

*El objetivo es mejorar la calidad continua del código y evitar su deterioro técnico.*