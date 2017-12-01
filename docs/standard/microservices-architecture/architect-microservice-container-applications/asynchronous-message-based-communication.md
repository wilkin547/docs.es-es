---
title: "Comunicación basada en mensajes asíncronos"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Comunicación basada en mensajes asíncronos"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df39771295d12e122edbe27e91cd899e3318e301
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="asynchronous-message-based-communication"></a>Comunicación basada en mensajes asíncronos

Mensajería asincrónica y comunicación orientada a eventos son fundamentales para propagar cambios a través de varios microservicios y sus modelos de dominio relacionadas. Como se mencionó anteriormente en la discusión microservicios y los contextos limitado (BCs), modelos (usuario, cliente, producto, cuenta, etc.) pueden tener diferentes implicaciones para microservicios diferente o BCs. Esto significa que, cuando se producen cambios, se necesita alguna manera para conciliar los cambios a través de los diferentes modelos. Una solución es coherencia definitiva y comunicación orientada a eventos en función de mensajería asíncrona.

Cuando se usa mensajería, los procesos se comunican mediante el intercambio de mensajes de forma asincrónica. Un cliente realiza un comando o una solicitud a un servicio mediante el envío de un mensaje. Si el servicio debe responder, envía un mensaje diferente al cliente. Puesto que es una comunicación basada en mensajes, el cliente supone que la respuesta no se recibirán inmediatamente y que no puede haber ninguna respuesta en absoluto.

Un mensaje está compuesto por un encabezado (metadatos como la información de identificación o seguridad) y un cuerpo. Los mensajes se envían normalmente a través de protocolos asincrónicas como AMQP.

La infraestructura preferida para este tipo de comunicación en la Comunidad de microservicios es un agente de mensaje ligera, que es diferente a los corredores de bolsa grandes y orchestrators utilizados en SOA. Un agente de mensaje ligera, de la infraestructura es normalmente "simple," actúa como un agente de mensajes, con implementaciones sencillas, como RabbitMQ o un bus de servicio escalables en la nube como Azure Service Bus. En este escenario, la mayoría de las ideas "inteligentes" sigue vive en los puntos de conexión que se forma de generar y consumir mensajes, es decir, en la microservicios.

Otra regla que debe intentar seguir, tanto como sea posible, es que se va a usar la mensajería asincrónica solo entre los servicios internos como utilizan la comunicación sincrónica (como HTTP) solo desde las aplicaciones de cliente con los servicios front-end (puertas de enlace de API y el primer nivel de microservicios).

Hay dos tipos de comunicación de mensajería asincrónica: comunicación basada en mensajes de receptor único y comunicación basada en mensajes de varios receptores. En las secciones siguientes se proporcionan detalles acerca de ellos.

## <a name="single-receiver-message-based-communication"></a>Comunicación basada en mensajes de receptor único 

Comunicación asincrónica basada en mensajes con un único receptor significa que no hay comunicación punto a punto que entrega un mensaje exactamente uno de los consumidores que está leyendo en el canal, y que el mensaje se procesa solo una vez. Sin embargo, hay situaciones especiales. Por ejemplo, en un sistema de nube que intenta recuperarse automáticamente de los errores, el mismo mensaje se pudo enviar varias veces. Debido a la red u otros errores, el cliente tiene que volver a intentar el envío de mensajes y el servidor tiene que implementar una operación para ser idempotente para procesar un mensaje concreto de una sola vez.

Comunicación basada en mensajes de receptor único es especialmente idónea para enviar comandos asincrónicos de uno microservicio a otro como se muestra en la figura 4-18 que muestra este enfoque.

Una vez que empezar a enviar la comunicación basada en mensajes (ya sea con comandos o eventos), no debe mezclar la comunicación basada en mensajes con comunicación sincrónica de HTTP.

![](./media/image18.PNG)

**Figura 4-18**. Un único microservicio recibe un mensaje asincrónico

Tenga en cuenta que cuando los comandos proceden de las aplicaciones cliente, puede implementarse como comandos sincrónicos de HTTP. Debe utilizar comandos basada en mensajes cuando necesite una mayor escalabilidad o cuando ya esté en un proceso empresarial basada en mensajes.

