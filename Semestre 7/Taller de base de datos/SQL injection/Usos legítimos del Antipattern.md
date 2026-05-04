Existen situaciones excepcionales donde se requiere flexibilidad dinámica que los parámetros estándar no cubren. Sin embargo, incluso en estos casos, **la entrada debe ser verificada rigurosamente**.
## Ejemplos:

- **Herramientas de administración:** Aplicaciones diseñadas específicamente para que un administrador escriba SQL directamente (como una consola de base de datos).

- **Identificadores dinámicos:** Cuando el nombre de una tabla o una columna debe cambiar según la lógica (por ejemplo, elegir entre la tabla `Bugs` o `FeatureRequests`), ya que la mayoría de los motores de base de datos no permiten parametrizar nombres de objetos de esquema.