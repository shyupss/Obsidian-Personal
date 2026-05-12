> La calidad es un concepto complejo y multidimensional. En términos generales, se define como el **conjunto de propiedades inherentes a una entidad que permiten juzgar su valor.**

*Un producto o servicio se considera de calidad cuando es "apto para su uso o propósito".*

En el ámbito específico del software, la calidad implica satisfacer las necesidades y expectativas de los clientes en relación con diversas características críticas:
- **Funcionalidad:** El software debe realizar las tareas para las que fue diseñado.
- **Diseño:** Estructura y estética adecuada.
- **Fiabilidad:** Capacidad de operar sin fallos bajo condiciones específicas.
- **Durabilidad:** Longevidad del producto.
- **Precio:** Relación valor-costo del producto.

---
# Verificación vs. Validación

Estos dos procesos son pilares de la calidad, pero poseen enfoques y objetivos distintos que suelen resumirse en dos preguntas fundamentales:

| Verificación   | ¿Se está construyendo el producto correctamente? | Análisis de documentos, artefactos de diseño y código para asegurar que el software cumple con las especificaciones y requisitos definidos. |
| -------------- | ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Validación** | ¿Se está construyendo el producto correcto?      | Evaluación del producto final para garantizar que satisface las necesidades reales y expectativas del usuario en su entorno de uso.         |
### Diferencias Operativas

| Característica | Verificación                                          | Validación                                                       |
| -------------- | ----------------------------------------------------- | ---------------------------------------------------------------- |
| **Enfoque**    | Comprobación de documentos, diseño y código.          | Mecanismo dinámico de prueba del producto real.                  |
| **Ejecución**  | No necesariamente implica ejecutar código.            | Requiere la ejecución del código.                                |
| **Métodos**    | Revisiones, inspecciones y recorridos (walkthroughs). | Pruebas de caja negra, caja blanca, funcionales y de aceptación. |
| **Cronología** | Ocurre antes de la validación.                        | Ocurre después de la verificación.                               |
| **Detección**  | Encuentra errores generalmente durante el desarrollo. | Encuentra errores generalmente al final del desarrollo.          |

---
# Impacto de la Baja Calidad y Costos Asociados

La falta de calidad en el software no solo genera inconvenientes técnicos, sino que puede derivar en catástrofes financieras y pérdidas humanas.

### Casos de Estudio de Fallos Críticos

- **Privacidad y Seguridad:** Filtraciones masivas como la de Yahoo (3.000 millones de cuentas expuestas, con un costo de 50 millones de dólares) y Marriott (500 millones de afectados).
- **Operaciones Críticas:** Fallos de TI en British Airways en 2019 que causaron caos en aeropuertos de Londres, cancelando más de 60 vuelos.
- **Ciberseguridad en Automoción:** El hackeo de un Jeep permitió a atacantes controlar frenos, radio y cambios, provocando el retiro de 1.4 millones de vehículos.
- **Sistemas de Defensa (Patriot):** En 1991, un error de software en el cálculo de rastreo (debido a una inexactitud de 0,000000095 segundos) causó que el sistema ignorara un misil entrante, matando a 28 soldados. El error se agravaba con el tiempo de operación (más de 100 horas en el incidente).
- **Efecto Y2K:** Error basado en el ahorro de espacio al guardar fechas en formato `dd/mm/aa`. Se temía que al pasar de 1999 al 2000, los sistemas interpretaran el año como 1900, provocando fallos fatales en cascada.
### El Costo de un "Bugfix"

El costo relativo de corregir un error aumenta exponencialmente a medida que el software avanza en su ciclo de vida:
- **Requerimientos (Req):** 1x (Costo base).
- **Diseño:** 5x.
- **Código:** 10x.
- **Pruebas de Desarrollo (DevT):** 20x.
- **Pruebas de Aceptación (AccT):** 50x.
- **Operaciones (Ops):** >150x.

**Conclusión:** La calidad debe integrarse desde el inicio; no puede añadirse después (_W. Edwards Deming_).

---
# Aseguramiento de Calidad (QA) frente a Control de Calidad (QC)

Aunque ambos gestionan la calidad, sus roles son complementarios pero distintos:
#### **Aseguramiento de Calidad (QA):**
**Procedimiento para garantizar la calidad mediante la definición de procesos y estándares**. Se centra en mejorar el proceso de desarrollo para hacerlo eficiente y eficaz, siendo una actividad **proactiva** orientada a **prevenir defectos**.
#### **Control de Calidad (QC):**
Aplicación de los **procesos definidos para eliminar productos que no cumplen con el nivel requerido**. Se centra en el producto final, siendo una actividad **reactiva** orientada a **detectar defectos** después de la producción.

| Característica | Control de Calidad (QC) | Aseguramiento de Calidad (QA) |
| -------------- | ----------------------- | ----------------------------- |
| **Enfoque**    | Producto                | Proceso                       |
| **Naturaleza** | Reactivo                | Proactivo                     |
| **Función**    | Función de línea        | Función de staff              |
| **Meta**       | Encontrar defectos      | Prevenir defectos             |

---
# Objetivos y Principios del Aseguramiento de Calidad

El lema central de la disciplina es: *"prevenir en vez de curar o, al menos, detección temprana".*
### Objetivos Principales
1. Mejorar la calidad general del software.
2. Reducir los costos operativos derivados de la corrección de errores.
3. Aumentar la satisfacción del cliente final.
4. Cumplir rigurosamente con los plazos y presupuestos establecidos.
### Principios Fundamentales
- **Participación de todo el equipo:** La calidad no es responsabilidad de un solo departamento.
- **Prevención en lugar de corrección:** Anticiparse a los fallos mediante procesos robustos.
- **Medición y seguimiento:** Lo que no se mide no se puede mejorar.
- **Orientación al cliente:** El éxito se define por la satisfacción del usuario.

---
# Herramientas y Normas de Calidad

Para operativizar el **QA**, se requiere de un marco normativo y herramientas tecnológicas.
### Herramientas de QA
- **Automatización de pruebas:** Para ejecuciones repetitivas y regresión.
- **Gestión de defectos:** Seguimiento y priorización de errores.
- **Monitoreo e informes:** Dashboards (como los de Azure DevOps) que muestran métricas de sprints, velocidad, ítems completados y severidad de bugs activos.
### Normas y Estándares
1. **Normas internas o propietarias:** Específicas de cada organización.
2. **ISO 9001:2015:** Estándar internacional para sistemas de gestión de calidad.
3. **CMMI (Capability Maturity Model Integration):** Modelo de madurez para la mejora de procesos.
4. **IEEE 730:** Estándar específico para el aseguramiento de la calidad del software.