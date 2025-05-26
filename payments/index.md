# Importación y tratamientos de pagos

## Estatus

Propuesta

## Fecha

2025-05-26

## Contexto

El core COBIS tiene la capacidad de importación de pagos masivos através de archivos según su layout. Sin embargo, aquellos que no puedan ser reconocidos no pueden redireccionarse a una cuenta de _suspernso_ hasta no averguar los dueñós de los pagos, en su lugar los registro de los pagos que no fueron reconocidos se mandan a un archivo de salida con el detalle. _El modelo de redireccionamiento, se toma de SAP Banking - Posting Control Office._

Como principal consideración, cada canal maneja un layout especifico que no va a ser identico al archivo requerido por el core, entonces se tiene que realizar una lectura → transformación → enriquecimiento → carga, para su tratamiento en el core.

No olvidar que el core tiene a nuestra disposición APIs para aplicación de pagos individuales y consulta de cuentas.

## Decisión

Un posible solución (de tres) es crear un sistema que lea los archivos de los canales, interprete y cargue en su propia BBDD. Luego comenzar disparar la aplicación de pagos al core. Aquellos pagos que no hayan sido aplicados derivado de algun error operativo, por ejemplo: cuenta cerrada o no reconocida, se redireccionarán (derivación) hacia una cuenta operativa denominada _"cuenta de suspenso"_. Finalmente cada registro procesado deberá dejar su estado final (APLICADO / DERIVADO).

Como opción y dependiendo del discovery de APIs del core, se buscará que luego de que un pago fue redireccionado y transferido a la cuenta correcta, se mande el detalle a este nuevo sistema para cerrar la trazabilidad. En caso de que el core no cuente con hooks o una forma viable de notificar, se delegará todo el detalle traspaso al core.

## Consecuencias

- 🟢El 100% de pagos queda dentro del core

- 🟢Contabilidad dentro del core

- 🟡Carga, transformación y gestión (hasta entrega completa por archivo) dentro de nuevo sistema

- 🟡Requiere procesos de conciiación contra el core.

### Siguientes pasos

Confirmar el alcance de las APIs del core. Revisar con el equipo de arquitectura la viabilidad de las opciones descritas.

## Alternatives

1. Mantener los pagos dentro del core en una cuenta de suspenso.

- 🟢**Contabilidad integrada**: Al quedarse dentro del core, los pagos no procesados ya estarían registrados en la contabilidad, lo que facilita el seguimiento y la conciliación. La caida contable se maneja de forma directa.

- 🟢**Transparencia**: Todo el procesamiento de los pagos exitosos y fallidos, quedan registrados en el core, lo que mejora la trazabilidad y visibilidad.

- 🟡**Dependencia del core**: El sistema podría volverse más complejo si el core no está diseñado para manejar estos pagos pendientes de una manera eficiente. (Pendiente de confirmar)

- 🟡**Gestión de pagos**: Se require un trabajo adicional para gestionar los pagos que deben devolverse a los canales emisor.

2. Gestionar los pagos no reconocidos en una aplicación externa.

- 🟢**Flexibilidad**: Diseñar la aplicación según las necesidades para gestionar los pagos no reconocidos, permitiendo un proceso más ágil y adaptado a los requerimientos de negocio.

- 🟢**Separación de responsabilidades**: Manejar los pagos fuera del core, minimiza el impacto en el core y se tiene mejor control sobre registros fallidos, mejorando la eficiencia operativa.

- 🔴**Contabilidad externa**: Esfuerzo adicional para asegurar que los pagos gestionados externamente sean reflejados en los reportes contables. Esto podría requerir integraciones adicionales y aumentar la complejidad en la generación de informes.

- 🔴**Riesgo de desconexión**: Mantener los pagos en una herramienta externa podría generar un desfase entre el core y la aplicación externa, lo que podría dificultar el control total de las transacciones si no se gestionan correctamente las integraciones.

3. Captura manual de pagos no renocidos.

- 🔴**Error humano y volumen**: Manejar el archivo de pagos no reconocidos de forma manual implicaria errores de captura de demasiado esfuerzo por parte del equipo de operaciones.

## References

Se estiman mas de 300,000 pagos no reconocidos diarios.
