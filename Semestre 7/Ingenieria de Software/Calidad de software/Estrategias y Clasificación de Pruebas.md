Para comprender las estrategias de prueba, se utiliza una analogía con la clasificación del **Reino Animal**. Así como los animales se categorizan según su forma de nacer (ovíparos, vivíparos), su alimentación (herbívoros, carnívoros, omnívoros) o el medio en que viven (terrestres, acuáticos), las pruebas de software se clasifican bajo cinco ejes fundamentales:

1. **Según la Accesibilidad**
2. **Según la Ejecución**
3. **Según el Método**
4. **Según el Alcance**
5. **Según el Nivel**

*Esta taxonomía permite al ingeniero seleccionar la estrategia adecuada dependiendo del objetivo de calidad y la fase del ciclo de vida del desarrollo.*

---
# 1. Clasificación según la Accesibilidad

Esta categoría se define por el grado de conocimiento que el evaluador posee sobre la estructura interna y la implementación del código del software bajo prueba.
### 1.1 Black Box Testing (Caja Negra)

Es un método donde se prueban las funcionalidades sin conocimiento alguno de la estructura interna del código, detalles de implementación o rutas internas. Se basa exclusivamente en los requisitos y especificaciones del software, por lo que también se denomina **pruebas de comportamiento**.

|Aspecto|Detalles|
|---|---|
|**Enfoque**|Entrada (Input) y Salida (Output).|
|**Ventajas**|No requiere conocimientos técnicos; el probador piensa como el usuario; desarrolladores y probadores trabajan de forma independiente; eficaz en sistemas complejos; detecta inconsistencias tempranas.|
|**Desventajas**|Posibilidad de ignorar escenarios técnicos críticos; la cobertura total es imposible en proyectos grandes.|

- **Ejemplos de técnicas:**
    - **Equivalence Class Partitioning (ECP):** División de datos de entrada en clases válidas e inválidas (ej. un campo que acepta edades de 18-60 clasifica como inválido <17 y >61).
    - **State Transition Testing:** Verificación de cambios de estado (ej. un sistema de logueo que bloquea la cuenta tras tres intentos fallidos).

### 1.2 White Box Testing (Caja Blanca)

Evalúa la estructura interna, el diseño y la codificación para verificar el flujo de entrada-salida y mejorar seguridad y usabilidad. El código es totalmente visible para el evaluador, por lo que se conoce como prueba de **caja transparente, de cristal o basada en código**.

**Elementos verificados:**
- Brechas de seguridad interna.
- Rutas rotas o mal estructuradas.
- Flujo de entradas específicas a través del código y resultados esperados.
- Funcionalidad de bucles condicionales.
- Instrucciones, objetos y funciones de forma individual.

| Aspecto         | Detalles                                                                                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Ventajas**    | Optimización del código y hallazgo de errores ocultos; fácil automatización; cobertura exhaustiva de rutas; inicio temprano en el SDLC (incluso sin GUI).                                                          |
| **Desventajas** | Alta complejidad y costo; requiere recursos profesionales con alto conocimiento en programación; toma mucho tiempo; si la realizan los desarrolladores, pueden omitirse detalles que causen errores en producción. |
### 1.3 Grey Box Testing (Caja Gris)

Técnica híbrida donde se tiene un **conocimiento parcial** de la estructura interna. El propósito es identificar defectos debidos a estructuras de código incorrectas o uso indebido de aplicaciones.

- **Ejemplo:** Probar una aplicación móvil de pedidos ("My Order"). El evaluador ve la interfaz (Caja Negra) pero también tiene acceso a realizar consultas SQL (Caja Blanca) para verificar que el monto total mostrado en la aplicación ($298) coincida exactamente con el registro en la base de datos de órdenes.

---
# 2. Clasificación según la Ejecución

Se refiere al modo en que los casos de prueba son procesados, ya sea por intervención humana o mediante software especializado.
#### 2.1 Pruebas Automatizadas
Consisten en el uso de herramientas especiales para ejecutar conjuntos de casos de prueba. Es la aplicación de software para automatizar procesos manuales humanos de revisión y validación. Son fundamentales en proyectos modernos bajo marcos de trabajo **Ágil y DevOps** desde su inicio.
#### 2.2 Pruebas Manuales
Los casos de prueba son ejecutados por un evaluador humano sin herramientas automatizadas. Es la técnica más primitiva pero esencial para encontrar errores críticos y problemas de usabilidad que una máquina podría no detectar.
#### 2.3 Pruebas Semiautomáticas
Combinan pasos automáticos con interacción manual necesaria.

