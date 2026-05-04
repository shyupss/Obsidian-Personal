Un sistema de bases de datos se divide en módulos funcionales para gestionar grandes volúmenes de información, que pueden oscilar desde gigabytes hasta terabytes. Dado que la memoria principal (RAM) es insuficiente para albergar tales cantidades, los datos residen en discos físicos y se trasladan a la memoria según sea necesario.

Los componentes funcionales se dividen en dos categorías principales: el **gestor de almacenamiento** y el **procesador de consultas**.

---
---
### Gestor de Almacenamiento

Este módulo proporciona la interfaz entre los datos de bajo nivel almacenados en el disco y los programas de aplicación o consultas enviadas al sistema. Es el encargado de interactuar con el gestor de archivos del sistema operativo.

| Componente                              | Función Principal                                                                                                  |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Gestor de Autorización e Integridad** | Comprueba que los usuarios tengan permiso de acceso y que se cumplan las restricciones de integridad.              |
| **Gestor de Transacciones**             | Asegura que la base de datos sea consistente a pesar de fallos y gestiona la ejecución concurrente sin conflictos. |
| **Gestor de Archivos**                  | Gestiona la reserva de espacio en disco y las estructuras de datos para representar la información.                |
| **Gestor de Memoria Intermedia**        | Responsable de traer datos del disco a la memoria principal y decidir qué información debe permanecer en la caché. |
#### Estructuras de Datos Implementadas

Para facilitar el acceso físico, el gestor de almacenamiento utiliza:

- **Archivos de datos:** Donde se almacena la base de datos propiamente dicha.
- **Diccionario de datos:** Almacena los metadatos, especialmente el esquema de la base de datos.
- **Índices:** Permiten un acceso rápido a elementos de datos específicos.

---
### Procesador de Consultas

Su función es simplificar el acceso a los datos, traduciendo instrucciones de alto nivel (lenguajes no procedimentales) a operaciones de bajo nivel que el sistema físico pueda ejecutar de manera eficiente.

| Componente                           | Función Principal                                                                                                                                                    |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Intérprete del LDD**               | Interpreta las instrucciones del Lenguaje de Definición de Datos y registra las definiciones en el diccionario de datos.                                             |
| **Compilador del LMD**               | Traduce las instrucciones del Lenguaje de Manipulación de Datos en un plan de evaluación. Realiza la **optimización de consultas** eligiendo el plan de menor coste. |
| **Motor de Evaluación de Consultas** | Ejecuta las instrucciones de bajo nivel generadas por el compilador del LMD.                                                                                         |

---

<div style="border:2px solid #888; padding:10px; width:600px; margin:auto; text-align:center;">
	<img src="estructura-del-sistema.png" width="500">
	<br>
	<em>Estructura del sistema</em>
</div>