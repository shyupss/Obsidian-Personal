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

La parte de un LMD que implica **recuperación** de información se llama **lenguaje de *consultas***. 

Aunque técnicamente sea incorrecto, ***en la práctica se usan los términos lenguaje de consultas y lenguaje de manipulación de datos como sinónimos.***