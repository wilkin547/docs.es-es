---
title: Comunicación entre servicios
description: Obtenga información sobre cómo los microservicios de back-end nativos en la nube se comunican con otros microservicios de back-end.
author: robvet
ms.date: 01/19/2021
ms.openlocfilehash: 63c80b38e2fa42dccebefc772c969266fa9d79ca
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506271"
---
# <a name="service-to-service-communication"></a>Comunicación entre servicios

Al pasar del cliente front-end, ahora se abordan los microservicios de back-end que se comunican entre sí.

Al construir una aplicación nativa en la nube, querrá ser sensible a la manera en que los servicios back-end se comunican entre sí. Idealmente, la menor comunicación entre servicios, mejor. Sin embargo, no siempre es posible evitar que los servicios back-end se basen entre sí para completar una operación.

Hay varios métodos ampliamente aceptados para implementar la comunicación entre servicios. El *tipo de interacción de comunicación* a menudo determinará el mejor enfoque.

Tenga en cuenta los siguientes tipos de interacción:

- *Consulta* : cuando un microservicio de llamada requiere una respuesta de un microservicio llamado, como "¡ Hola, quiero obtener la información de comprador de un identificador de cliente determinado".

- *Comando* : cuando el microservicio de llamada necesita otro microservicio para ejecutar una acción, pero no requiere una respuesta, como "Hola, simplemente enviar este pedido".

- *Evento* : cuando un microservicio, denominado publicador, genera un evento que el estado ha cambiado o se ha producido una acción. Otros microservicios, denominados suscriptores interesados, pueden reaccionar al evento adecuadamente. El publicador y los suscriptores no se reconocen entre sí.

Los sistemas de microservicios suelen usar una combinación de estos tipos de interacción al ejecutar operaciones que requieren interacción entre servicios. Echemos un vistazo a cada una de ellas y cómo podría implementarlas.

## <a name="queries"></a>Consultas

Muchas veces, un microservicio podría necesitar *consultar* otro, lo que requiere una respuesta inmediata para completar una operación. Un microservicio de cesta de la compra puede necesitar información del producto y un precio para agregar un artículo a su cesta. Existen muchos enfoques para implementar operaciones de consulta.

### <a name="requestresponse-messaging"></a>Mensajería de solicitud-respuesta

Una opción para implementar este escenario es que el microservicio de back-end que realiza la llamada realice solicitudes HTTP directas a los microservicios que necesita consultar, tal como se muestra en la figura 4-8.

![Comunicación HTTP directa](./media/direct-http-communication.png)

**Figura 4-8**. Comunicación HTTP directa

Aunque las llamadas HTTP directas entre microservicios son relativamente fáciles de implementar, se debe tener cuidado para minimizar esta práctica. Para empezar, estas llamadas siempre son *sincrónicas* y bloquearán la operación hasta que se devuelva un resultado o se agote el tiempo de espera de la solicitud. A partir de ahora, los servicios independientes, que se pueden desarrollar de manera independiente e implementar con frecuencia, se acoplan entre sí. A medida que el acoplamiento entre los microservicios aumenta, disminuyen sus ventajas arquitectónicas.

La ejecución de una solicitud poco frecuente que realiza una única llamada HTTP directa a otro microservicio puede ser aceptable para algunos sistemas. Sin embargo, no se recomienda realizar llamadas de gran volumen que invoquen llamadas HTTP directas a varios microservicios. Pueden aumentar la latencia y afectar negativamente al rendimiento, la escalabilidad y la disponibilidad del sistema. Incluso peor, una larga serie de comunicaciones HTTP directas puede conducir a cadenas profundas y complejas de llamadas de microservicios sincrónicas, que se muestran en la figura 4-9:

![Encadenamiento de consultas HTTP](./media/chaining-http-queries.png)

**Figura 4-9**. Encadenamiento de consultas HTTP

