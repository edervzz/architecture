# Arquitectura de Software

[Topicos]() | [Acerca de mí](/me.md)

## Topicos

- [Equipos de trabajo](/teams.md)
- [Architecture Decision Records](/adr.md)

## Que actividades realiza un Arquitecto de Software

- Diseño de la infraestructura (servidores, almacenamiento, on-prem, cloud)
- Familiarizado con requerimientos
- Plan de carrera enfocado en cloud, infraestructura y seguridad

Un arquitecto sabe lo que se debe hacer, por ende esta familiarizado con el desarrollo aunque no es su principal objetivo.

Se asegura de que el diseño del software implementa los requisitos del sistema.

Prepara POCs, revisa librerias, DB, patrones y tendencias.

## Un arquitecto, vela por una misión

Todo sistema diseñado por el arquitecto debe cumplir 4 aspectos:

- Fast
- Secure
- Reliable
- Easy to Maintain

## Mindset, _entender las necesidades del negocio_

- Siempre tratar de entender las partes internas del negocio
- Que le quita el sueño al usuario
- Puntos debiles y fuertes
- Con quien compiten
- Cual es la estrategia de crecimiento

## Proceso de Arquitectura

1. Entender los requerimientos del Sistema
2. Entender los requerimientos no funcionales del Sistema
   - Atributos de calidad
     - Escalabilidad: Scale up (cpu, mem), Scale out (vm, load-balancers, redundancia)
     - Manejabilidad: que pasa dentro del sistema (Monitoreo)
     - Modularidad: piezas moviles, bloques pequeños que suman un todo
     - Extensibilidad: ampliar funcionalidad
     - Testeabilidad: tipos de testing (manual, unitaria, integración)
3. Mapear los Componentes
4. Seleccionar el Stack tecnológico
5. Diseñar la arquitectura
6. Escribir documento de arquitectura
7. Apoyo al equipo

**Diseñar la solución basada en un alcance real, no siempre más es mejor**

**Cual es el efecto que tendrá el sistema en el cliente de tu cliente**

## Dependiendo de con quien se hable es el lenguaje

Es sumamente importante que el arquitecto hable el lenguaje adecuado con la persona adecuada.

- PM: Que ventajas tiene hacerlo de esta forma
- Dev lead: Que y como lo construimos
- Director: Que resuelve, que aporta esta solución
