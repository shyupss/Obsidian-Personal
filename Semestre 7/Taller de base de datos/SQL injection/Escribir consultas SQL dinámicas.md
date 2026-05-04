En el desarrollo de aplicaciones modernas, es esencial que las consultas SQL se adapten a las necesidades del usuario en tiempo de ejecución.

El objetivo principal es construir sentencias SQL que incorporen valores proporcionados externamente, como términos de búsqueda, credenciales de inicio de sesión o filtros de visualización.

La necesidad surge cuando el desarrollador intenta hacer que la aplicación sea interactiva.

Por ejemplo, al buscar un bug específico en el sistema de seguimiento por su identificador, la consulta debe ser capaz de insertar ese `id` dinámicamente en la cláusula `WHERE`.