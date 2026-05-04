### ¿Qué son las comunicaciones de datos?
Las comunicaciones de datos estudian cómo **transmitir información entre dispositivos** de manera **eficiente y confiable** mediante señales.
### Modelo de comunicaciones de datos
El proceso de comunicación puede representarse como:

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="modelo-comunicaciones-de-datos.png" width="600">
	<br>
	<em>Diagrama general de bloques</em>
</div>

### Etapas del proceso
### 1. Generación del mensaje  
El usuario genera un mensaje $(m)$.  

<hr>
### 2. Representación en datos  
El mensaje se convierte en una secuencia de bits $(g)$.  

<hr>
### 3. Transmisor  
Convierte los bits en una señal electromagnética: $g(t) → s(t)$ 

<hr>
### 4. Transmisión  
La señal se propaga a través del medio. $s(t) → r(t)$

Durante este proceso:  
- la señal se distorsiona  
- aparece ruido  

<hr>
### 5. Receptor  
Intenta reconstruir la señal original:  $r(t) → g'(t)$  

<hr>
### 6. Reconstrucción del mensaje  
Los bits se convierten nuevamente en mensaje:  $m' ≈ m$

<hr>
### ¿Qué problemas aparecen?
Durante la comunicación surgen problemas como:  
- distorsión de la señal  
- errores en los datos  
- diferencias de velocidad  
- fallos en la transmisión

Estos problemas dan origen a las tareas en las tareas en los sistemas de comunicación vistos en la introducción.