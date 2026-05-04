Cuando MySQL utiliza un índice secundario para encontrar una fila, realiza un proceso de dos pasos:

1. **Búsqueda en el índice secundario:** Se recorre el árbol B-tree del índice secundario desde la raíz, pasando por los nodos internos hasta llegar al nodo hoja que contiene el valor buscado y su respectiva clave primaria.

2. **Búsqueda en la clave primaria (Look up):** Con el valor de la clave primaria obtenido, MySQL realiza una segunda búsqueda en el índice agrupado para extraer la fila completa con todas sus columnas.

> ***Este proceso subraya por qué la clave primaria es fundamental para el rendimiento: cada búsqueda en un índice secundario termina en una búsqueda por clave primaria.***