- **Motivaciones:** Resolver un CAPTCHA antes de iniciar una prueba automatizada; automatizar partes estables del sistema mientras se mantienen manuales las partes que cambian frecuentemente (como una GUI en desarrollo).
- **Enfoque:** Existen técnicas para abstraer las partes no automatizadas, permitiendo una transición fluida entre la ejecución del bot y la intervención del evaluador.

---
# 3. Clasificación según el método

Se refiere a la distinción entre aquellas actividades de verificación que requieren ejecutar el programa y aquellas que no.
### 3.1 Pruebas Estáticas (Static Testing)
Estas pruebas se caracterizan por realizarse **sin ejecutar el software**.

- **Objetivo:** Revisar productos de trabajo para la **prevención de defectos** y su detección temprana.
- **Elementos revisados:** Incluyen documentos de requerimientos, casos de prueba, planes de prueba, el código fuente y guías de usuario.
- **Ejecución:** Se pueden realizar mediante **revisión manual** o **revisión automática del código** en cualquier etapa del ciclo de vida del software.
- **Qué detectan:** Son útiles para identificar vulnerabilidades, código duplicado o muerto, incumplimiento de estándares de codificación y alta complejidad ciclomática.
### 3.2 Pruebas Dinámicas (Dynamic Testing)
A diferencia de las anteriores, estas pruebas se realizan **mientras el código está en ejecución**.

- **Objetivo:** Asegurar que el comportamiento del software coincida con los **requerimientos del negocio** mediante pruebas funcionales y no funcionales.
- **Enfoque:** Se centran en la detección de fallos y en confirmar que los defectos previamente encontrados han sido corregidos.
- **Costo y tiempo:** Por lo general, se llevan a cabo en etapas más tardías que las pruebas estáticas, lo que implica que los defectos encontrados en esta fase suelen ser **más costosos** de reparar.

---
# 4. Clasificación según el Alcance

> El alcance divide las pruebas principalmente en dos categorías: Funcionales y No Funcionales.
## 4.1 Pruebas Funcionales
Se centran en el "qué" hace el sistema, validando que las funciones operen según los requisitos.
#### **UAT (User Acceptance Testing):**
Son pruebas de aceptación realizadas por el usuario final o el cliente. Su objetivo es verificar y aceptar el sistema antes de su paso al entorno de producción. Se ejecutan en la fase final, tras completar las pruebas unitarias, de integración y de sistema.
#### **Pruebas Exploratorias:**
Evaluación basada en el aprendizaje del producto a través de la exploración y experimentación activa. Involucra procesos de cuestionamiento, modelado, observación e inferencia por parte del tester.
#### **Pruebas de Humo (Smoke Testing):**
Proceso para determinar si la compilación del software es estable. Es un conjunto mínimo de pruebas ejecutadas en cada compilación para confirmar que las funcionalidades básicas operan y que el equipo de QA puede proceder con pruebas más rigurosas. 
_Ejemplo: Verificar que todas las páginas del menú cargan tras un despliegue._
#### **Pruebas de Sanidad (Sanity Testing):**
Se realizan tras recibir una compilación con cambios menores o correcciones de errores. Su objetivo es determinar que la funcionalidad propuesta no presenta errores fácilmente verificables y que los cambios no introdujeron nuevos problemas.
Si falla, se rechaza la compilación para ahorrar costos.
_Ejemplo: Verificar que, tras un cambio en el manejo de stock, no se muestren productos con stock cero._
#### **Pruebas de Regresión:**
También llamadas de "no impacto", confirman de si un cambio reciente en el código no ha afectado negativamente a las funciones existentes. Se vuelven a ejecutar casos de prueba previos para asegurar que la funcionalidad anterior sigue operando correctamente.
_Ejemplo: Validar que el proceso de ventas sigue funcionando tras agregar un nuevo módulo de estadísticas_

## 4.2 Pruebas No Funcionales (de rendimiento)

