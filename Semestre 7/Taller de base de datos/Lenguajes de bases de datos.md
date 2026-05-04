Un sistema de bases de datos proporciona un ***lenguaje de definición de datos*** para especificar el esquema de la base de datos y un ***lenguaje de manipulación de datos*** para expresar las consultas a la base de datos y las modificaciones.

En la práctica, ***los lenguajes de definición y manipulación de datos NO son dos lenguajes separados***; en su lugar simplemente forman partes de un único lenguaje de bases de datos, tal como SQL, ampliamente usado.

---
# Lenguaje de definición de datos (LDD)

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

---
# Lenguaje de manipulación de datos (LMD)

El **LMD** se usa para **trabajar con los datos ya almacenados**.

Permite:
- consultar datos (SELECT)
- insertar datos (INSERT)
- borrar datos (DELETE)
- modificar datos (UPDATE)

LMDs los hay dos tipos:
- ***LMDs procedimentales.***: Requieren que el usuario especifique qué datos se necesitan y cómo obtener esos datos.
```pseudo
\begin{algorithm}
\begin{algorithmic}
  \Procedure{ObtenerClientesConSaldoAlto}{}
    \State abrir archivo clientes
    \While{no fin de archivo}
        \State leer registro cliente
        \If{cliente.saldo > 1000}
            \State imprimir cliente.nombre
        \EndIf
    \EndWhile
    \State cerrar archivo clientes
  \EndProcedure
\end{algorithmic}
\end{algorithm}
```
- ***LMDs declarativos:*** (también conocidos como **LMDs no procedimentales**). Requieren que el usuario especifique qué datos se necesitan sin especificar cómo obtener esos datos.
``` sql
	SELECT nombre FROM clientes;
```

*El componente LMD del lenguaje SQL es no procedimental*

---

Una **consulta** es una instrucción de solicitud para recuperar información.

La parte de un LMD que implica **recuperación** de información se llama **lenguaje de consultas**. 

Aunque técnicamente sea incorrecto, ***en la práctica se usan los términos lenguaje de consultas y lenguaje de manipulación de datos como sinónimos.***