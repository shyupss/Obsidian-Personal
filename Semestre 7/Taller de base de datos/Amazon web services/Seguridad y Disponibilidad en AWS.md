Modelo de Responsabilidad Compartida

1. **Seguridad de la Nube (Responsabilidad de AWS):** Protección de la infraestructura física, redes y servicios gestionados.
2. **Seguridad en la Nube (Responsabilidad del Cliente):** Gestión de parches en aplicaciones, control de acceso (IAM), configuración de subredes en VPC y cifrado de datos.

***Mejores Prácticas de Seguridad en RDS:***
### Cifrado
Utilizar AWS KMS para datos en reposo y SSL/TLS para datos en tránsito.
### Aislamiento de Red
Ejecutar instancias en una **VPC** dentro de subredes privadas, utilizando Grupos de Seguridad para controlar el tráfico.
### Gestión de Accesos
Utilizar **IAM** para la autenticación y asignar permisos mínimos necesarios a los usuarios locales de la base de datos.
### Backup
Configurar backups automáticos (retención de 0 a 35 días) y realizar _snapshots_ manuales antes de cambios críticos.