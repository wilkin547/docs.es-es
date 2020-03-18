---
title: Comunicación en una arquitectura de microservicio
description: Explore distintas formas de comunicación entre microservicios, y comprenda las implicaciones de formas sincrónicas y asincrónicas.
ms.date: 01/30/2020
ms.openlocfilehash: f2d6e78966bb7d5f481de6db0ab1dcfe2812a1b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401524"
---
# <a name="communication-in-a-microservice-architecture"></a>Comunicación en una arquitectura de microservicio

En una aplicación monolítica que se ejecuta en un único proceso, los componentes se invocan entre sí mediante llamadas de función o método de nivel de lenguaje. Pueden estar estrechamente acoplados si se crean objetos con código (por ejemplo, `new ClassName()`) o pueden invocarse de forma desacoplada si se usa la inserción de dependencias al hacer referencia a abstracciones en lugar de a instancias de objeto concretas. En cualquier caso, los objetos se ejecutan en el mismo proceso. Lo más complicado a la hora de pasar de una aplicación monolítica a una aplicación basada en microservicios es cambiar el mecanismo de comunicación. Una conversión directa de llamadas de método en curso a llamadas RPC a servicios dará lugar a una comunicación extensa y no eficaz con un mal rendimiento en entornos distribuidos. Los desafíos que conlleva diseñar un sistema distribuido correctamente son tan bien conocidos que incluso existe un canon llamado [Falacias del cómputo distribuido](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) que enumera las expectativas que suelen tener los desarrolladores al migrar de diseños monolíticos a distribuidos.

No existe una única solución, sino varias. Una de ellas implica aislar los microservicios de negocios lo máximo posible. Luego se usa la comunicación asincrónica entre los microservicios internos y se sustituye la comunicación específica típica de la comunicación en proceso entre objetos por la comunicación general. Para ello se agrupan las llamadas y se devuelven los datos que agregan los resultados de varias llamadas internas al cliente.

Una aplicación basada en microservicios es un sistema distribuido que se ejecuta en varios procesos o servicios, normalmente incluso en varios servidores o hosts. Lo habitual es que cada instancia de servicio sea un proceso. Por lo tanto, los servicios deben interactuar mediante un protocolo de comunicación entre procesos como HTTP, AMQP o un protocolo binario como TCP, en función de la naturaleza de cada servicio.

La comunidad de microservicios promueve la filosofía "[puntos de conexión inteligentes y canalizaciones tontas](https://simplicable.com/new/smart-endpoints-and-dumb-pipes)". Este eslogan fomenta un diseño lo más desacoplado posible entre microservicios y lo más cohesionado posible dentro de un único microservicio. Como se ha explicado anteriormente, cada microservicio posee sus propios datos y su propia lógica de dominio. Pero normalmente los microservicios que componen una aplicación de un extremo a otro se establecen sencillamente mediante comunicaciones de REST en lugar de protocolos complejos como WS-\* y comunicaciones flexibles controladas por eventos en lugar de orquestadores de procesos de negocios centralizados.

Los dos protocolos que se usan habitualmente son respuesta-solicitud HTTP con API de recurso (sobre todo al consultar) y mensajería asincrónica ligera al comunicar actualizaciones en varios microservicios. Se explican más detalladamente en las secciones siguientes.

## <a name="communication-types"></a>Tipos de comunicación

El cliente y los servicios pueden comunicarse a través de muchos tipos diferentes de comunicación, cada uno destinado a un escenario y unos objetivos distintos. Inicialmente, esos tipos de comunicaciones se pueden clasificar en dos ejes.

El primer eje define si el protocolo es sincrónico o asincrónico:

- Protocolo sincrónico. HTTP es un protocolo sincrónico. El cliente envía una solicitud y espera una respuesta del servicio. Eso es independiente de la ejecución de código de cliente, que puede ser sincrónica (el subproceso está bloqueado) o asincrónica (el subproceso no está bloqueado y al final la respuesta llega a una devolución de llamada). Lo importante aquí es que el protocolo (HTTP/HTTPS) es sincrónico y el código de cliente solo puede continuar su tarea cuando recibe la respuesta del servidor HTTP.

