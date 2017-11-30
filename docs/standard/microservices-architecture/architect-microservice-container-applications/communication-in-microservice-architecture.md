---
title: "Comunicación en una arquitectura de microservicio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Comunicación en las arquitecturas de arquitectura de microservicio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 8d38095a151b7568619b17340d768eff684d3271
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="communication-in-a-microservice-architecture"></a>Comunicación en una arquitectura de microservicio

En una aplicación monolítica se ejecuta en un único proceso, componentes invocación entre sí mediante llamadas de función o método de nivel de lenguaje. Estos pueden ser estrechamente si va a crear objetos con el código (por ejemplo, `new ClassName()`), o puede invocar de forma desacoplada si usas la inyección de dependencia haciendo referencia a abstracciones en lugar de instancias de objeto concreta. En cualquier caso, los objetos se están ejecutando en el mismo proceso. El desafío más importante cuando se cambia de una aplicación a una aplicación basada en microservicios monolítica consiste en cambiar el mecanismo de comunicación. Una conversión directa de las llamadas a métodos en proceso en llamadas a RPC a los servicios hará que una locuaz y una comunicación eficaz no que no se realizará correctamente en entornos distribuidos. Los desafíos de diseñar el sistema distribuido correctamente lo suficientemente bien como se sabe que incluso es un canon conocido como el [la fallacies de computación distribuida](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) que muestra suposiciones que los desarrolladores a menudo cuando se mueven desde monolítico a diseños distribuidos.

No hay no una solución, pero varios. Una solución implica aislar el microservicios de negocios tanto como sea posible. A continuación, utilizan la comunicación asincrónica entre el microservicios interno y reemplace comunicación específica que es típica de comunicaciones dentro de un proceso entre los objetos con la comunicación general. Puede hacerlo mediante la agrupación de llamadas y devolviendo los datos que agrega los resultados de varias llamadas internas, al cliente.

Una aplicación basada en microservicios es un sistema distribuido que se ejecutan en varios procesos o servicios, normalmente incluso en varios servidores o hosts. Normalmente, cada instancia de servicio es un proceso. Por lo tanto, los servicios deben interactúan mediante un protocolo de comunicación entre procesos, como HTTP, AMQP o un protocolo binario como TCP, dependiendo de la naturaleza de cada servicio.

La Comunidad de microservicio fomenta la filosofía de "[inteligentes extremos y canalizaciones no inteligente](http://simplicable.com/new/smart-endpoints-and-dumb-pipes)." Este eslogan anima a un diseño que sea lo más desacoplada como sea posible entre microservicios y productiva como posible dentro de un único microservicio. Como se explicó anteriormente, cada microservicio posee sus propios datos y su propia lógica de dominio. Pero normalmente simplemente se choreographed la microservicios crear una aplicación de extremo a extremo mediante el uso de las comunicaciones de REST, en lugar de protocolos complejos, como WS -\* y centralizada de comunicaciones flexibles orientada a eventos en lugar de proceso orchestrators empresarial.

Los dos protocolos usados son solicitud/respuesta HTTP con el recurso de API (al consultar la mayoría de todos) y mensajería asincrónica ligera al comunicarse las actualizaciones a través de varios microservicios. Estos se explican con más detalle en las secciones siguientes.

## <a name="communication-types"></a>Tipos de comunicación

Cliente y servicios pueden comunicarse a través de muchos tipos diferentes de comunicación, cada uno destinado a un escenario diferente y objetivos. Inicialmente, los tipos de comunicaciones se pueden clasificar en dos ejes.

El primer eje consiste en definir si el protocolo es sincrónico o asincrónico:

-   Protocolo sincrónico. HTTP es un protocolo sincrónico. El cliente envía una solicitud y espera una respuesta del servicio. Que es independiente de la ejecución de código de cliente que podría ser sincrónica (el subproceso está bloqueado) o asincrónico (no se bloquea el subproceso, y la respuesta de llegar a una devolución de llamada al final). La cuestión importante aquí es que el protocolo (HTTP/HTTPS) es sincrónico y el código de cliente solo puede continuar su tarea cuando recibe la respuesta del servidor HTTP.

-   Protocolo asincrónico. Otros protocolos como AMQP (es decir, un protocolo compatible con muchos sistemas operativos y entornos de nube) usan mensajes asincrónicos. Normalmente el remitente de mensaje o código de cliente no espera una respuesta. Simplemente envía el mensaje como al enviar un mensaje a una cola de RabbitMQ o cualquier otro agente de mensajes.

El segundo eje consiste en definir si la comunicación tiene un único receptor o receptores varios:

