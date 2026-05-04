Un "red herring" es una distracción que desvía del objetivo real. En MySQL, el hardware y el _tuning_
suelen actuar como tales.
### El Hardware como Distracción

No se debe comenzar escalando el hardware para "ver si ayuda". El escalado debe ser el último recurso, tras optimizar consultas, datos y patrones de acceso. Las razones para evitar el escalado prematuro son:
1. **Falta de aprendizaje:** No se descubre la causa raíz del problema.
2. **Insostenibilidad:** El escalado físico es complejo y los costos en la nube pueden crecer exponencialmente.
3. **Límites del workload:** Si la aplicación causa escaneos de tabla, más memoria no solucionará el problema de fondo.
### Ajuste (Tuning) de MySQL

Se diferencian tres conceptos críticos que a menudo se confunden:

| Término                         | Definición                                                                        | Objetivo                                                          |
| ------------------------------- | --------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Tuning (Ajuste)**             | Ajuste de variables de sistema para investigación y desarrollo (I+D).             | Expandir el conocimiento sobre los límites de MySQL.              |
| **Configuring (Configuración)** | Establecer variables apropiadas para el hardware y el entorno.                    | Una ejecución general razonable del servidor.                     |
| **Optimizing (Optimización)**   | Mejorar el rendimiento reduciendo la carga de trabajo o haciéndola más eficiente. | Respuesta más rápida y mayor capacidad con el hardware existente. |

Como solución práctica, MySQL 8.0 introdujo la configuración automática con `innodb_dedicated_server`, haciendo que el ajuste manual sea cada vez menos necesario.