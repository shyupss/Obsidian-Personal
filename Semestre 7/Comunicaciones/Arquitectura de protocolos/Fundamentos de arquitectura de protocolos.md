La comunicación entre sistemas es un proceso complejo que involucra múltiples tareas, tales como:  
- establecer un camino entre origen y destino  
- identificar correctamente el sistema destino  
- verificar que el receptor está preparado para recibir datos  
- garantizar compatibilidad en el formato de la información
### Problema de diseño
Implementar todas estas funciones en un único módulo genera:
- alta complejidad  
- dificultad de mantenimiento  
- baja escalabilidad

<hr>
### Solución: arquitectura en capas  
Para manejar esta complejidad, el sistema de comunicación se organiza en una **arquitectura de protocolos**, basada en capas.

Cada capa:
- realiza un subconjunto de tareas específicas  
- utiliza los servicios de la capa inferior  
- proporciona servicios a la capa superior
### Funcionamiento  
- las capas se organizan de forma jerárquica  
- cada capa es independiente de las demás  
- cambios en una capa no deberían afectar a otras

<hr>
### Comunicación entre sistemas
La comunicación se realiza entre **capas equivalentes (capas pares)** en distintos sistemas, mediante protocolos.
### Concepto de protocolo  
Un protocolo define las reglas de comunicación entre capas pares y se caracteriza por:  
- **Sintaxis**: formato de los datos  
- **Semántica**: significado y control de la información  
- **Temporización**: sincronización y velocidad de transmisión
### Concepto de arquitectura de protocolos  
Una arquitectura de protocolos es una estructura organizada en capas, compuesta por módulos de hardware y software, que permite gestionar el intercambio de datos entre sistemas.  

En esta arquitectura, las funciones necesarias para la comunicación se dividen en distintos módulos, cada uno encargado de un subconjunto de tareas relacionadas.

Cada módulo:  
- realiza funciones específicas dentro del proceso de comunicación  
- utiliza los servicios del módulo inferior  
- proporciona servicios al módulo superior

La arquitectura se dispone de forma jerárquica, formando una pila de capas, donde cada capa abstrae los detalles de las capas inferiores.

Además, para que exista comunicación entre sistemas, es necesario que cada capa tenga una entidad equivalente en el sistema remoto. Estas entidades se comunican mediante protocolos, que definen las reglas para el intercambio de información.

---

