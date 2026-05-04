
El antipatrón consiste en construir cadenas de consulta SQL mediante la **concatenación directa** de variables de entrada del usuario.

Al tratar la entrada del usuario como parte del comando SQL, se le otorga al usuario el poder de alterar la lógica de la consulta.
## El error fundamental

El texto identifica que el error no es la construcción dinámica de la consulta, sino el proceso de permitir que datos externos "salten" de ser simples valores a convertirse en código ejecutable.

**Ejemplo de código vulnerable:**
- Si un usuario malintencionado ingresa algo como `' OR '1'='1`, la consulta final se transforma en algo que el desarrollador no planeó:
- Esto devolvería todas las cuentas de la base de datos, evadiendo cualquier lógica de autenticación.
## Riesgos de seguridad y consecuencias

La inyección de SQL puede llevar a:
- **Fuga de datos:** Acceso no autorizado a información sensible.
- **Pérdida de datos:** Ejecución de comandos como `DROP TABLE` o `DELETE`.
- **Compromiso del sistema:** En algunos casos, el atacante puede ejecutar comandos a nivel del sistema operativo a través de funciones de la base de datos.

---
# Cómo reconocerlo

Existen señales claras de que una aplicación es vulnerable a este antipatrón:
#### **Concatenación de strings:**
El uso excesivo de operadores `+`, `.` o interpolación de variables dentro de cadenas que luego se ejecutan como SQL.
#### **Uso de funciones de escape manuales:**
Intentar "limpiar" la entrada mediante el reemplazo manual de comillas (por ejemplo, `str_replace("'", "''", input)`), lo cual suele ser insuficiente ante técnicas de evasión avanzadas.
#### **Entrada de usuario en identificadores:**
Cuando se permite que el usuario elija nombres de tablas o columnas sin una validación estricta, lo que no puede resolverse con parámetros estándar.