## <a name="multiple-receivers-message-based-communication"></a>Comunicación basada en mensajes de varios receptores 

Como un enfoque más flexible, también puede usar un mecanismo de publicación/suscripción para que la comunicación desde el remitente estará disponible para microservicios suscriptor adicionales o para las aplicaciones externas. Por lo tanto, le ayudará a seguir la [abrir/cerrar principio](https://en.wikipedia.org/wiki/Open/closed_principle) en el servicio de envío. De este modo, los suscriptores adicionales pueden agregarse en el futuro sin necesidad de modificar el servicio del remitente.

Si utiliza una comunicación de publicación/suscripción, puede que esté usando una interfaz de bus de eventos a eventos de publicación para los suscriptores.

## <a name="asynchronous-event-driven-communication"></a>Comunicación asincrónica orientada a eventos

Cuando se utiliza la comunicación asincrónica orientada a eventos, un microservicio publica un evento cuando sucede algo dentro de su dominio y otro microservicio debe tener en cuenta que, al igual que un cambio de precio en un microservicio del catálogo de productos de integración. Microservicios adicionales suscriben a los eventos para que puedan recibir de forma asincrónica. Cuando esto ocurre, los receptores pueden actualizar sus propias entidades de dominio, lo que pueden producir más eventos de integración para su publicación. Este sistema de publicación/suscripción normalmente se realiza mediante una implementación de un bus de eventos. El bus de eventos pueden diseñarse como una abstracción o interfaz, pero con la API que es necesario suscribirse o cancelar la suscripción a eventos y para publicar los eventos. El bus de eventos también puede tener uno o más implementaciones en función de cualquier agente entre procesos y mensajería, como una cola de mensajes o un bus de servicio que admite la comunicación asincrónica y un modelo de publicación/suscripción.

Si un sistema utiliza coherencia definitiva controlada por eventos de integración, se recomienda que este enfoque se realizar absolutamente nada para el usuario final. El sistema no debe usar un enfoque que se asemeje a eventos de integración, como SignalR o sistemas de sondeo desde el cliente. El usuario final y el propietario de la empresa tienen explícitamente adoptar coherencia definitiva en el sistema y tenga en cuenta que, en muchos casos la empresa no tiene ningún problema con este enfoque, siempre que sea explícita.

Como se ha indicado anteriormente en la [desafíos y soluciones de administración de datos de distribuida](#challenges-and-solutions-for-distributed-data-management) sección, puede usar eventos de integración para implementar tareas de negocio que abarcan varios microservicios. Por lo tanto, tendrá coherencia definitiva entre dichos servicios. Una transacción coherente se compone de una colección de acciones distribuidas. En cada acción, el microservicio relacionado actualiza una entidad de dominio y publica otro evento de integración que genera la siguiente acción dentro de la misma tarea to-end.

Un punto importante es que puede comunicarse con varios microservicios que están suscrito el mismo evento. Para ello, puede usar la publicación/suscripción de mensajería basado en la comunicación orientada a eventos, como se muestra en la figura 4-19. Este mecanismo de publicación/suscripción no es exclusivo de la arquitectura de microservicio. Es similar a la forma en que [limitado contextos](http://martinfowler.com/bliki/BoundedContext.html) en DDD debe comunicarse o a la forma en que se propagan las actualizaciones de la base de datos de escritura a la base de datos de lectura en el [comando y la segregación de responsabilidad de consulta (CQRS)](http://martinfowler.com/bliki/CQRS.html)patrón de arquitectura. El objetivo es tener la coherencia entre varios orígenes de datos a través de su sistema distribuido.

![](./media/image19.png)

**Figura 4-19**. Comunicación asincrónica de mensajes controlada por eventos

Su implementación determinará qué protocolo que se usará para las comunicaciones orientadas a eventos, basada en mensajes. [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol) puede ayudar a lograr una comunicación en cola confiable.

Al usar un bus de eventos, puede utilizar un nivel de abstracción (por ejemplo, una interfaz de bus de eventos) basado en una implementación en las clases relacionada con código que usa la API de un agente de mensajes como [RabbitMQ](https://www.rabbitmq.com/) o un bus de servicio como [Bus de servicio de azure con temas](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). Como alternativa, puede usar un bus de servicio de nivel superior como NServiceBus, MassTransit o Brighter para articular el bus de eventos y sistema de publicación/suscripción.

## <a name="a-note-about-messaging-technologies-for-production-systems"></a>Una nota sobre la mensajería de tecnologías destinadas a sistemas de producción

Las tecnologías de mensajes disponibles para implementar el bus de eventos abstractos se encuentran en distintos niveles. Por ejemplo, los productos como RabbitMQ (transporte de broker mensajería) y Service Bus de Azure se colocan en un nivel inferior a otros productos, como NServiceBus, MassTransit o Brighter, que puede trabajar en la parte superior RabbitMQ y Service Bus de Azure. La elección depende de cuántas características enriquecidas en el nivel de aplicación y la escalabilidad de cuadro que necesita para la aplicación. Para implementar sólo un bus de eventos de prueba de concepto para su entorno de desarrollo, como lo hemos hecho en el ejemplo eShopOnContainers, una implementación sencilla en la parte superior RabbitMQ que se ejecuta en un contenedor de Docker puede ser suficiente.

Sin embargo, para una importancia decisiva y sistemas de producción que necesitan hyper escalabilidad, es recomendable evaluar el Bus de servicio de Azure. Las características que facilitan el desarrollo de aplicaciones distribuidas y abstracciones de alto nivel, le recomendamos que evalúe otros bus de servicio comercial y de código abierto, como NServiceBus, MassTransit y Brighter. Por supuesto, puede crear sus propias características de bus de servicio sobre tecnologías de nivel inferior como RabbitMQ y Docker. Pero ese trabajo mecánica podría muy costosa para una aplicación de empresa personalizados.

## <a name="resiliently-publishing-to-the-event-bus"></a>Publicación de forma resistente en el bus de eventos

Un desafío al implementar una arquitectura orientada a eventos a través de varios microservicios se muestra cómo actualizar de manera automática el estado en el microservicio original al publicar de forma resistente sus eventos relacionados con la integración en el bus de eventos, en función de algún modo de transacciones. Éstas son algunas maneras para lograr esto, aunque podría haber enfoques adicionales también.

-   Uso de una cola transaccional (basado en DTC) como MSMQ. (Sin embargo, esto es un método heredado).

-   Usar [minería de datos del registro de transacciones](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Usar completa [origen de evento](https://msdn.microsoft.com/en-us/library/dn589792.aspx) patrón.

-   Mediante el [patrón de bandeja de salida](http://gistlabs.com/2014/05/the-outbox/): una tabla de base de datos transaccional como una cola de mensajes que será la base para un componente de creador de eventos que se cree el evento y publicarlo.

Temas adicionales para tener en cuenta al utilizar la comunicación asincrónica son idempotencia de mensaje y la desduplicación de mensaje. En estos temas se tratan en la sección [implementar la comunicación entre microservicios (eventos de integración) basada en eventos](#implementing_event_based_comms_microserv) más adelante en esta guía.

## <a name="additional-resources"></a>Recursos adicionales

-   **Evento controlado por mensajería**
    [*http://soapatterns.org/design\_patrones/evento\_controlada por\_de mensajería*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Canal de publicación/suscripción**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **UDI Dahan. Se ha aclarado CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **Comando y consultar la segregación de responsabilidad (CQRS)**
    [*https://docs.microsoft.com/azure/architecture/patterns/cqrs*](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

-   **Comunicación entre limitado contextos**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)

-   **Coherencia definitiva**
    [*https://en.wikipedia.org/wiki/Eventual\_coherencia*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Jimmy Bogard. Refactorización hacia resistencia: Evaluación de acoplamiento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)


>[!div class="step-by-step"]
[Anterior] (comunicación-en-microservicio-architecture.md) [siguiente] (mantener de microservicio-apis.md)
