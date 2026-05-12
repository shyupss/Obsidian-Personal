Los modelos de comportamiento **describen la dinámica del sistema**, es decir, **qué sucede cuando el sistema responde a estímulos provenientes de su entorno**, procesando **datos** o reaccionando a **eventos**.

---
# Modelado dirigido por datos

Muestran la secuencia de acciones involucradas en el procesamiento de datos de entrada y la generación de una salida asociada.

> Son particularmente útiles durante el análisis de requisitos, pues sirven para mostrar el procesamiento “extremo a extremo” de un sistema.

***Históricamente se modelaba con DFD (Data-Flow Diagram), UML no soporta esos diagramas y propone usar diagramas de actividad.***

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="modeladodirigidopordatos.png" width="400">
	<br>
	<em>Modelado dirigido por datos</em>
</div>

---
# Modelado dirigido por eventos

Muestra cómo un sistema responde a eventos externos e internos. 

> Se basa en la suposición de que un sistema tiene un número infinito de estados y que los eventos (estímulos) pueden causar una transición de un estado a otro.

***UML soporta modelado basado en eventos usando diagramas de estado.***

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagramadeestados.png" width="350">
	<br>
	<em>Diagrama de estados</em>
</div>