Por supuesto, puede imaginarse el riesgo en el diseño que se muestra en la imagen anterior. ¿Qué ocurre si \# se produce un error en el paso 3? ¿O el paso \# 8 produce un error? ¿Cómo se recupera? ¿Qué ocurre si \# el paso 6 es lento porque el servicio subyacente está ocupado? ¿Cómo se puede continuar? Incluso si todo funciona correctamente, piense en la latencia que podría tener esta llamada, que es la suma de la latencia de cada paso.

El gran grado de acoplamiento en la imagen anterior sugiere que los servicios no se modelaron de forma óptima. El equipo volvería a revisar su diseño.

### <a name="materialized-view-pattern"></a>Patrón Materialized View

Una opción popular para quitar el acoplamiento de microservicios es el [patrón de vista materializada](/azure/architecture/patterns/materialized-view). Con este patrón, un microservicio almacena su propia copia local y desnormalizada de los datos que pertenecen a otros servicios. En lugar del microservicio de cesta de la compra que consulta el catálogo de productos y los microservicios de precios, mantiene su propia copia local de los datos. Este patrón elimina el acoplamiento innecesario y mejora la confiabilidad y el tiempo de respuesta. Toda la operación se ejecuta dentro de un único proceso. Exploramos este patrón y otros aspectos relacionados con los datos en el capítulo 5.

### <a name="service-aggregator-pattern"></a>Patrón Service Aggregator

Otra opción para eliminar el acoplamiento de microservicios a microservicios es un [microservicio de agregador](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/), que se muestra en color púrpura en la figura 4-10.

![Servicio de agregación](./media/aggregator-service.png)

**Figura 4-10**. Microservicio del agregador

El patrón aísla una operación que realiza llamadas a varios microservicios de back-end, centralizando su lógica en un microservicio especializado.  El microservicio del agregador de retirada púrpura de la ilustración anterior organiza el flujo de trabajo para la operación de desprotección. Incluye llamadas a varios microservicios de back-end en orden secuencial. Los datos del flujo de trabajo se agregan y se devuelven al autor de la llamada. Aunque sigue implementando llamadas HTTP directas, el microservicio del agregador reduce las dependencias directas entre los microservicios de back-end.

### <a name="requestreply-pattern"></a>Patrón de solicitud/respuesta

Otro enfoque para desacoplar mensajes HTTP sincrónicos es un [patrón de solicitud-respuesta](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html), que usa la comunicación en cola. La comunicación mediante una cola es siempre un canal unidireccional, con un productor que envía el mensaje y el consumidor la recibe. Con este patrón, se implementan una cola de solicitudes y una cola de respuesta, que se muestran en la figura 4-11.

![Patrón de solicitud-respuesta](./media/request-reply-pattern.png)

**Figura 4-11**. Patrón de solicitud-respuesta

En este caso, el productor de mensajes crea un mensaje basado en consulta que contiene un identificador de correlación único y lo coloca en una cola de solicitudes. El servicio consumidor quita los mensajes de la cola, los procesa y coloca la respuesta en la cola de respuesta con el mismo identificador de correlación. El servicio productor quita el mensaje de la cola, lo hace coincidir con el identificador de correlación y continúa el procesamiento. En la sección siguiente se describen los detalles de las colas.

## <a name="commands"></a>Comandos:

Otro tipo de interacción de comunicación es un *comando*. Un microservicio puede necesitar otro microservicio para realizar una acción. El microservicio de pedidos puede necesitar el microservicio de envío para crear un envío para un pedido aprobado. En la figura 4-12, un microservicio, denominado productor, envía un mensaje a otro microservicio, el consumidor, y le hace algo.

![Interacción de comandos con una cola](./media/command-interaction-with-queue.png)

**Figura 4-12**. Interacción de comandos con una cola

La mayoría de las veces, el productor no requiere una respuesta y puede *desencadenar y olvidar* el mensaje. Si se necesita una respuesta, el consumidor envía un mensaje independiente de vuelta al productor en otro canal. Un mensaje de comando se envía mejor de forma asincrónica con una cola de mensajes. compatible con un agente de mensajes ligeros. En el diagrama anterior, observe cómo una cola separa y desacopla ambos servicios.

