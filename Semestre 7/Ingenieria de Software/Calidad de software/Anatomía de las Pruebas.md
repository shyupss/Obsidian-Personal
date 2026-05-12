# Metodología de Pruebas: Conceptos y Casos de Prueba

El **ISTQB** (International Software Testing Qualifications Board) establece los estándares profesionales para los distintos roles en pruebas (Tester Ágil, Analista de Pruebas, Gerente de Pruebas, etc.).
### Terminología Técnica de un Caso de Prueba

- **Software bajo prueba (SUT):** El módulo o sistema específico que se está evaluando.
- **Datos de prueba (Input):** Valores de entrada necesarios para la ejecución.
- **Setup (Configuración):** Precondiciones necesarias antes de probar (ej. el usuario debe existir en la BD).
- **Pasos de la Prueba (Invocation):** Acciones secuenciales que el tester debe realizar.
- **Resultado Esperado (Expected Outcome):** Comportamiento definido por los requisitos.
- **Oráculo (Oracle):** Método para validar si el resultado real coincide con el esperado (puede ser una persona, un robot o un fragmento de código).
- **Teardown (Limpieza):** Acciones para retornar el sistema al estado original (ej. borrar datos insertados en la BD).
- **Informe (Reporting):** Documentación del éxito o fallo, incluyendo evidencias (capturas, videos).