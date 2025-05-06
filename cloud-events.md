# Cloud Events

Estandar abierto para diseñado para la interoperabilidad de eventos en sistemas distribuido y nube.

Su objetivo es estandarizar como se describen y transportan los eventos entre los sistemas, asegurando que los mensajes sean comprendidos sin importar la plataforma o protocolo de comunicación utilizado.

## Componentes Clave

1. Cabeceras de cloud events

- id: identificador úico del eventos
- source: fuente que genera el evento
- specversion: versión de la especificación que se esta utilizando
- type: tipo de evento a nivel de negocio (order.created)
- time: hora en que ocurrió dicho evento

2. Cuerpo del evento

- Este contiene los datos del eventos, como el detalle de una orden de pago, sin embargo el formato puede variar según el implementador

3. Protocolo de transporte

- http, kafka, amqp, etc

## Ventajas

- La estandarización permite que distintas plataformas puedan ser compatibles, sin problemas de escalabilidad.
- Los eventos no deben preocuparse por quienes los consumen (desacoplamiento).
- Fácil de implementar.
