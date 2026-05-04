MySQL emplea tres métodos principales para acceder a los datos, ordenados de mayor a menor eficiencia:
# Búsqueda por Índice (Index Lookup)

Es el método más rápido y el objetivo de la optimización de consultas.

Utiliza la estructura ordenada del índice y el acceso algorítmico para encontrar filas específicas o rangos de filas.

> ***Es esencial para el rendimiento, y prácticamente todas las consultas deberían aspirar a utilizar este método.***
# Escaneo de Índice (Index Scan)

Ocurre cuando no es posible realizar una búsqueda por índice, pero MySQL decide que es más barato leer un índice secundario completo que la tabla entera.

- Se lee el índice de principio a fin.

> Sigue siendo una forma de "fuerza bruta", aunque sobre una estructura más pequeña que la tabla completa.
# Escaneo de Tabla (Table Scan)

Es el método de acceso por fuerza bruta definitivo.

- MySQL lee cada fila de la tabla utilizando la clave primaria para encontrar las que coinciden con los criterios de la consulta.

> ***Generalmente es perjudicial para el rendimiento y suele indicar que la consulta no está utilizando un índice adecuado. Se recomienda encarecidamente optimizar las consultas que resulten en escaneos de tabla.***