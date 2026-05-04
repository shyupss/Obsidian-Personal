El **LDD** se usa para **definir la estructura de la base de datos**.

Es decir, sirve para:
- crear tablas
- definir atributos
- establecer tipos de datos

***Ejemplo:***
``` sql
CREATE TABLE cuenta (
  numero_cuenta CHAR(10),
  saldo INTEGER
);
```
*La ejecución de esta instrucción crea la tabla cuenta. Además, actualiza un conjunto especial de tablas denominado **diccionario de datos** o **directorio de datos.***

### Diccionario de datos

El **diccionario de datos** es una base de datos interna del SGBD que almacena **metadatos**, es decir, datos acerca de los datos.

El esquema de una tabla es un ejemplo de metadatos.

Un sistema de base de datos ***consulta el diccionario de datos antes de leer o modificar*** los datos reales.