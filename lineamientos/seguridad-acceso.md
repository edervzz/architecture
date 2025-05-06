# 2. Seguridad y Control de acceso

Uso de OAuth 2.0, JWT o API Keys según el caso.

Implementación de RBAC o ABAC para control granular.

## Autenticación

| Método    | Uso                                                                                                                     | Seguridad    |
| --------- | ----------------------------------------------------------------------------------------------------------------------- | ------------ |
| OAuth 2.0 | Aplicaciones donde los usuarios necesitan </br> conectarse a sistemas sin exponer credenciales,                         | Alta         |
| JWT       | Autenticación de APIs para sesiones sin estado, validación de usuarios rápida                                           | Media / Alta |
| API Keys  | Autorización entre servidores donde no hay intervesión directa de usuarios finales </br> Considerar restricciones de IP | Baja         |

## Autorización

Definir la seguridad basado en control y flexiblidad

### RBAC (Role-Based Access Control): para aplicaciones con estructuras claras y permisos predefinidos

_Baja flexibilidad, fácil administración, escalabilidad limitada_

- Definición de Roles
- Asignación de Permisos a Rol
- Asociación de Roles a Usuarios

Ej. Roles Admin, Manager, User para el manejo del sistema. Nuevos equipos podrian implicar nuevos roles.

### ABAC (Attribute-Based Access Control): para aplicaciones dinámicas con reglas más precisas y contexto variable.

_Alta flexibilidad, administración compleja, alta escalabilidad_

- Definir atributros relevantes
- Creación de reglas basadas en atributos
- Implementar evaluación de politicas (OPA)

Ej. Acceso al sistema solo si se trabaja en horario laboral y/o desde una IP dentro de la empresa.

## Datos Sensibles
