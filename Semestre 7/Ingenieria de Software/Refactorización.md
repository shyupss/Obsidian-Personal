La refactorización se define como una técnica disciplinada para reestructurar un cuerpo de código existente. Su característica fundamental es que altera la **estructura interna** del software sin modificar su **comportamiento externo** u observable.

Esta disciplina se puede entender desde dos perspectivas gramaticales:
- **Como Sustantivo:** Un cambio específico realizado en la estructura interna del software para que sea más fácil de entender y más económico de modificar.
- **Como Verbo:** La acción de reestructurar el software mediante la aplicación de una serie de refactorizaciones sucesivas.

---
# Técnicas de Refactorización

### Rename Variable (Renombrar Variable)
Consiste en cambiar nombres genéricos o crípticos (ej. `let a = height * width;`) por nombres significativos que revelen la intención (ej. `let area = height * width;`). Mejora la legibilidad de inmediato.
### Encapsulate Variable (Encapsular Variable)
Transforma el acceso directo a datos por accesos a través de funciones (Getters/Setters).
- **Antes:** `let defaultOwner = {firstName: "Martin", ...};`
- **Después:** Uso de funciones `defaultOwner()` y `setDefaultOwner(arg)` para gestionar el acceso al dato.
### Combine Functions into Class (Combinar Funciones en Clase)
Se aplica cuando un grupo de funciones opera estrechamente sobre un cuerpo común de datos (usualmente pasados como argumentos).
- **Ventajas:** Hace explícito el entorno común, simplifica las llamadas eliminando argumentos repetitivos y proporciona una referencia clara para pasar el objeto a otras partes del sistema.
### Introduce Parameter Object (Introducir Objeto de Parámetro)
Si varias funciones reciben el mismo grupo de parámetros (ej. `startDate`, `endDate`), estos se agrupan en un solo objeto (ej. `aDateRange`).
### Inline Variable (Variable en Línea)
Si una variable no añade claridad y su nombre solo repite lo que hace la expresión, se elimina la variable y se utiliza la expresión directamente.
### Extract Variable (Extraer Variable)
Es el proceso inverso a _Inline Variable_. Se utiliza para descomponer expresiones complejas en partes nombradas que faciliten la comprensión de la lógica de negocio.

---
# ¿Cuándo Refactorizar?

La refactorización no debe ser una tarea aislada, sino integrada en el flujo de desarrollo mediante los siguientes criterios:
1. **Primera vez:** Simplemente hazlo.
2. **Segunda vez:** Hazlo de nuevo, pero avergüénzate de repetir código.
3. **Tercera vez:** Comienza a refactorizar.
#### Situaciones Clave
- **Al agregar funcionalidad:** Ayuda a comprender código ajeno. El código limpio es más fácil de extender.
- **Al corregir un error:** Los errores suelen esconderse en el código "sucio". Al limpiar el código, los bugs se vuelven evidentes. Además, elimina la necesidad de tareas de refactorización especiales a futuro, lo que genera satisfacción en la gestión de proyectos.
- **Durante una revisión de código:** Es la última oportunidad para ordenar el código antes de su despliegue. Se recomienda realizarlo en pareja para solucionar problemas rápidos y estimar los complejos.

---
# Atributos del Código Limpio (Clean Code)

Un código se considera limpio cuando cumple con las siguientes premisas:
1. **Obviedad:** Es fácil de entender para otros programadores; evita nomenclaturas deficientes o métodos excesivamente extensos.
2. **Sin duplicidad:** Cada cambio debe realizarse en un solo lugar. La duplicidad aumenta la carga cognitiva.
3. **Minimalismo:** Contiene el número mínimo de clases y partes móviles. Menos código es menos responsabilidad.
4. **Efectividad de Pruebas:** Pasa todas las pruebas. Un código con 95% de éxito en pruebas se considera sucio; un 0% de cobertura se considera una situación crítica.
5. **Costo:** Es más fácil y barato de mantener.

---
# Olores de Código (Code Smells)

Los "olores de código" son indicadores de que el software requiere refactorización. No son errores por sí mismos, sino síntomas de problemas de diseño.
### Bloaters (Inflados)
> Métodos y clases que han crecido hasta proporciones gigantescas. No suelen aparecer de inmediato, sino que se acumulan con el tiempo si no hay esfuerzo por erradicarlos.
### Object-Orientation Abusers (Abusadores de la Orientación a Objetos)
> Surgen por la aplicación incorrecta o incompleta de los principios de la programación orientada a objetos (POO).
- _Ejemplo:_ No usar polimorfismo y depender de múltiples sentencias `if (animal instanceof Gato)`. La solución suele ser extraer métodos a clases abstractas y usar `@Override`.
### Change Preventers (Inhibidores de Cambio)
> Ocurre cuando un cambio simple en un lugar del código obliga a realizar múltiples modificaciones en otros lugares, encareciendo el desarrollo.
### Dispensables (Desechables)
> Código innecesario cuya ausencia mejoraría la eficiencia y claridad.
- **Dead Code (Código Muerto):** Variables que nunca se usan, código después de una sentencia `return`, o bloques `if(false)` que jamás se ejecutan.
### Couplers (Acopladores)
> Indican un acoplamiento excesivo entre clases o el uso de delegación innecesaria.
- **Middle Man (Intermediario):** Una clase que solo delega trabajo a otra. Si la clase solo sirve como puente sin añadir valor, debe eliminarse obligando al cliente a llamar directamente al objeto final.