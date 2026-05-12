Los **modelos de interacción** se centran en capturar y representar cómo se comunica el sistema con su entorno y cómo interactúan sus propios componentes internos entre sí.

> Se parte de la premisa de que prácticamente todos los sistemas incluyen algún tipo de intercambio de información o acciones.

Estos modelos cubren tres tipos principales de interacciones:
1. **Interacciones del usuario:** que implican entradas y salidas de datos.
2. **Interacciones sistema a sistema:** entre el software que se está desarrollando y otros sistemas externos.
3. **Interacciones entre componentes:** el diálogo interno entre las partes que forman el sistema.

***Para modelar la interacción, se utilizan principalmente dos tipos de diagramas UML:***

---
# Diagramas de Caso de Uso

Se utilizan para modelar las interacciones entre el sistema y sus **actores externos**, que pueden ser tanto personas como otros sistemas.

- **Propósito:** Ayudan a definir qué hace el sistema desde el punto de vista del usuario, sin entrar en detalles técnicos de cómo lo hace.
- **Elementos clave:** Incluyen al **actor** (quién interactúa), el **caso de uso** (la funcionalidad específica), el **sujeto** (los límites del sistema) y las líneas de comunicación que los conectan.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="casodeuso.png" width="300">
	<br>
	<em>Diagrama de caso de uso</em>
</div>

---
# Diagramas de Secuencia

Mientras que los casos de uso dicen _qué_ sucede, los diagramas de secuencia se encargan de modelar el **comportamiento dinámico** del sistema a lo largo del tiempo.

- **Propósito:** Muestran cómo responden los objetos o componentes ante eventos específicos, detallando el orden cronológico de los mensajes.
- **Elementos clave:** Utilizan **líneas de vida** para los objetos, **mensajes** representados por flechas y estructuras de control como **bucles** (_loops_) o **alternativas** (_alt_) para manejar condiciones lógicas complejas.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="diagramadesecuencias.png" width="350">
	<br>
	<em>Diagrama de secuencias UML</em>
</div>
