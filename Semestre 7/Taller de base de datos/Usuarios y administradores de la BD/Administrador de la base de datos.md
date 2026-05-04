Una de las principales razones de usar SGBDs es tener un control centralizado tanto de los datos como de los programas que acceden a esos datos.

La persona que tiene este control central sobre el sistema se llama ***administrador de la base de datos (ABD).*** Las funciones del ABD incluyen las siguientes:
## Definición del esquema.
 El ABD crea el esquema original de la base de datos escribiendo un conjunto de instrucciones de definición de datos en el LDD.
## Definición de la estructura y del método de acceso.
## Modificación del esquema y de la organización física.
Los ABD realizan cambios en el esquema y en la organización física para reflejar las necesidades cambiantes de la organización, o para alterar la organización física para mejorar el rendimiento.
## Concesión de autorización para el acceso a los datos.
La concesión de diferentes tipos de autorización permite al administrador de la base de datos determinar a qué partes de la base de datos puede acceder cada usuario.

La información de autorización se mantiene en una estructura del sistema especial que el sistema de base de datos consulta cuando se intenta el acceso a los datos en el sistema.
## Mantenimiento rutinario.
- ***Copia de seguridad periódica*** de la base de datos, bien sobre cinta o sobre servidores remotos, para prevenir la pérdida de datos en caso de desastres como inundaciones.
- ***Asegurarse de que haya suficiente espacio libre en disco*** para las operaciones normales y aumentar el espacio en disco según sea necesario
- ***Supervisión de los trabajos que se ejecuten en la base de datos*** y asegurarse de que el rendimiento no se degrada por tareas muy costosas iniciadas por algunos usuarios