- Protocolo asincrónico. Otros protocolos como AMQP (un protocolo compatible con muchos sistemas operativos y entornos de nube) usan mensajes asincrónicos. Normalmente el código de cliente o el remitente del mensaje no espera ninguna respuesta. Simplemente envía el mensaje al igual que cuando se envía un mensaje a una cola de RabbitMQ o a cualquier otro agente de mensajes.

El segundo eje define si la comunicación tiene un único receptor o varios:

- Receptor único. Cada solicitud debe ser procesada por un receptor o servicio exactamente. Un ejemplo de este tipo de comunicación es el [patrón Command](https://en.wikipedia.org/wiki/Command_pattern).

- Varios receptores. Cada solicitud puede ser procesada por entre cero y varios receptores. Este tipo de comunicación debe ser asincrónica. Un ejemplo es el mecanismo de [publicación o suscripción](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) empleado en patrones como la [arquitectura controlada por eventos](https://microservices.io/patterns/data/event-driven-architecture.html). Se basa en una interfaz de bus de eventos o un agente de mensajes para propagar las actualizaciones de datos entre varios microservicios mediante eventos; normalmente se implementa a través de un bus de servicio o algún artefacto similar como [Azure Service Bus](https://azure.microsoft.com/services/service-bus/) mediante [temas y suscripciones](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions).

Una aplicación basada en microservicio suele usar una combinación de estos estilos de comunicación. El tipo más común es la comunicación de un único receptor con un protocolo sincrónico como HTTP/HTTPS al invocar a un servicio normal HTTP Web API. Además, los microservicios suelen usar protocolos de mensajería para la comunicación asincrónica entre microservicios.

Resulta útil conocer estos ejes para tener claros los posibles mecanismos de comunicación, aunque no son la preocupación más importante a la hora de compilar microservicios. Al integrar microservicios, no son importantes ni la naturaleza asincrónica de la ejecución de subprocesos de cliente ni la naturaleza asincrónica del protocolo seleccionado. Lo que *sí* es importante es poder integrar los microservicios de forma asincrónica a la vez que se mantiene su independencia, como se explica en la sección siguiente.

## <a name="asynchronous-microservice-integration-enforces-microservices-autonomy"></a>La integración asincrónica del microservicio obliga a su autonomía

Como se ha mencionado, lo importante al compilar una aplicación basada en microservicios es la forma de integrarlos. Lo ideal es intentar minimizar la comunicación entre los microservicios internos. Cuantas menos comunicaciones haya entre microservicios, mejor. Pero en muchos casos tendrá que integrar los microservicios de algún modo. Cuando necesite hacerlo, la regla fundamental es que la comunicación entre los microservicios debe ser asincrónica. Eso no significa que tenga que usar un protocolo determinado (por ejemplo, mensajería asincrónica frente a HTTP sincrónico). Simplemente significa que la comunicación entre los microservicios debe realizarse únicamente mediante la propagación asincrónica de datos, aunque se debe intentar no depender de otros microservicios internos como parte de la operación solicitud-respuesta HTTP del servicio inicial.

Si es posible, no dependa nunca de la comunicación sincrónica (solicitud-respuesta) entre varios microservicios, ni siquiera para las consultas. El objetivo de cada microservicio es ser autónomo y estar a disposición del cliente, aunque los demás servicios que forman parte de la aplicación de un extremo a otro estén inactivos o en mal estado. Si cree que necesita realizar una llamada desde un microservicio a otros (por ejemplo, una solicitud HTTP para una consulta de datos) para poder proporcionar una respuesta a una aplicación cliente, tiene una arquitectura que no resistirá si se producen errores en algunos microservicios.

Además, el tener dependencias HTTP entre microservicios, como al crear largos ciclos de solicitud-respuesta con cadenas de solicitudes HTTP, como se muestra en la primera parte de la figura 4-15, no solo hace que los microservicios no sean autónomos, sino que también afecta a su rendimiento en cuanto alguno de los servicios de esa cadena no funciona correctamente.

Cuantas más dependencias sincrónicas agregue entre microservicios, como solicitudes de consulta, peor será el tiempo de respuesta total de las aplicaciones cliente.

![Diagrama que muestra tres tipos de comunicaciones entre los microservicios.](./media/communication-in-microservice-architecture/sync-vs-async-patterns-across-microservices.png)

**Figura 4-15**. Anti-patrones y patrones de comunicación entre microservicios

Tal y como se muestra en el diagrama anterior, en la comunicación sincrónica se crea una "cadena" de solicitudes entre los microservicios mientras se atiende la solicitud del cliente. Esto es un antipatrón. En la comunicación asincrónica los microservicios usan mensajes asincrónicos o sondeo http para comunicarse con otros microservicios, pero la solicitud de cliente se sirve inmediatamente.

Si el microservicio tiene que producir una acción adicional en otro microservicio, siempre que sea posible, no realice esa acción de forma sincrónica como parte de la operación solicitud-respuesta original del microservicio. Por el contrario, hágalo de forma asincrónica (mediante mensajería asincrónica o eventos de integración, colas, etc.). Pero, siempre que sea posible, no invoque a la acción de forma sincrónica como parte de la operación solicitud-respuesta sincrónica original.

Y, por último (y aquí es donde surgen la mayoría de los problemas al compilar microservicios), si el microservicio inicial necesita datos cuyo propietario original es otro microservicio, no dependa de la realización de solicitudes sincrónicas para esos datos. En su lugar, replique o propague esos datos (solo los atributos que necesite) en la base de datos del servicio inicial mediante la coherencia final (normalmente mediante eventos de integración, como se explica en las próximas secciones).

Como se ha indicado anteriormente en la sección [Identificación de los límites del modelo de dominio para cada microservicio](identify-microservice-domain-model-boundaries.md), la duplicación de algunos datos en varios microservicios no es un diseño incorrecto, sino que permite convertir los datos al lenguaje o los términos específicos de ese dominio adicional o contexto enlazado. Por ejemplo, en la [aplicación eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers), hay un microservicio denominado `identity-api` que se encarga de la mayoría de los datos del usuario con una entidad denominada `User`. Sin embargo, cuando necesite almacenar datos sobre el usuario en el microservicio `Ordering`, lo hará como una entidad diferente denominada `Buyer`. La entidad `Buyer` comparte la misma identidad con la entidad `User` original, pero podría tener solo los atributos que necesita el dominio `Ordering` y no el perfil completo del usuario.

Podría usar cualquier protocolo para comunicar y propagar datos de forma asincrónica en microservicios para disponer de coherencia final. Como se ha mencionado, puede usar eventos de integración con un bus de eventos o un agente de mensajes o, si no, puede usar incluso HTTP mediante el sondeo de los demás servicios, No importa. Lo importante es no crear dependencias sincrónicas entre los microservicios.

En las siguientes secciones se explican los diversos estilos de comunicación que se pueden usar en una aplicación basada en microservicio.

## <a name="communication-styles"></a>Estilos de comunicación

Hay muchos protocolos y opciones que se pueden usar para la comunicación, según el tipo de comunicación que se quiera emplear. Si va a usar un mecanismo de comunicación sincrónico basado en solicitud-respuesta, los enfoques de protocolos como HTTP y REST son los más comunes, especialmente si va a publicar los servicios fuera del host de Docker o el clúster de microservicios. Si va a comunicarse entre servicios de forma interna (dentro del host de Docker o el clúster de microservicios), es posible que también quiera usar mecanismos de comunicación de formato binario (como WCF mediante TCP y formato binario). También puede usar mecanismos de comunicación asincrónicos basados en mensajes como AMQP.

Además hay varios formatos de mensaje como JSON o XML, o incluso formatos binarios, que pueden resultar más eficaces. Si el formato binario elegido no es estándar, probablemente no sea buena idea publicar los servicios con ese formato. Puede usar un formato no estándar para la comunicación interna entre los microservicios. Podría hacerlo así para la comunicación entre microservicios dentro del host de Docker o el clúster de microservicios (orquestadores de Docker, por ejemplo) o para las aplicaciones cliente de su propiedad que se comunican con los microservicios.

### <a name="requestresponse-communication-with-http-and-rest"></a>Comunicación solicitud-respuesta con HTTP y REST

Cuando un cliente usa la comunicación solicitud-respuesta, envía una solicitud a un servicio, este la procesa y luego envía una respuesta. La comunicación solicitud-respuesta resulta especialmente idónea para consultar datos de una interfaz de usuario en tiempo real (una interfaz de usuario activa) desde aplicaciones cliente. Por tanto, en una arquitectura de microservicio probablemente se use este mecanismo de comunicación para la mayoría de las consultas, como se muestra en la figura 4-16.

![Diagrama que muestra las comunicaciones de solicitud/respuesta para las consultas y actualizaciones activas.](./media/communication-in-microservice-architecture/request-response-comms-live-queries-updates.png)

**Figura 4-16**. Uso de la comunicación solicitud-respuesta HTTP (sincrónica o asincrónica)

Cuando un cliente usa la comunicación solicitud-respuesta, da por hecho que la respuesta llegará en poco tiempo, normalmente en menos de un segundo, o unos pocos segundos como máximo. Si se retrasan las respuestas, debe implementar la comunicación asincrónica basada en [patrones de mensajería](https://docs.microsoft.com/azure/architecture/patterns/category/messaging) y [tecnologías de mensajería](https://en.wikipedia.org/wiki/Message-oriented_middleware), que es otro enfoque que se explica en la sección siguiente.

Un estilo arquitectónico popular para la comunicación solicitud-respuesta es [REST](https://en.wikipedia.org/wiki/Representational_state_transfer). Este enfoque se basa en el protocolo [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) y está estrechamente relacionado con él, ya que adopta verbos HTTP como GET, POST y PUT. REST es el enfoque de arquitectura de comunicación más usado a la hora de crear servicios. Puede implementar servicios REST cuando desarrolle servicios Web API de ASP.NET Core.

El uso de servicios REST de HTTP como lenguaje de definición de interfaz ofrece algunas ventajas. Por ejemplo, si usa [metadatos de Swagger](https://swagger.io/) para describir la API de servicio, puede usar herramientas que generan código auxiliar de cliente que puede detectar y usar directamente los servicios.

### <a name="additional-resources"></a>Recursos adicionales

- **Martin Fowler. Richardson Maturity Model** A description of the REST model (Modelo de madurez Richardson. Una descripción del modelo REST). \
  <https://martinfowler.com/articles/richardsonMaturityModel.html>

- **Swagger** Sitio oficial. \
  <https://swagger.io/>

### <a name="push-and-real-time-communication-based-on-http"></a>Comunicación de inserción y en tiempo real basada en HTTP

Otra posibilidad (normalmente para fines distintos que REST) es una comunicación en tiempo real y de uno a varios con marcos de trabajo de nivel superior como [ASP.NET SignalR](https://www.asp.net/signalr) y protocolos como [WebSockets](https://en.wikipedia.org/wiki/WebSocket).

Como se muestra en la figura 4-17, la comunicación HTTP en tiempo real significa que puede hacer que el código de servidor inserte contenido en los clientes conectados a medida que los datos están disponibles, en lugar de hacer que el servidor espere a que un cliente pida nuevos datos.

![Diagrama que muestra las comunicaciones de inserción y en tiempo real basadas en SignalR.](./media/communication-in-microservice-architecture/one-to-many-communication.png)

**Figura 4-17**. Comunicación de mensajes asincrónica en tiempo real uno a uno

SignalR es una buena forma de lograr una comunicación en tiempo real para insertar contenido a los clientes desde un servidor back-end. Puesto que la comunicación es en tiempo real, las aplicaciones cliente muestran los cambios prácticamente de forma inmediata. Normalmente, esto se controla mediante un protocolo como WebSockets, con muchas conexiones WebSockets (una por cliente). Un ejemplo típico es cuando un servicio comunica un cambio en el marcador de un partido a muchas aplicaciones web cliente a la vez.

>[!div class="step-by-step"]
>[Anterior](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
>[Siguiente](asynchronous-message-based-communication.md)