> Evalúan atributos como la velocidad, estabilidad y uso de recursos bajo carga. No buscan errores funcionales, sino "cuellos de botella".

La importancia de estas pruebas se refleja en datos económicos: se estima que una interrupción en Amazon Web Services puede costar 1,100 dólares por segundo.

- **Carga:** Determinan el comportamiento del software bajo condiciones de carga basadas en la vida real (variables). Identifican el número máximo de usuarios o transacciones que el sistema soporta. _Ejemplo: Probar el sistema con 10,000 usuarios concurrentes._
- **Estrés:** Miden la robustez y capacidad de manejo de errores en condiciones extremadamente pesadas, buscando el "punto de ruptura" del sistema (software o hardware) para garantizar que no se bloquee en situaciones de crisis.
- **Spike:** Evalúan la reacción del software ante picos repentinos y extremos de carga en intervalos de tiempo muy cortos. _Ejemplo: El inicio de venta de entradas para un concierto a una hora específica._
- **Resistencia:** Aseguran que el sistema pueda manejar la carga esperada durante periodos de tiempo prolongados. _Ejemplo: El acceso continuo de estudiantes a una plataforma de exámenes nacionales durante una semana completa._
- **Volumen:** Determinan el comportamiento del sistema ante grandes registros de datos en la base de datos. _Ejemplo: Evaluar cómo responde un sistema al pasar de 14 millones a 140 millones de usuarios._
- **Escalabilidad:** Miden la eficacia del software para "escalar" y admitir un aumento de carga. Ayuda a planificar la adición de capacidad. _Ejemplo: Verificar que el software escala progresivamente para soportar un aumento del 400% en ventas navideñas_
- **Compatibilidad:** Evalúan el funcionamiento en distintos dispositivos, sistemas operativos (Ubuntu, CentOS) y navegadores (Chrome, Opera), considerando variables de red.
- **Seguridad:** Identifican vulnerabilidades, amenazas y riesgos para evitar ataques maliciosos o pérdida de información y reputación.
- **Usabilidad:** Enfocadas en la Experiencia de Usuario (UX). Involucran estudios donde moderadores observan a usuarios reales completar tareas para identificar problemas de confusión o éxito.

---
# 5. Clasificación según el Nivel

Esta clasificación sigue una estructura piramidal, desde los componentes más pequeños hasta la aceptación final.
#### **Nivel 1 - Pruebas Unitarias:**
Prueban unidades individuales (módulos, funciones, métodos) para garantizar su corrección. Son pruebas de bajo nivel, generalmente automatizadas y escritas por desarrolladores durante la codificación. _Ejemplo: Probar un método de escritura de archivos ante diferentes estados del archivo (vacío, con contenido, inexistente)._
#### **Nivel 2 - Pruebas de Integración:**
Evalúan cómo los módulos de software, a menudo creados por diferentes equipos, interactúan entre sí. Se centran en la comunicación de datos entre módulos. _Ejemplo: Probar un endpoint de API y su capacidad de guardar datos en la BD._
#### **Nivel 3 - Pruebas de Sistema (End-to-End):**
Prueban la aplicación integrada como un todo en un entorno similar al de producción. Su fin es verificar que el sistema se ajusta a los requisitos comerciales globales.
#### **Nivel 4 - Pruebas de Aceptación:**
Nivel final antes del lanzamiento a producción. Garantizan que el producto cumple con los estándares de calidad y requisitos comerciales.
    - **Prueba Alfa:** Realizada por testers o empleados internos en el sitio del desarrollador.
    - **Prueba Beta:** Realizada por usuarios finales en su propio entorno.

---
# Otras Clasificaciones y Técnicas

Existen enfoques adicionales que complementan las estrategias anteriores:

- **Pruebas A/B:** Enfoque estadístico que compara dos versiones de un sistema. Se despliega una nueva funcionalidad a un grupo limitado y, si los resultados son superiores, se despliega a todos.
- **Accesibilidad:** Grado en que el sistema puede ser usado por personas con diversas capacidades y características físicas o cognitivas.
- **Internacionalización y Localización:** Adaptación del software a diferentes idiomas y contextos regionales.
- **Pruebas Destructivas:** Intentan causar fallos incontrolados para probar la robustez y establecer los límites de estabilidad operativa del software.