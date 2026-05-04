La solución definitiva se resume en el principio de "No confiar en nadie", tratando toda entrada externa como potencialmente peligrosa.
## Parámetros de consulta (Prepared Statements)

Esta es la técnica más efectiva. Consiste en separar la estructura de la consulta SQL de los datos. Se utiliza un marcador de posición (como `?` o `:name`) que el motor de la base de datos interpreta solo como un valor literal, nunca como código.

- **Proceso:**
    1. Se envía la plantilla de la consulta al servidor.
    2. Se envían los valores por separado.
    3. El servidor combina ambos de forma segura, garantizando que el dato no altere el comando.
## Validación de entrada

Antes de procesar cualquier dato, se debe validar que cumpla con el formato esperado.

- **Tipos de datos:** Asegurarse de que un `id` sea realmente un entero.
- **Listas blancas (Whitelisting):** Si el usuario debe elegir una columna para ordenar (ej. `ORDER BY`), la aplicación debe verificar que la opción esté en una lista predefinida de columnas válidas.

|Método de Validación|Descripción|
|---|---|
|**Filtrado**|Eliminar caracteres peligrosos (insuficiente por sí solo).|
|**Tipado fuerte**|Convertir la entrada al tipo de dato correcto (ej. `int`).|
|**Lista Blanca**|Comparar la entrada contra un conjunto cerrado de valores permitidos.|
## Mapeo de valores dinámicos

Para casos donde se necesiten identificadores dinámicos (tablas o columnas), no se debe usar el string del usuario directamente. En su lugar, se debe usar un mapeo interno:
##### Incorrecto:
``` python
user_table = input("Tabla: ")

query = "SELECT * FROM " + user_table
cursor.execute(query)
```

##### Correcto:
``` python
user_option = input("Elegir tabla (1: clientes, 2: cuentas): ")

table_map = {
    "1": "clientes",
    "2": "cuentas"
}

if user_option in table_map:
    table_name = table_map[user_option]
    query = f"SELECT * FROM {table_name}"
    cursor.execute(query)
else:
    print("Opción inválida")
```

> Al seguir estas soluciones, el desarrollador garantiza que la aplicación cumpla con el objetivo de ser dinámica sin exponer la base de datos a ataques destructivos.