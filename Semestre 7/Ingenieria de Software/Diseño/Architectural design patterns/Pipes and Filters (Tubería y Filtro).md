Este patrón **describe un modelo para sistemas que procesan flujos de datos**.

> En esta arquitectura, cada paso de procesamiento se encapsula dentro de un componente llamado filtro (transformador). Los datos se desplazan a través de conectores denominados tuberías (pipes).

---
# Modelo de Operación

Las transformaciones funcionales procesan sus entradas y producen salidas de manera secuencial o paralela. Los datos fluyen de un componente a otro y se transforman conforme se desplazan por la secuencia. Los filtros pueden procesar los datos de dos formas:

1. **Ítem por ítem:** Procesamiento en tiempo real del flujo de datos.
2. **Lote (Batch):** Procesamiento de un conjunto de datos en un solo bloque.

---

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="pipes&filters.png" width="400">
	<br>
	<em>Diseño arquitectónico - Pipes & Filters</em>
</div>

---

| Característica    | Detalle                                                                                                                                                                                                                                 |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Cuándo se usa** | Común en aplicaciones de procesamiento de datos (batch o transaccionales) donde las entradas se procesan en etapas separadas para generar salidas relacionadas.                                                                         |
| **Ventajas**      | Fácil de entender y altamente reutilizable. El flujo de trabajo coincide con muchas estructuras empresariales. Permite una evolución directa al agregar nuevas transformaciones. Puede ser secuencial o concurrente.                    |
| **Desventajas**   | Requiere un acuerdo estricto sobre el formato de transferencia de datos entre filtros. El análisis y síntesis constante de formatos aumenta la carga del sistema y puede impedir la reutilización si las estructuras son incompatibles. |
