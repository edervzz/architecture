1.  Infraestructura Cloud / On-Premise

    - ¿Dónde se desplegará el sistema? AWS, Azure, GCP o servidores físicos.
    - Evaluación de costos: Optimización de instancias, almacenamiento y redes.
    - Monitoreo y observabilidad: ¿Se usarán herramientas como CloudWatch, Prometheus, OpenTelemetry?

2.  Diseño de Redes y Comunicación

    - Configuración de VPCs y subredes para aislar ambientes.
    - Balanceo de carga: ¿Será Nginx, ALB (AWS) o HAProxy?
    - Firewall y reglas de seguridad: ¿Se están aplicando correctamente?

3.  Arquitectura de Contenedores / Despliegue

    - Uso de Docker / Kubernetes para orquestación.
    - Estrategias de despliegue: ¿Blue-Green o Canary Deployment?
    - Automatización CI/CD con GitHub Actions, GitLab CI o AWS CodePipeline.

4.  Seguridad y Autenticación

    - Gestión de identidades: ¿Se usa OAuth 2.0, JWT, o API Keys?
    - Protección de datos: ¿Hay cifrado en tránsito y en reposo?
    - Aplicación de RBAC o ABAC para control granular de permisos.

5.  Bases de datos y almacenamiento

    - Elección del motor: ¿MySQL, PostgreSQL, DynamoDB?
    - Estrategia de caching con Redis o Memcached.
    - Respaldo y recuperación en S3, Aurora o almacenamiento distribuido.

6.  Escalabilidad y rendimiento

    - Pruebas de carga con JMeter o Locust.
    - Uso eficiente de recursos: ¿Se requieren instancias con autoescalado?
    - Optimización de código y bases de datos para evitar cuellos de botella.