-   Receptor único. Cada solicitud debe ser procesado por exactamente un receptor o servicio. Un ejemplo de este tipo de comunicación es la [patrón comandos](https://en.wikipedia.org/wiki/Command_pattern).

-   Varios receptores. Cada solicitud puede ser procesado por cero a varios receptores. Este tipo de comunicación debe ser asincrónica. Un ejemplo es el [de publicación/suscripción](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) mecanismo utilizado para los patrones similares a [arquitectura orientada a eventos](http://microservices.io/patterns/data/event-driven-architecture.html). Esto se basa en un agente de interfaz o un mensaje de bus de eventos para propagar las actualizaciones de datos entre varios microservicios a través de eventos; Normalmente se implementa a través de un bus de servicio ni ningún artefacto similar como [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) utilizando [temas y suscripciones](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).

Una aplicación basada en microservicio a menudo utilizará una combinación de estos estilos de comunicación. El tipo más común es el único receptor comunicación con un protocolo sincrónico como HTTP/HTTPS al invocar un servicio Web API HTTP normal. Normalmente, también se Microservicios usar protocolos de mensajería para la comunicación asincrónica entre microservicios.

Estos ejes son buenos conocer para tener mayor claridad en los mecanismos de comunicación posible, pero no son las preocupaciones más importantes al compilar microservicios. La naturaleza asincrónica de ejecución de subprocesos de cliente ni siquiera la naturaleza asincrónica del protocolo seleccionado son los puntos son importantes cuando se integra microservicios. ¿Qué *es* importante es poder integrar su microservicios asincrónicamente manteniendo la independencia del microservicios, tal como se describe en la sección siguiente.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>Integración de microservicio asincrónica aplica autonomía de microservicio

Como se ha mencionado, el punto importante al compilar una aplicación basada en microservicios es la forma de integrar su microservicios. Idealmente, debe intentar minimizar la comunicación entre el microservicios interno. El menos las comunicaciones entre microservicios, mejor. Pero, por supuesto, en muchos casos tendrá que integrar la microservicios de algún modo. Si necesita hacerlo, la regla fundamental aquí es que la comunicación entre el microservicios debe ser asincrónica. Que no significa que se debe usar un protocolo específico (por ejemplo, mensajería asincrónica frente a HTTP sincrónico). Simplemente significa que la comunicación entre microservicios debe realizarse solo mediante la propagación datos de forma asincrónica, pero no intenta dependen de otros microservicios interno como parte de la operación de solicitud/respuesta HTTP del servicio inicial.

Si es posible, nunca dependen de comunicación sincrónica (solicitud-respuesta) entre varios microservicios, ni siquiera para las consultas. El objetivo de cada microservicio es son autónomos y están disponibles para el consumidor de cliente, aunque los demás servicios que forman parte de la aplicación de extremo a extremo están inactivo o mal estado. Si cree que necesita realizar una llamada desde un microservicio a otros microservicios (por ejemplo, realizando una solicitud HTTP para una consulta de datos) en orden para que pueda proporcionar una respuesta a una aplicación cliente, tiene una arquitectura que no será resistente cuando algunos microservicios producirá un error.

Además, si tiene dependencias HTTP entre microservicios, al igual que al crear largos ciclos de solicitud/respuesta con HTTP solicitan cadenas, como se muestra en la primera parte de la figura 4-15, no solo convierte su microservicios no autónomos, sino también su rendimiento afectados tan pronto como uno de los servicios en dicha cadena no esté funcionando correctamente. 

Más agregar dependencias sincrónicas entre microservicios, por ejemplo, las solicitudes de consulta, el peor que obtiene el tiempo de respuesta total para las aplicaciones cliente.

![](./media/image15.png)

**Figura 4-15**. Antipatrones y patrones de comunicación entre microservicios

Si es necesario generar una acción adicional en otro microservicio su microservicio, si es posible, no realizar esa acción como parte de la operación de solicitud y respuesta de microservicio original y de forma sincrónica. En su lugar, hacerlo de forma asincrónica (mediante mensajería asincrónica o eventos de integración, colas, etcetera.). Sin embargo, cuando sea posible, no invocan la acción de forma sincrónica como parte de la operación de solicitud y respuesta sincrónica original.

Y, finalmente, (y es donde la mayoría de los problemas surgen al generar microservicios), si la microservicio inicial necesita que los datos que originalmente pertenece a otro microservicios, no confíe en que realiza solicitudes sincrónicas para esos datos. En su lugar, replicar o propagar esos datos (solo los atributos que se necesiten) en la base de datos del servicio inicial mediante coherencia definitiva (normalmente mediante el uso de eventos de integración, como se explica en las próximas secciones).

Como se indicó anteriormente en la sección [identifica los límites del modelo de dominio para cada microservicio](#identifying-domain-model-boundaries-for-each-microservice), duplicación de algunos datos a través de varias microservicios no es un diseño incorrecto, por el contrario, al hacer que puede convertir los datos en el idioma específico o los términos de ese dominio adicional o el contexto limitado. Por ejemplo, en la [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) aplicación tienen un microservicio denominado identity.api que está a cargo de la mayoría de los datos del usuario a una entidad con el nombre de usuario. Sin embargo, si necesita almacenar datos acerca del usuario en el orden de microservicio, almacenar una entidad diferente denominada comprador. La entidad de comprador comparte la misma identidad con la entidad de usuario original, pero podría tener sólo los atributos algunas son necesarios para el dominio de orden y no el perfil completo del usuario.

Puede usar cualquier protocolo de comunicarse y propagar datos de forma asincrónica a través de microservicios para disponer de coherencia definitiva. Como se mencionó, puede usar eventos de integración con un bus de eventos o el mensaje broker o se puede usar incluso HTTP por sondeo en los demás servicios en su lugar. No importa. La regla importante es no crear dependencias sincrónicas entre su microservicios.

Las siguientes secciones explican los varios estilos de comunicación que se puede considerar el uso de una aplicación basada en microservicio.

## <a name="communication-styles"></a>Estilos de comunicación

Hay muchos protocolos y las opciones que puede usar para la comunicación, según el tipo de comunicación que desea usar. Si se utiliza un mecanismo de comunicación basada en solicitud/respuesta sincrónica, protocolos como HTTP y el resto de los enfoques son las más comunes, especialmente si va a publicar los servicios fuera del clúster de host o microservicio de Docker. Si va a comunicarse entre servicios internamente (dentro de su clúster de host o microservicios Docker) que le interese usar mecanismos de comunicación de formato binario (como la comunicación remota de Service Fabric o WCF mediante el uso de TCP y el formato binario). Como alternativa, puede usar los mecanismos de comunicación asincrónica y basada en mensajes como AMQP.

También hay varios formatos de mensaje como JSON o XML, o incluso binarios formatos, que pueden ser más eficaces. Si el formato binario elegido no es un estándar, probablemente no es una buena idea públicamente publicar los servicios con ese formato. Puede utilizar un formato no estándar para la comunicación interna entre los microservicios. Puede hacer esto cuando la comunicación entre microservicios dentro de su clúster de host o microservicio de Docker (orchestrators de Docker o Azure Service Fabric) o propietario de aplicaciones de cliente que se comunican con el microservicios.

### <a name="requestresponse-communication-with-http-and-rest"></a>Comunicación de solicitud/respuesta con HTTP y REST 

Cuando un cliente utiliza la comunicación de solicitud/respuesta, envía una solicitud a un servicio, a continuación, el servicio procesa la solicitud y envía una respuesta. Comunicación de solicitud/respuesta es especialmente idóneo para consultar los datos de una interfaz de usuario en tiempo real (una interfaz de usuario en directo) desde aplicaciones cliente. Por lo tanto, en una arquitectura de microservicio probablemente usará este mecanismo de comunicación para la mayoría de las consultas, tal como se muestra en la figura 4-16.

![](./media/image16.png)

**Figura 4-16**. El uso de comunicación de solicitud/respuesta HTTP (sincrónica o asincrónica)

Cuando un cliente utiliza la comunicación de solicitud/respuesta, da por supuesto que la respuesta llegarán en poco tiempo, normalmente menos de un segundo o unos pocos segundos como máximo. Para respuestas con retraso, debe implementar la comunicación asincrónica basada en [patrones de mensajería](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) y [tecnologías de mensajería](https://en.wikipedia.org/wiki/Message-oriented_middleware), que es un enfoque diferente que se explica en la sección siguiente.

Es un estilo arquitectónico popular para la comunicación de solicitud/respuesta [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). Este enfoque se basa en y estrechamente acoplado, el [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) de protocolo, la adopción de verbos HTTP, como GET, POST y colocar. REST es el enfoque de arquitectura de comunicación más usados al crear servicios. Puede implementar servicios REST al desarrollar servicios Web de ASP.NET Core API.

Hay un valor adicional al usar los servicios de REST de HTTP como el lenguaje de definición de interfaz. Por ejemplo, si usa [Swagger metadatos](http://swagger.io/) para describir la API de servicio, puede usar herramientas que generan código auxiliar del cliente directamente puede detectar y consumir los servicios.

### <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. Modelo de madurez Richardson.** Una descripción del modelo REST.
    [*http://martinfowler.com/articles/richardsonMaturityModel.HTML*](http://martinfowler.com/articles/richardsonMaturityModel.html)

-   **Swagger.** El sitio oficial.
    [*http://swagger.IO/*](http://swagger.io/)

### <a name="push-and-real-time-communication-based-on-http"></a>Comunicación en tiempo real basada en HTTP e inserción

Otra posibilidad (normalmente con fines diferentes al resto) es una comunicación en tiempo real y de uno a varios con marcos de trabajo de nivel superiores como [ASP.NET SignalR](https://www.asp.net/signalr) y protocolos como [WebSockets](https://en.wikipedia.org/wiki/WebSocket).

Como se muestra en la figura 4-17, la comunicación en tiempo real de HTTP significa que puede tener el código de servidor Insertar contenido en los clientes conectados, como los datos estén disponibles, en lugar de hacer que el servidor espera para que un cliente solicitar nuevos datos.

![](./media/image17.png)

**Figura 4-17**. Comunicación asincrónica de mensajes en tiempo real uno a uno

Puesto que es la comunicación en tiempo real, las aplicaciones cliente mostrar los cambios casi al instante. Normalmente, esto se controla mediante un protocolo como WebSockets, con muchas conexiones WebSockets (uno por cliente). Un ejemplo típico es cuando un servicio comunica un cambio en la puntuación de un juego de deportes para muchas aplicaciones web de cliente al mismo tiempo.


>[!div class="step-by-step"]
[Anterior] (direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md) [siguiente] (asincrónica-message-según-communication.md)
