El objetivo del PCA es explicar la mayor parte de la variabilidad en los datos con un número menor de variables que el conjunto de datos original.

Para un conjunto de datos con $p$ variables, podríamos examinar las gráficas por pares de cada variable contra cada otra variable, pero incluso para un $p$ moderado, el número de gráficos se vuelve excesivo y no es útil.

Por ejemplo, cuando $p=7$ hay $\frac{p(p-1)}{2}=21$ diagramas de dispersión que podrían analizarse.

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="PCA-con-p7.png" width="400">
	<br>
	<em>Ejemplo de PCA con siete variables.</em>
</div>

En particular, nos gustaría obtener una representación ***bidimensional*** de los datos que ***capturan la mayor parte de la información,*** entonces podemos proyectar las observaciones en este espacio de baja dimensión.

PCA proporciona una herramienta para hacer precisamente esto: Encuentra una ***representación de baja dimensión*** de un conjunto de datos que contiene la ***mayor cantidad de variación*** posible.

La idea es que cada una de las $n$ observaciones se encuentra en el espacio $p-dimensional$, pero ***no todas estas dimensiones son igualmente interesantes.***

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="variacion-pdimencional.png" width="400">
	<br>
	<em>Todas las dimensiones no son igual de interesantes</em>
</div>

PCA busca un ***pequeño número de dimensiones que sean lo más interesantes posible,*** donde el concepto de interesante se mide por ***la cantidad de observaciones que varían a lo largo de cada dimensión.***

***Cada una de las dimensiones encontradas por PCA es una combinación lineal de las características p*** y podemos tomar estas combinaciones lineales de las mediciones y ***reducir el número de gráficos necesarios para el análisis*** visual mientras retenemos la mayor parte de la información presente en los datos.