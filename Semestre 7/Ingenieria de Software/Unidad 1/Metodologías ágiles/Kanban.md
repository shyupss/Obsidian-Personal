
Originado en japón, por Toyota en los años 40. Se utilizaba como un sistema de control de inventario para optimizar la producción en las fábricas. Kanban en japonés significa “Tarjeta visual” o “señal” y se refiere a las tarjetas físicas usadas para indicar el flujo de trabajo y la disponibilidad de los materiales en el proceso de fabricación. El modelo fue adoptado por el ámbito de desarrollo de software en la década de los 2000.

Se basa en una filosofía centrada en la mejora continua. Las tareas se extraen de una lista de acciones pendientes en un flujo de trabajo constante.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="kanban.png" width="500">
	<br>
	<em>Kanban</em>
</div>

## Visualización

La visualización es fundamental en Kanban. Se utiliza un tablero Kanban, generalmente dividido en columnas que representan diferentes etapas del flujo de trabajo, desde la idea hasta la entrega. Cada tarea o elemento de trabajo se representa como una tarjeta que se mueve a través del tablero a medida que avanza en el proceso.

Las columnas del tablero típicamente incluyen las etapas como "Por hacer", "En progreso", "En revisión" y "Completado".

## Limitación del trabajo en proceso (WIP)

Se establece un límite en la cantidad de trabajo que se puede realizar simultáneamente en cada etapa del flujo de trabajo. Limitar el trabajo en proceso ayuda a evitar la sobrecarga de trabajo, reducir el tiempo de espera y mantener un flujo constante de trabajo.

Un desarrollador no puede empezar una nueva tarea hasta que haya completado o movido al menos una tarea al estado "Completado". Limitar el WIP ayuda a evitar la multitarea excesiva y a mantener un flujo de trabajo más fluido.

## Flujo continuo

Kanban se centra en optimizar el flujo de trabajo, identificando cuellos de botella, eliminando desperdicios y maximizando la eficiencia en cada etapa del proceso. Se anima a los equipos a identificar y abordar los obstáculos que ralentizan el flujo de trabajo.

***Ej.*** Durante una reunión regular de revisión del flujo, el equipo identifica que la etapa de revisión de código está siendo un cuello de botella. Deciden asignar más recursos para revisar el código o implementar un sistema de rotación de tareas para equilibrar la carga de trabajo

## Feedback

Kanban promueve la mejora continua mediante la revisión regular del proceso y el rendimiento del equipo. Se fomenta la retroalimentación continua de los clientes y los miembros del equipo para identificar áreas de mejora y realizar ajustes en el proceso.

***Ej.*** Después de cada iteración de desarrollo, el equipo realiza una retrospectiva para analizar lo que salió bien, lo que salió mal y qué se puede mejorar. Basándose en esta retroalimentación, ajustan sus procesos y prácticas para la siguiente iteración, como mejorar la comunicación entre el equipo o implementar nuevas herramientas de prueba automatizadas.

## Gestión

Kanban requiere que las políticas y reglas del proceso de desarrollo de software sean claras y estén explícitamente definidas. Esto ayuda a garantizar que todos los miembros del equipo comprendan cómo se debe realizar el trabajo y cuáles son las expectativas en cada etapa del proceso.

## Mejora continua

Kanban adopta un enfoque pragmático y evolutivo para la implementación de cambios. En lugar de realizar cambios radicales, se fomenta la implementación de pequeñas mejoras incrementales de manera continua, lo que permite a los equipos adaptarse gradualmente y aprender de la experiencia

***Ej.*** En lugar de cambiar todo el proceso de desarrollo de un proyecto de una sola vez, el equipo decide implementar una pequeña mejora cada semana. Por ejemplo, podrían comenzar por automatizar las pruebas de integración antes de pasar a la mejora del proceso de despliegue continuo en las siguientes semanas.

---
# Tablero Kanban

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="kanban-board.png" width="600">
	<br>
	<em>Tablero kanban</em>
</div>

---
# ¿Cuándo implementar kanban?

- **Flujo de trabajo no lineal:** Cuando el equipo enfrenta un flujo de trabajo impredecible o no lineal, donde las tareas surgen de manera irregular y no se ajustan bien a los ciclos de desarrollo predefinidos. Kanban es especialmente útil para proyectos de mantenimiento o soporte, donde las solicitudes de trabajo pueden surgir en cualquier momento y necesitan ser abordadas de manera rápida y eficiente.
- **Necesidad de visibilidad y transparencia:** Cuando se requiere una mayor visibilidad y transparencia en el proceso de desarrollo para que todos los miembros del equipo comprendan el estado de cada tarea y dónde se encuentra en el flujo de trabajo.
- **Enfoque en mejora continua:** Cuando el equipo busca un enfoque de mejora continua en su proceso de desarrollo, Kanban proporciona un marco para identificar y abordar los cuellos de botella, eliminar desperdicios y optimizar el flujo de trabajo de manera constante.