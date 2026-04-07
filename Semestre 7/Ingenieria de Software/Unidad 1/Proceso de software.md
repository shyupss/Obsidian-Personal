# Fases de un proyecto

Un proyecto en general se divide en distintas etapas:
- idea del proyecto
- preparación
- planificación
- ejecución y control
- cierre
- evaluación posterior

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="fases-de-un-proyecto.png" width="600">
	<br>
	<em>Fases de un proyecto</em>
</div>

El software se inserta dentro de un **marco de gestión de proyectos**, no vive aislado.

---
# 1. Fase de preparación

En esta fase se debe decidir si el proyecto se lleva a cabo o no.

Entonces, se debe analizar:
- Necesidad del proyecto
- Valoración económico
- Viabilidad de la idea

👉 Antes de programar, se decide si **debería existir el sistema**.

Dentro de la fase de preparación existen dos productos principales:

1. **Project charter (cartera del proyecto)**: documento que autoriza formalmente la existencia de un proyecto y confiere al director del proyecto la autoridad para asignar los recursos de la organización a las actividades del proyecto.
	- Convierte una idea abstracta en un objetivo concreto
	- Justifica la necesidad del proyecto
	- Incluye una estimación de beneficios financieros
	- Incluye una estimación de requisitos preliminares

2. **Estudio de viabilidad:** permite a las organizaciones determinar si el proyecto es posible, rentable y conveniente.
	Para esto existen distintos tópicos a analizar:
	- **Viabilidad económica**: ¿Cuánto costará monetariamente el proyecto?
	- **Viabilidad Técnica**: ¿Tenemos el conocimiento/tecnología necesaria? 
	- **Viabilidad Temporal**: ¿Cuánto nos demoraremos en el proyecto?
	- **Viabilidad Operativa**: ¿El sistema puede ser utilizado eficazmente en un entorno real?
	- **Viabilidad Legal**: ¿Cumplo con la ley?

---
# 2. Fase de planeación

Selección de una estrategia para producir un producto, así como la definición de las actividades a realizar para conseguir ese objetivo, la concurrencia y solapamiento de dichas actividades y recursos asignados.
	- ¿Qué actividades debo hacer? 
	- ¿Cuándo? 
	- ¿Cuánto va a costar hacerlas?
	- ¿Qué recursos necesito?
	- ¿Quién es el responsable de cada tarea?
#### Actividades durante la ejecución de un proyecto software
<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="actividades-software.png" width="600">
	<br>
	<em>Actividades durante la ejecución de un proyecto software</em>
</div>

---
# Ciclo de vida

Un ciclo de vida es la evolución de un sistema, producto, servicio, proyecto u otra entidad, desde su concepción hasta el retiro.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="evolucion-de-un-sistema.png" width="600">
	<br>
	<em>Evolucion de un sistema</em>
</div>

La función principal de un ciclo de vida de un software es determinar el orden de las fases así como de los procesos involucrados en el desarrollo de software, teniendo en cuenta el modelo que se haya utilizado como referencia.

El marco de referencia que contiene:
- Fases/Etapas
    - Procesos
	    - Actividades
		    - Tareas

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="descomposicion-jerarquica.png" width="300">
	<br>
	<em>Descomposicion jerarquica</em>
</div>

---
# Modelos de procesos

Los modelos describen los procesos que podrían utilizarse para adquirir, suministrar, desarrollar, explotar, soportar y mantener el software, es decir desde que surge la idea hasta que se retira.

No buscan imponer la utilización de un modelo de ciclo de vida específico, el uso de técnicas o herramientas de software específicas o una estructura de organización para un proyecto de desarrollo.

Cada empresa debería seleccionar para cada proyecto los procesos que considere necesarios realizar (con las actividades que crea convenientes) y establecer sus propios ciclos de vida.

Ej: ISO 12207, …

---
# Diferencia entre modelos de procesos y de ciclos de vida

Un Modelo de Procesos determina qué procesos pueden utilizarse para desarrollar software.

El Ciclo de Vida determina cuáles son los procesos y en qué orden se realizan, y cuáles son las actividades y/o tareas implicadas que voy a utilizar en mi desarrollo concreto.

---
# Modelos de ciclo de vida

## Cascada (predictivo)
Se usa una secuencia uniforme y ordenada de las fases de desarrollo. En cada fase empieza cuando termina la anterior
### Ventajas
- Fácil de planificar, comprender y seguir.
### Desventajas
- Inflexible
- Exige definición completa de requisitos al comienzo.
- No se adapta a cambios en funcionalidad y tecnología
- Lento y costoso – requiere mucha documentación y un proceso muy estricto de desarrollo
- Producto disponible al final del desarrollo del proyecto.
### Cuando usar
Cuando los requisitos son estables y están bien comprendidos al comienzo del desarrollo. El usuario prefiere todas las funcionalidades en la primera entrega

---
## Incremental
El sistema se construye **por partes funcionales (incrementos)**, donde cada incremento añade nueva funcionalidad al sistema existente.
### Cómo funciona
1. defines funcionalidades globales
2. decides qué implementar primero
3. construyes un **incremento**
4. entregas una versión parcial
5. agregas otro incremento
### Características
- no es lineal
- hay planificación inicial
- entregas parciales
- sistema crece progresivamente
## Ventajas
- feedback temprano
- entrega valor rápido
- más flexible que cascada
### Problemas
- errores de requisitos pueden aparecer tarde
- requiere buena gestión
- integración puede ser compleja

*Se recomienda este ciclo de vida cuando: Los requisitos están bien comprendidos al comienzo del desarrollo. O el usuario se beneficia de obtener versiones intermedias.*

---
# Modelo iterativo

 El sistema se desarrolla en ciclos donde **se redefine y mejora continuamente**, sin requerir todos los requisitos al inicio.
### Cómo funciona
1. se tiene una idea inicial incompleta
2. se construye una versión básica
3. se obtiene feedback
4. se vuelve a diseñar
5. se mejora el sistema
6. repites
### Características clave
- no es lineal
- hay planificación inicial
- entregas parciales
- sistema crece progresivamente
## Ventajas
- alta adaptabilidad
- ideal para problemas inciertos
- aprendizaje continuo
## Problemas
- difícil estimar tiempo
- difícil medir progreso
- riesgo de nunca terminar

*Se recomienda cuando los requisitos o el diseño no están completamente definidos al comienzo del desarrollo y es posible que haya grandes cambios. También cuando se están probando nuevas tecnologías.*

Sin embargo, la práctica tiene una crítica sobre los modelos de ciclo de vida...
[[Evolución del proceso]]