Una cola de mensajes es una construcción intermediario a través de la cual un productor y un consumidor pasan un mensaje. Las colas implementan un patrón de mensajería asincrónico y punto a punto. El productor sabe dónde se debe enviar un comando y enruta las rutas correctamente. La cola garantiza que un mensaje se procesa exactamente en una de las instancias del consumidor que leen desde el canal. En este escenario, el productor o el servicio de consumidor se pueden escalar horizontalmente sin que ello afecte a los demás. Además, las tecnologías pueden ser dispares en cada lado, lo que significa que podríamos tener un microservicio de Java que llame a un microservicio de [Golang](https://golang.org) .

En el capítulo 1, hablamos sobre los *servicios de respaldo*. Los servicios de respaldo son recursos auxiliares de los que dependen los sistemas nativos en la nube. Las colas de mensajes son servicios de respaldo. La nube de Azure admite dos tipos de colas de mensajes que los sistemas nativos en la nube pueden usar para implementar la mensajería de comandos: Azure Storage colas y colas de Azure Service Bus.

### <a name="azure-storage-queues"></a>Colas de Azure Storage

Las colas de Azure Storage ofrecen una infraestructura de puesta en cola sencilla, rápida, asequible y respaldada por cuentas de Azure Storage.

[Azure Storage colas](/azure/storage/queues/storage-queues-introduction) incluyen un mecanismo de puesta en cola basado en REST con mensajería confiable y persistente. Proporcionan un conjunto de características mínimas, pero son económicas y almacenan millones de mensajes. Su capacidad oscila hasta 500 TB. Un solo mensaje puede tener un tamaño de hasta 64 KB.

Puede tener acceso a los mensajes desde cualquier lugar del mundo a través de llamadas autenticadas con HTTP o HTTPS. Las colas de almacenamiento se pueden escalar horizontalmente a un gran número de clientes simultáneos para controlar los picos de tráfico.

Dicho esto, existen limitaciones en el servicio:

- No se garantiza el orden de los mensajes.

- Los mensajes solo se pueden conservar durante siete días antes de que se quiten automáticamente.

- No está disponible la compatibilidad con la administración de estado, la detección de duplicados o las transacciones.

En la figura 4-13 se muestra la jerarquía de una cola de Azure Storage.

![Jerarquía de colas de almacenamiento](./media/storage-queue-hierarchy.png)

**Figura 4-13**. Jerarquía de colas de almacenamiento

En la ilustración anterior, observe cómo las colas de almacenamiento almacenan sus mensajes en la cuenta de Azure Storage subyacente.

Para los desarrolladores, Microsoft proporciona varias bibliotecas de cliente y de servidor para el procesamiento de colas de almacenamiento. Se admiten la mayoría de las plataformas principales, como .NET, Java, JavaScript, Ruby, Python y go. Los desarrolladores nunca deben comunicarse directamente con estas bibliotecas. Al hacerlo, se acoplará estrechamente el código del microservicio al Queue service Azure Storage. Es aconsejable aislar los detalles de implementación de la API. Introduzca una capa de intermediación, o una API intermedia, que exponga las operaciones genéricas y encapsule la biblioteca concreta. Este acoplamiento flexible le permite intercambiar un servicio de cola por otro sin tener que realizar cambios en el código del servicio principal.

Azure Storage las colas son una opción económica para implementar la mensajería de comandos en las aplicaciones nativas de la nube. Especialmente cuando el tamaño de una cola supera los 80 GB, o un conjunto de características simple es aceptable. Solo paga por el almacenamiento de los mensajes; no hay cargos por hora fijos.

### <a name="azure-service-bus-queues"></a>Colas de Azure Service Bus

Para requisitos de mensajería más complejos, considere la posibilidad de Azure Service Bus las colas.

Sentado sobre una infraestructura de mensajes sólida, [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview) admite un *modelo de mensajería* asíncrona. Los mensajes se almacenan de forma confiable en un agente (la cola) hasta que los recibe el consumidor. La cola garantiza la entrega de mensajes de primero en salir/primero en salir (FIFO), respetando el orden en que se agregaron los mensajes a la cola.

El tamaño de un mensaje puede ser mucho mayor, hasta 256 KB. Los mensajes se conservan en la cola durante un período de tiempo ilimitado. Service Bus admite no solo llamadas basadas en HTTP, sino que también proporciona compatibilidad total con el [Protocolo AMQP](/azure/service-bus-messaging/service-bus-amqp-overview). AMQP es un estándar abierto entre proveedores que admite un protocolo binario y mayores grados de confiabilidad.

Service Bus proporciona un amplio conjunto de características, incluida la [compatibilidad con transacciones](/azure/service-bus-messaging/service-bus-transactions) y una [característica de detección de duplicados](/azure/service-bus-messaging/duplicate-detection). La cola garantiza "como máximo una entrega" por mensaje. Descarta automáticamente un mensaje que ya se ha enviado. Si un productor tiene dudas, puede volver a enviar el mismo mensaje y Service Bus garantiza que solo se procesará una copia. La detección de duplicados le libera de tener que crear una infraestructura de infraestructura adicional.

Dos características más empresariales son las particiones y las sesiones. Un solo agente de mensajes controla una cola de Service Bus convencional y se almacena en un único almacén de mensajes. No obstante, la creación de [particiones Service Bus](/azure/service-bus-messaging/service-bus-partitioning) propaga la cola entre varios agentes de mensajes y almacenes de mensajes. El rendimiento general ya no está limitado por el rendimiento de un solo agente de mensajes o almacén de mensajería. Una interrupción temporal de un almacén de mensajería no representa una cola con particiones disponible.

Las [sesiones de Service Bus](https://codingcanvas.com/azure-service-bus-sessions/) proporcionan una manera de agrupar mensajes relacionados. Imagine un escenario de flujo de trabajo en el que los mensajes se deben procesar juntos y la operación se completa al final. Para aprovechar las ventajas, las sesiones se deben habilitar explícitamente para la cola y cada mensaje relacionado debe contener el mismo identificador de sesión.

Sin embargo, hay algunas advertencias importantes: Service Bus tamaño de las colas está limitado a 80 GB, que es mucho menor que lo que está disponible en las colas de almacenamiento. Además, Service Bus las colas incurren en un costo base y un cargo por operación.

En la figura 4-14 se describe la arquitectura de alto nivel de una cola de Service Bus.

![Cola de Service Bus](./media/service-bus-queue.png)

**Figura 4-14**. Cola de Service Bus

En la ilustración anterior, observe la relación punto a punto. Dos instancias del mismo proveedor están poniendo en cola los mensajes en una sola cola de Service Bus. Cada mensaje se consume solo en una de las tres instancias de consumidor de la derecha. A continuación, se describe cómo implementar la mensajería en la que es posible que todos los consumidores puedan estar interesados en el mismo mensaje.

## <a name="events"></a>Eventos

Message Queue Server es una manera eficaz de implementar la comunicación en la que un productor puede enviar un mensaje de forma asincrónica a un consumidor. Sin embargo, ¿qué ocurre cuando *muchos consumidores diferentes* están interesados en el mismo mensaje? Una cola de mensajes dedicada para cada consumidor no se podría escalar bien y resultaría difícil de administrar.

Para abordar este escenario, pasamos al tercer tipo de interacción de mensajes, el *evento*. Un microservicio anuncia que se ha producido una acción. Otros microservicios, si está interesado, reaccionan ante la acción o el evento.

Los eventos son un proceso de dos pasos. Para un cambio de estado determinado, un microservicio publica un evento en un agente de mensajes, lo que lo pone a disposición de cualquier otro microservicio interesado. El microservicio interesado se notifica mediante la suscripción al evento en el agente de mensajes. El patrón de [publicación/suscripción](/azure/architecture/patterns/publisher-subscriber) se usa para implementar la [comunicación basada en eventos](/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications).

En la figura 4-15 se muestra un microservicio de cesta de la compra que publica un evento con otros dos microservicios que se suscriben a él.

![Mensajería Event-Driven](./media/event-driven-messaging.png)

**Figura 4-15**. Mensajería Event-Driven

Tenga en cuenta el componente de *bus de eventos* que se encuentra en medio del canal de comunicación. Es una clase personalizada que encapsula el agente de mensajes y lo desacopla de la aplicación subyacente. Los microservicios de ordenación y de inventario operan de forma independiente el evento sin ningún conocimiento de los demás ni del microservicio de cesta de la compra. Cuando el evento registrado se publica en el bus de eventos, actúan sobre él.

Con los eventos, pasamos de la tecnología de puesta en cola a los *temas*. Un [tema](/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) es similar a una cola, pero admite un patrón de mensajería de uno a varios. Un microservicio publica un mensaje. Varios microservicios de suscripción pueden optar por recibir el mensaje y actuar sobre él. En la figura 4-16 se muestra una arquitectura de tema.

![Arquitectura de temas](./media/topic-architecture.png)

**Figura 4-16**. Arquitectura de temas

En la ilustración anterior, los publicadores envían mensajes al tema. Al final, los suscriptores reciben mensajes de las suscripciones. En el centro, el tema reenvía los mensajes a las suscripciones en función de un conjunto de reglas, que se muestra en los cuadros azul oscuro. Las reglas actúan como un filtro que reenvía mensajes específicos a una suscripción. En este caso, se enviará un evento "GetPrice" al precio y a las suscripciones de registro, ya que la suscripción de registro ha elegido recibir todos los mensajes.  Un evento "GetInformation" se enviaría a la información y a las suscripciones de registro.

La nube de Azure admite dos servicios de temas distintos: Azure Service Bus temas y Azure EventGrid.

### <a name="azure-service-bus-topics"></a>Azure Service Bus Topics

En la parte superior del mismo modelo de mensaje asincrónico de Azure Service Bus colas se [Azure Service Bus temas](/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions). Un tema puede recibir mensajes de varios publicadores independientes y enviar mensajes a hasta 2.000 suscriptores. Las suscripciones se pueden agregar o quitar dinámicamente en tiempo de ejecución sin detener el sistema ni volver a crear el tema.

Muchas características avanzadas de Azure Service Bus colas también están disponibles para los temas, como la [detección de duplicados](/azure/service-bus-messaging/duplicate-detection) y la [compatibilidad con transacciones](/azure/service-bus-messaging/service-bus-transactions). De forma predeterminada, los temas de Service Bus se controlan mediante un único agente de mensajes y se almacenan en un único almacén de mensajes. No obstante, la creación de [particiones de Service Bus](/azure/service-bus-messaging/service-bus-partitioning) escala un tema mediante la propagación entre varios agentes de mensajes y almacenes de mensajes.

La [entrega de mensajes programada](/azure/service-bus-messaging/message-sequencing) etiqueta un mensaje con una hora específica para su procesamiento. El mensaje no aparecerá en el tema antes de esa hora. El [aplazamiento de mensajes](/azure/service-bus-messaging/message-deferral) le permite aplazar una recuperación de un mensaje en otro momento. Ambos se usan normalmente en escenarios de procesamiento de flujo de trabajo donde las operaciones se procesan en un orden determinado. Puede posponer el procesamiento de los mensajes recibidos hasta que se complete el trabajo anterior.

Service Bus temas son una tecnología sólida y probada para habilitar la comunicación de publicación/suscripción en los sistemas nativos de la nube.

### <a name="azure-event-grid"></a>Azure Event Grid

Aunque Azure Service Bus es un agente de mensajería probado en la batalla con un conjunto completo de características empresariales, [Azure Event Grid](/azure/event-grid/overview) es el nuevo niño en el bloque.

A primera vista, Event Grid puede parecer simplemente otro sistema de mensajería basado en temas. Sin embargo, es diferente de muchas maneras. Centrado en las cargas de trabajo orientadas a eventos, permite el procesamiento de eventos en tiempo real, la integración profunda de Azure y una plataforma abierta, todo ello en una infraestructura sin servidor. Está diseñado para aplicaciones contemporáneos nativas en la nube y sin servidor

Como *backplane* centralizado, o canalización, Event Grid reacciona a los eventos dentro de los recursos de Azure y desde sus propios servicios.

Las notificaciones de eventos se publican en un tema Event Grid, que, a su vez, enruta cada evento a una suscripción. Los suscriptores se asignan a las suscripciones y consumen los eventos. Al igual que Service Bus, Event Grid admite un *modelo de suscriptor filtrado* donde una suscripción establece una regla para los eventos que desea recibir. Event Grid proporciona un rendimiento rápido con una garantía de 10 millones eventos por segundo, lo que permite la entrega casi en tiempo real, más allá de lo que puede generar Azure Service Bus.

Una zona dulce para Event Grid es su profunda integración en el tejido de la infraestructura de Azure. Un recurso de Azure, como Cosmos DB, puede publicar eventos integrados directamente en otros recursos de Azure interesados, sin necesidad de código personalizado. Event Grid puede publicar eventos de una suscripción, un grupo de recursos o un servicio de Azure, lo que permite a los desarrolladores controlar el ciclo de vida de los recursos en la nube. Sin embargo, Event Grid no se limita a Azure. Es una plataforma abierta que puede consumir eventos HTTP personalizados publicados desde aplicaciones o servicios de terceros y enrutar eventos a suscriptores externos.

Al publicar y suscribirse a eventos nativos desde recursos de Azure, no se requiere ninguna codificación. Con la configuración sencilla, puede integrar eventos de un recurso de Azure a otro aprovechando la fontanería integrada para los temas y las suscripciones. En la figura 4-17 se muestra la anatomía de Event Grid.

![Event Grid anatomía](./media/event-grid-anatomy.png)

**Figura 4-17**. Event Grid anatomía

Una diferencia importante entre EventGrid y Service Bus es el *patrón de intercambio de mensajes* subyacente.

Service Bus implementa un *modelo de extracción* de estilo anterior en el que el suscriptor de nivel inferior sondea activamente la suscripción de tema para los nuevos mensajes. En el costado, este enfoque proporciona al suscriptor control total sobre el ritmo en el que procesa los mensajes. Controla cuándo y cuántos mensajes se procesan en un momento dado. Los mensajes sin leer permanecen en la suscripción hasta que se procesen. Una laguna significativa es la latencia entre el momento en que se genera el evento y la operación de sondeo que extrae ese mensaje al suscriptor para su procesamiento. Además, la sobrecarga de sondeo constante para el siguiente evento consume recursos y dinero.

Sin embargo, EventGrid es diferente. Implementa un modelo de *Insertar* en el que los eventos se envían a EventHandlers tal como se reciben, lo que da lugar a una entrega de eventos casi en tiempo real. También reduce el costo ya que el servicio solo se desencadena cuando se necesita consumir un evento, no continuamente como con el sondeo. Dicho esto, un controlador de eventos debe administrar la carga entrante y proporcionar mecanismos de limitación para evitar que se sobrecargue. Muchos servicios de Azure que consumen estos eventos, como Azure Functions y Logic Apps proporcionan funcionalidades de escalado automático automática para controlar las mayores cargas.  

Event Grid es un servicio en la nube sin servidor totalmente administrado. Se escala dinámicamente en función del tráfico y se le cobra solo por el uso real, no por la capacidad adquirida previamente. Las primeras 100.000 operaciones al mes son gratuitas: las operaciones que se definen como entrada de eventos (notificaciones de eventos entrantes), intentos de entrega de suscripciones, llamadas de administración y filtrado por asunto. Con una disponibilidad del 99,99%, EventGrid garantiza la entrega de un evento en un período de 24 horas, con funcionalidad de reintento integrada para la entrega incorrecta. Los mensajes no entregados se pueden migrar a una cola de "mensajes con problemas de entrega" para su resolución.  A diferencia de Azure Service Bus, Event Grid se optimiza para un rendimiento rápido y no admite características como mensajería ordenada, transacciones y sesiones.

### <a name="streaming-messages-in-the-azure-cloud"></a>Transmisión de mensajes en la nube de Azure

Azure Service Bus y Event Grid proporcionan una gran compatibilidad para las aplicaciones que exponen eventos únicos y discretos, como un nuevo documento, que se ha insertado en un Cosmos DB. Pero, ¿qué ocurre si el sistema nativo de la nube necesita procesar un *flujo de eventos relacionados*? Los [flujos de eventos](/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) son más complejos. Normalmente, se ordenan por tiempo, se interrelacionan y se deben procesar como un grupo.

[Azure Event hubs](https://azure.microsoft.com/services/event-hubs/) es una plataforma de streaming de datos y un servicio de ingesta de eventos que recopila, transforma y almacena eventos. Se ajusta para capturar datos de streaming, como las notificaciones de eventos continuos que se emiten desde un contexto de telemetría. El servicio es muy escalable y puede almacenar y [procesar millones de eventos por segundo](/azure/event-hubs/event-hubs-about). Como se muestra en la figura 4-18, a menudo es una puerta delantera para una canalización de eventos, desacoplando el flujo de ingesta del consumo de eventos.

![Centro de eventos de Azure](./media/azure-event-hub.png)

**Figura 4-18**. Centro de eventos de Azure

Event hubs admite la baja latencia y la retención de tiempo configurable. A diferencia de las colas y los temas, Event Hubs conservar los datos de eventos después de que los lea un consumidor. Esta característica permite a otros servicios de análisis de datos, tanto internos como externos, reproducir los datos para su posterior análisis. Los eventos almacenados en el centro de eventos solo se eliminan tras la expiración del período de retención, que es un día de forma predeterminada, pero configurable.

Event hubs admite protocolos de publicación de eventos comunes, como HTTPS y AMQP. También es compatible con Kafka 1,0. [Las aplicaciones de Kafka existentes pueden comunicarse con el centro de eventos](/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) mediante el protocolo Kafka, lo que proporciona una alternativa a la administración de clústeres de Kafka de gran tamaño. Muchos sistemas nativos de la nube de código abierto adoptan Kafka.

Event Hubs implementa el streaming de mensajes a través de un [modelo de consumidor con particiones](/azure/event-hubs/event-hubs-features) en el que cada consumidor solo Lee un subconjunto específico o una partición del flujo de mensajes. Este patrón permite una gran escala horizontal para procesamiento de eventos y proporciona otras características centradas en secuencias que no están disponibles en colas y temas. Una partición es una secuencia ordenada de eventos que se mantiene en un centro de eventos. A medida que llegan eventos más recientes, se agregan al final de esta secuencia. En la figura 4-19 se muestra la creación de particiones en un centro de eventos.

![Creación de particiones del centro de eventos](./media/event-hub-partitioning.png)

**Figura 4-19**. Creación de particiones del centro de eventos

En lugar de leer desde el mismo recurso, cada grupo de consumidores Lee un subconjunto o una partición del flujo de mensajes.

En el caso de las aplicaciones nativas de la nube que deben transmitir un gran número de eventos, Azure Event Hub puede ser una solución sólida y asequible.

>[!div class="step-by-step"]
>[Anterior](front-end-communication.md)
>[Siguiente](grpc.md)
