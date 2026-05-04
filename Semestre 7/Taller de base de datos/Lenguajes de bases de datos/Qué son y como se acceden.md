# ¿Que es un lenguaje de base de datos?

Un sistema de bases de datos proporciona un ***lenguaje de definición de datos*** para especificar el esquema de la base de datos y un ***lenguaje de manipulación de datos*** para expresar las consultas a la base de datos y las modificaciones.

En la práctica, ***los lenguajes de definición y manipulación de datos NO son dos lenguajes separados***; en su lugar simplemente forman partes de un único lenguaje de bases de datos, tal como SQL, ampliamente usado.
# Acceso a la base de datos

Los programas de aplicación son programas que se usan para interaccionar con la base de datos.

Los programas de aplicación se escriben usualmente en un **lenguaje anfitrión,** tal como Cobol, C, C++ o Java.

Para acceder a la base de datos, ***las instrucciones LMD necesitan ser ejecutadas desde el lenguaje anfitrión***. Hay dos maneras de hacerlo:

1. ***Proporcionando una interfaz de programas de aplicación*** (conjunto de procedimientos) que se pueden usar para enviar instrucciones LMD y LDD a la base de datos, y recuperar los resultados.

2. ***Extendiendo la sintaxis del lenguaje anfitrión*** para incorporar llamadas LMD dentro del programa del lenguaje anfitrión.

---