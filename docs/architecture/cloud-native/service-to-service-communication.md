---
title: Comunicación de servicio a servicio
description: Obtenga información sobre cómo los microservicios nativos de la nube de back-end se comunican con otros microservicios back-end.
author: robvet
ms.date: 09/09/2019
ms.openlocfilehash: 926be3c2eb4513c89ebcd1f31dceb7d58639dc6f
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523563"
---
# <a name="service-to-service-communication"></a>Comunicación de servicio a servicio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Al pasar del cliente front-end, ahora nos dirigimos a microservicios back-end que se comunican entre sí.

Al crear una aplicación nativa de la nube, querrá ser sensible a cómo se comunican los servicios back-end entre sí. Idealmente, cuanto menos comunicación entre servicios, mejor. Sin embargo, la evitación no siempre es posible, ya que los servicios back-end a menudo dependen unos de otros para completar una operación.

Existen varios enfoques ampliamente aceptados para implementar la comunicación entre servicios. El *tipo de interacción de comunicación* a menudo determinará el mejor enfoque.

Tenga en cuenta los siguientes tipos de interacción:

- *Consulta:* cuando un microservicio que realiza una llamada requiere una respuesta de un microservicio llamado, como" "Oye, dame la información del comprador para un identificador de cliente determinado."

- *Comando:* cuando el microservicio que realiza la llamada necesita otro microservicio para ejecutar una acción, pero no requiere una respuesta, como, "Oye, simplemente envía esta orden".

- *Evento:* cuando un microservicio, denominado publicador, genera un evento que indica que el estado ha cambiado o se ha producido una acción. Otros microservicios, denominados suscriptores, que están interesados, pueden reaccionar al evento de forma adecuada. El editor y los suscriptores no se conocen entre sí.

Los sistemas de microservicios suelen usar una combinación de estos tipos de interacción al ejecutar operaciones que requieren interacción entre servicios. Echemos un vistazo de cerca a cada uno y cómo podría implementarlos.

## <a name="queries"></a>Consultas

Muchas veces, un microservicio puede necesitar *consultar* otro, lo que requiere una respuesta inmediata para completar una operación. Un microservicio de cesta de la compra puede necesitar información del producto y un precio para agregar un artículo a su cesta. Hay una serie de enfoques para implementar operaciones de consulta.

### <a name="requestresponse-messaging"></a>Mensajería de solicitud-respuesta

Una opción para implementar este escenario es que el microservicio back-end de llamada realice solicitudes HTTP directas a los microservicios que necesita consultar, que se muestra en la figura 4-8.

![Comunicación HTTP directa](./media/direct-http-communication.png)

**Figura 4-8**. Comunicación HTTP directa

Aunque las llamadas HTTP directas entre microservicios son relativamente sencillas de implementar, se debe tener cuidado para minimizar esta práctica. Para empezar, estas llamadas siempre son *sincrónicas* y bloquearán la operación hasta que se devuelva un resultado o se adelante la solicitud. Lo que antes eran servicios independientes e independientes, capaces de evolucionar de forma independiente y desplegarse con frecuencia, ahora se acoplan entre sí. A medida que aumenta el acoplamiento entre los microservicios, sus beneficios arquitectónicos disminuyen.

La ejecución de una solicitud poco frecuente que realiza una única llamada HTTP directa a otro microservicio podría ser aceptable para algunos sistemas. Sin embargo, no es recomendable realizar llamadas de gran volumen que invoquen llamadas HTTP directas a varios microservicios. Pueden aumentar la latencia y afectar negativamente al rendimiento, la escalabilidad y la disponibilidad del sistema. Peor aún, una larga serie de comunicaciones HTTP directas puede conducir a cadenas profundas y complejas de llamadas de microservicios sincrónicos, que se muestra n.o 4-9:

![Encadenamiento de consultas HTTP](./media/chaining-http-queries.png)

**Figura 4-9**. Encadenamiento de consultas HTTP

Usted puede sin duda imaginar el riesgo en el diseño mostrado en la imagen anterior. ¿Qué sucede \#si se produce un error en el paso 3? ¿O \#el paso 8 falla? ¿Cómo te recuperas? ¿Qué \#sucede si el paso 6 es lento porque el servicio subyacente está ocupado? ¿Cómo continúas? Incluso si todo funciona correctamente, piense en la latencia en la que incurriría esta llamada, que es la suma de la latencia de cada paso.

El gran grado de acoplamiento en la imagen anterior sugiere que los servicios no se modelaron de forma óptima. Sería bueno que el equipo revisara su diseño.

### <a name="materialized-view-pattern"></a>Patrón Materialized View

Una opción popular para eliminar el acoplamiento de microservicios es el [patrón de vista materializada.](https://docs.microsoft.com/azure/architecture/patterns/materialized-view) Con este patrón, un microservicio almacena su propia copia local desnormalizada de los datos que son propiedad de otros servicios. En lugar del microservicio de la cesta de la compra que consulta el catálogo de productos y los microservicios de precios, mantiene su propia copia local de esos datos. Este patrón elimina el acoplamiento innecesario y mejora la fiabilidad y el tiempo de respuesta. Toda la operación se ejecuta dentro de un único proceso. Exploramos este patrón y otras preocupaciones de datos en el Capítulo 5.

### <a name="service-aggregator-pattern"></a>Patrón de agregador de servicio

Otra opción para eliminar el acoplamiento de microservicio a microservicio es un [microservicio de agregador,](https://devblogs.microsoft.com/cesardelatorre/designing-and-implementing-api-gateways-with-ocelot-in-a-microservices-and-container-based-architecture/)que se muestra en púrpura en la figura 4-10.

![Servicio de agregador](./media/aggregator-service.png)

**Figura 4-10**. Microservicio de agregador

El patrón aísla una operación que realiza llamadas a varios microservicios back-end, centralizando su lógica en un microservicio especializado.  El microservicio de agregador de desprotección púrpura en la figura anterior orquesta el flujo de trabajo para la operación de desprotección. Incluye llamadas a varios microservicios back-end en un orden secuenciado. Los datos del flujo de trabajo se agregan y se devuelven al autor de la llamada. Aunque sigue implementando llamadas HTTP directas, el microservicio de agregador reduce las dependencias directas entre los microservicios back-end.

### <a name="requestreply-pattern"></a>Patrón de solicitud/respuesta

Otro enfoque para desacoplar mensajes HTTP sincrónicos es un [patrón de solicitud-respuesta,](https://www.enterpriseintegrationpatterns.com/patterns/messaging/RequestReply.html)que utiliza la comunicación de cola. La comunicación mediante una cola siempre es un canal unidireccional, con un productor enviando el mensaje y el consumidor recibiendo. Con este patrón, se implementan una cola de solicitudes y una cola de respuesta, que se muestran en la Figura 4-11.

![Patrón de solicitud-respuesta](./media/request-reply-pattern.png)

**Figura 4-11**. Patrón de solicitud-respuesta

Aquí, el productor de mensajes crea un mensaje basado en consultas que contiene un identificador de correlación único y lo coloca en una cola de solicitudes. El servicio de consumo elimina los mensajes, los procesa y coloca la respuesta en la cola de respuesta con el mismo identificador de correlación. El servicio de productor elimina el mensaje, lo hace coincidir con el identificador de correlación y continúa el procesamiento. Cubrimos las colas en detalle en la siguiente sección.

## <a name="commands"></a>Comandos:

Otro tipo de interacción de comunicación es un *comando*. Un microservicio puede necesitar otro microservicio para realizar una acción. El microservicio De pedidos puede necesitar el microservicio Envío para crear un envío para un pedido aprobado. En la Figura 4-12, un microservicio, denominado Productor, envía un mensaje a otro microservicio, el Consumidor, ordenándolo que haga algo.

![Interacción de comandos con una cola](./media/command-interaction-with-queue.png)

**Figura 4-12**. Interacción de comandos con una cola

Muy a menudo, el Productor no requiere una respuesta y puede *disparar y olvidar* el mensaje. Si se necesita una respuesta, el consumidor envía un mensaje independiente al productor en otro canal. Un mensaje de comando se envía mejor de forma asincrónica con una cola de mensajes. un agente de mensajes ligero. En el diagrama anterior, observe cómo una cola separa y desacopla ambos servicios.

Una cola de mensajes es una construcción intermedia a través de la cual un productor y un consumidor pasan un mensaje. Las colas implementan un patrón de mensajería asincrónico punto a punto. El Productor sabe dónde necesita enviarse un comando y rutea adecuadamente. La cola garantiza que un mensaje es procesado por exactamente una de las instancias de consumidor que están leyendo desde el canal. En este escenario, el productor o el servicio de consumidor pueden escalar horizontalmente sin afectar al otro. Además, las tecnologías pueden ser dispares en cada lado, lo que significa que podríamos tener un microservicio Java llamando a un microservicio [Golang.](https://golang.org)

En el capítulo 1, hablamos de *los servicios*de respaldo . Los servicios de respaldo son recursos auxiliares de los que dependen los sistemas nativos de la nube. Las colas de mensajes son servicios de respaldo. La nube de Azure admite dos tipos de colas de mensajes que los sistemas nativos de la nube pueden consumir para implementar la mensajería de comandos: colas de Azure Storage y colas de Bus de servicio de Azure.

### <a name="azure-storage-queues"></a>Colas de Azure Storage

Las colas de almacenamiento de Azure ofrecen una infraestructura de cola sencilla que es rápida, asequible y está respaldada por cuentas de almacenamiento de Azure.

[Las colas](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction) de azure Storage cuentan con un mecanismo de cola basado en REST con mensajería confiable y persistente. Proporcionan un conjunto de características mínimo, pero son baratos y almacenan millones de mensajes. Su capacidad oscila hasta 500 TB. Un solo mensaje puede tener un tamaño de hasta 64 KB.

Puede acceder a los mensajes desde cualquier lugar del mundo a través de llamadas autenticadas mediante HTTP o HTTPS. Las colas de almacenamiento pueden escalar horizontalmente a un gran número de clientes simultáneos para controlar los picos de tráfico.

Dicho esto, hay limitaciones con el servicio:

- El orden de los mensajes no está garantizado.

- Un mensaje solo puede persistir durante siete días antes de que se elimine automáticamente.

- La compatibilidad con la administración de estados, la detección de duplicados o las transacciones no está disponible.

En la figura 4-13 se muestra la jerarquía de una cola de Azure Storage.

![Jerarquía de colas de almacenamiento](./media/storage-queue-hierarchy.png)

**Figura 4-13**. Jerarquía de colas de almacenamiento

En la figura anterior, observe cómo las colas de almacenamiento almacenan sus mensajes en la cuenta de Azure Storage subyacente.

Para los desarrolladores, Microsoft proporciona varias bibliotecas de cliente y servidor para el procesamiento de colas de almacenamiento. La mayoría de las plataformas principales son compatibles, incluyendo .NET, Java, JavaScript, Ruby, Python y Go. Los desarrolladores nunca deben comunicarse directamente con estas bibliotecas. Si lo hace, acoplará estrechamente el código de microservicio al servicio Azure Storage Queue. Es una mejor práctica aislar los detalles de implementación de la API. Introducir una capa de intermediación, o API intermedia, que expone operaciones genéricas y encapsula la biblioteca concreta. Este acoplamiento suelto le permite intercambiar un servicio de cola por otro sin tener que realizar cambios en el código de servicio principal.

Las colas de Azure Storage son una opción económica para implementar la mensajería de comandos en las aplicaciones nativas de la nube. Especialmente cuando un tamaño de cola superará los 80 GB, o un conjunto de características simple es aceptable. Solo paga por el almacenamiento de los mensajes; no hay cargos fijos por hora.

### <a name="azure-service-bus-queues"></a>Azure Service Bus Queues

Para requisitos de mensajería más complejos, tenga en cuenta las colas de Azure Service Bus.

En una sólida infraestructura de mensajes, [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview) admite un modelo de *mensajería intermediada.* Los mensajes se almacenan de forma fiable en un intermediario (la cola) hasta que el consumidor los recibe. La cola garantiza la entrega de mensajes First-In/First-Out (FIFO), respetando el orden en que se agregaron los mensajes a la cola.

El tamaño de un mensaje puede ser mucho mayor, hasta 256 KB. Los mensajes se conservan en la cola durante un período de tiempo ilimitado. Service Bus no solo admite llamadas basadas en HTTP, sino que también proporciona compatibilidad completa con el [protocolo AMPQ.](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-amqp-overview) AMPQ es un estándar abierto entre proveedores que admite un protocolo binario y mayores grados de confiabilidad.

Service Bus proporciona un amplio conjunto de características, incluida la [compatibilidad con transacciones](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) y una característica de [detección de duplicados.](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) La cola garantiza "como máximo una entrega por mensaje" por mensaje. Descarta automáticamente un mensaje que ya se ha enviado. Si un productor tiene dudas, puede volver a enviar el mismo mensaje y Service Bus garantiza que solo se procesará una copia. La detección de duplicados le libera de tener que construir plomería de infraestructura adicional.

Otras dos características empresariales son la partición y las sesiones. Una cola de Service Bus convencional se controla mediante un único agente de mensajes y se almacena en un único almacén de mensajes. Sin embargo, [la partición](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) de Service Bus distribuye la cola entre varios agentes de mensajes y almacenes de mensajes. El rendimiento general ya no está limitado por el rendimiento de un único agente de mensajes o almacén de mensajería. Una interrupción temporal de un almacén de mensajería no hace que una cola con particiones no esté disponible.

[Las sesiones](https://codingcanvas.com/azure-service-bus-sessions/) de Service Bus proporcionan una manera de agrupar mensajes. Imagine un escenario de flujo de trabajo donde los mensajes deben procesarse juntos y la operación se debe completar al final. Para aprovecharlas, las sesiones deben habilitarse explícitamente para la cola y cada mensaje relacionado debe contener el mismo identificador de sesión.

Sin embargo, hay algunas advertencias importantes: el tamaño de las colas de Service Bus está limitado a 80 GB, que es mucho más pequeño que lo que está disponible en las colas de almacenamiento. Además, las colas de Service Bus incurren en un costo base y un cargo por operación.

La figura 4-14 describe la arquitectura de alto nivel de una cola de Service Bus.

![Cola de Service Bus](./media/service-bus-queue.png)

**Figura 4-14**. Cola de Service Bus

En la figura anterior, observe la relación punto a punto. Dos instancias del mismo proveedor están encolando mensajes en una sola cola de Service Bus. Cada mensaje es consumido por solo una de las tres instancias de consumidor a la derecha. A continuación, analizamos cómo implementar la mensajería donde diferentes consumidores pueden estar interesados en el mismo mensaje.

## <a name="events"></a>Eventos

La cola de mensajes es una forma eficaz de implementar la comunicación en la que un productor puede enviar un mensaje de forma asincrónica a un consumidor. Sin embargo, ¿qué sucede cuando *muchos consumidores diferentes* están interesados en el mismo mensaje? Una cola de mensajes dedicada para cada consumidor no escalaría bien y se volvería difícil de administrar.

Para abordar este escenario, pasamos al tercer tipo de interacción de mensaje, el *evento*. Un microservicio anuncia que se ha producido una acción. Otros microservicios, si están interesados, reaccionan a la acción o al evento.

Los eventos son un proceso de dos pasos. Para un cambio de estado determinado, un microservicio publica un evento en un agente de mensajes, lo que lo hace disponible para cualquier otro microservicio interesado. El microservicio interesado se notifica suscribiéndose al evento en el agente de mensajes. Utilice el patrón [Publicar/Suscribir](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) se utiliza para implementar la [comunicación basada en eventos.](https://docs.microsoft.com/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/integration-event-based-microservice-communications)

En la figura 4-15 se muestra un microservicio de cesta de la compra que publica un evento con otros dos microservicios que se suscriben a él.

![Mensajería controlada por eventos](./media/event-driven-messaging.png)

**Figura 4-15**. Mensajería controlada por eventos

Observe el componente de bus de *eventos* que se encuentra en el centro del canal de comunicación. Es una clase personalizada que encapsula el agente de mensajes y lo desacopla de la aplicación subyacente. Los microservicios de pedidos e inventario operan el evento de forma independiente sin tener conocimiento el uno del otro, ni el microservicio de la cesta de la compra. Cuando el evento registrado se publica en el bus de eventos, actúan sobre él.

Con eventos, pasamos de la tecnología de cola a *los temas.* Un [tema](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) es similar a una cola, pero admite un patrón de mensajería de uno a varios. Un microservicio publica un mensaje. Varios microservicios de suscripción pueden elegir recibir y actuar según ese mensaje. La Figura 4-16 muestra una arquitectura de tema.

![Arquitectura de temas](./media/topic-architecture.png)

**Figura 4-16**. Arquitectura de temas

En la figura anterior, los editores envían mensajes al tema. Al final, los suscriptores reciben mensajes de suscripciones. En el medio, el tema reenvía los mensajes a las suscripciones en función de un conjunto de *reglas,* que se muestran en cuadros azules oscuros. Las reglas actúan como un filtro que reenvía mensajes específicos a una suscripción. Aquí, se enviaría un evento "CreateOrder" a la Suscripción \#1 y a la Suscripción \#3, pero no a la Suscripción \#2. Se enviará un evento "OrderCompleted" a la Suscripción \#2 y a la Suscripción \#3.

La nube de Azure admite dos servicios de temas diferentes: Temas de Azure Service Bus y Azure EventGrid.

### <a name="azure-service-bus-topics"></a>Azure Service Bus Topics

En la parte superior del mismo modelo de mensajes de intermediario robusto de las colas de Azure Service Bus se encuentran Temas de [Azure Service Bus.](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-how-to-use-topics-subscriptions) Un tema puede recibir mensajes de varios editores independientes y enviar mensajes a hasta 2.000 suscriptores. Las suscripciones se pueden agregar o quitar dinámicamente en tiempo de ejecución sin detener el sistema ni volver a crear el tema.

Muchas características avanzadas de las colas de Azure Service Bus también están disponibles para temas, como Detección de [duplicados](https://docs.microsoft.com/azure/service-bus-messaging/duplicate-detection) y [Compatibilidad con transacciones.](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-transactions) De forma predeterminada, los temas de Service Bus se controlan mediante un único agente de mensajes y se almacenan en un único almacén de mensajes. Sin más, [Service Bus Partitioning](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-partitioning) escala un tema al distribuirlo entre muchos agentes de mensajes y almacenes de mensajes.

[Entrega de mensajes programada](https://docs.microsoft.com/azure/service-bus-messaging/message-sequencing) etiqueta un mensaje con una hora específica para el procesamiento. El mensaje no aparecerá en el tema antes de esa hora. [Aplazamiento de](https://docs.microsoft.com/azure/service-bus-messaging/message-deferral) mensajes le permite aplazar una recuperación de un mensaje a un momento posterior. Ambos se utilizan normalmente en escenarios de procesamiento de flujo de trabajo donde las operaciones se procesan en un orden determinado. Puede posponer el procesamiento de los mensajes recibidos hasta que se haya completado el trabajo anterior.

Los temas de Service Bus son una tecnología sólida y probada para permitir la comunicación de publicación/suscripción en sus sistemas nativos de la nube.

### <a name="azure-event-grid"></a>Azure Event Grid

Aunque Azure Service Bus es un agente de mensajería probado en batalla con un conjunto completo de características empresariales, [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) es el nuevo niño del bloque.

A primera vista, Event Grid puede parecerse a otro sistema de mensajería basado en temas. Sin embargo, es diferente en muchos sentidos. Centrado en cargas de trabajo controladas por eventos, permite el procesamiento de eventos en tiempo real, la integración profunda de Azure y una plataforma abierta, todo en infraestructura sin servidor. Está diseñado para aplicaciones nativas de la nube y sin servidor contemporáneas

Como backplane o *canalización*de eventos centralizados, Event Grid reacciona a eventos dentro de los recursos de Azure y desde sus propios servicios.

Las notificaciones de eventos se publican en un tema de Event Grid, que, a su vez, enruta cada evento a una suscripción. Los suscriptores se asignan a suscripciones y consumen los eventos. Al igual que Service Bus, Event Grid admite un modelo de *suscriptor filtrado* donde una suscripción establece una regla para los eventos que desea recibir. Event Grid proporciona un rendimiento rápido con una garantía de 10 millones de eventos por segundo que permite la entrega casi en tiempo real, mucho más de lo que Azure Service Bus puede generar.

Un punto dulce para Event Grid es su profunda integración en el tejido de la infraestructura de Azure. Un recurso de Azure, como Cosmos DB, puede publicar eventos integrados directamente en otros recursos de Azure interesados, sin necesidad de código personalizado. Event Grid puede publicar eventos desde una suscripción de Azure, un grupo de recursos o un servicio, lo que proporciona a los desarrolladores un control detallado sobre el ciclo de vida de los recursos en la nube. Sin embargo, Event Grid no se limita a Azure., Event Grid is't limited to Azure. Es una plataforma abierta que puede consumir eventos HTTP personalizados publicados desde aplicaciones o servicios de terceros y enrutar eventos a suscriptores externos.

Al publicar y suscribirse a eventos nativos desde recursos de Azure, no se requiere codificación. Con una configuración sencilla, puede integrar eventos de un recurso de Azure a otro aprovechando la plomería integrada para temas y suscripciones. La Figura 4-17 muestra la anatomía de Event Grid.

![Anatomía de Event Grid](./media/event-grid-anatomy.png)

**Figura 4-17**. Anatomía de Event Grid

Una diferencia importante entre EventGrid y Service Bus es el *patrón*de intercambio de mensajes subyacente.

Service Bus implementa un modelo de *extracción* de estilo anterior en el que el suscriptor de nivel inferior sondea activamente la suscripción de tema para los mensajes nuevos. En el lado positivo, este enfoque da al suscriptor el control total del ritmo al que procesa los mensajes. Controla cuándo y cuántos mensajes procesar en un momento dado. Los mensajes no leídos permanecen en la suscripción hasta que se procesan. Una deficiencia significativa es la latencia entre el momento en que se genera el evento y la operación de sondeo que extrae ese mensaje al suscriptor para su procesamiento. Además, la sobrecarga del sondeo constante para el próximo evento consume recursos y dinero.

EventGrid, sin embargo, es diferente. Implementa un modelo de *inserción* en el que los eventos se envían a los EventHandlers tal como se reciben, lo que proporciona una entrega de eventos casi en tiempo real. También reduce el costo, ya que el servicio se desencadena solo cuando es necesario consumir un evento, no continuamente como con el sondeo. Dicho esto, un controlador de eventos debe controlar la carga entrante y proporcionar mecanismos de limitación para protegerse de verse abrumado. Muchos servicios de Azure que consumen estos eventos, como Azure Functions y Logic Apps, proporcionan capacidades de escalado automático para controlar el aumento de las cargas.  

Event Grid es un servicio en la nube sin servidor totalmente administrado. Se escala dinámicamente en función de su tráfico y le cobra solo por su uso real, no por la capacidad precomprada. Las primeras 100.000 operaciones al mes son gratuitas: las operaciones que se definen como entrada de eventos (notificaciones de eventos entrantes), intentos de entrega de suscripciones, llamadas de administración y filtrado por sujeto. Con una disponibilidad del 99,99 %, EventGrid garantiza la entrega de un evento en un período de 24 horas, con funcionalidad de reintento integrada para una entrega sin éxito. Los mensajes no entregados se pueden mover a una cola de "letra muerta" para su resolución.  A diferencia de Azure Service Bus, Event Grid está optimizado para un rendimiento rápido y no admite características como mensajería ordenada, transacciones y sesiones.

### <a name="streaming-messages-in-the-azure-cloud"></a>Transmisión de mensajes en la nube de Azure

Azure Service Bus y Event Grid proporcionan una excelente compatibilidad para las aplicaciones que exponen eventos únicos y discretos, como si se ha insertado un nuevo documento en Cosmos DB. Pero, ¿qué sucede si el sistema nativo de la nube necesita procesar una *secuencia de eventos relacionados?* Las secuencias de eventos son más [complejas.](https://docs.microsoft.com/archive/msdn-magazine/2015/february/microsoft-azure-the-rise-of-event-stream-oriented-systems) Normalmente están ordenados en el tiempo, interrelacionados y deben procesarse como un grupo.

[Azure Event Hub](https://azure.microsoft.com/services/event-hubs/) es una plataforma de streaming de datos y un servicio de ingesta de eventos que recopila, transforma y almacena eventos. Está ajustado para capturar datos de streaming, como notificaciones de eventos continuas emitidas desde un contexto de telemetría. El servicio es altamente escalable y puede almacenar y [procesar millones de eventos por segundo.](https://docs.microsoft.com/azure/event-hubs/event-hubs-about) Se muestra en la Figura 4-18, a menudo es una puerta principal para una tubería de eventos, desacoplando la corriente de ingesta del consumo de eventos.

![Centro de eventos de Azure](./media/azure-event-hub.png)

**Figura 4-18**. Centro de eventos de Azure

Event Hub admite baja latencia y retención de tiempo configurable. A diferencia de las colas y los temas, event Hubs mantienen los datos de eventos después de que un consumidor los haya leído. Esta característica permite que otros servicios analíticos de datos, tanto internos como externos, reproduzcan los datos para su posterior análisis. Los eventos almacenados en el centro de eventos solo se eliminan al expirar el período de retención, que es un día de forma predeterminada, pero configurable.

Event Hub admite protocolos de publicación de eventos comunes, incluidos HTTPS y AMQP. También es compatible con Kafka 1.0. [Las aplicaciones kafka existentes pueden comunicarse con Event Hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview) mediante el protocolo Kafka que proporciona una alternativa a la administración de clústeres kafka grandes. Muchos sistemas nativos de nube de código abierto adoptan Kafka.

Event Hubs implementa el streaming de mensajes a través de un modelo de [consumidor con particiones](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) en el que cada consumidor solo lee un subconjunto o partición específico de la secuencia de mensajes. Este patrón permite una gran escala horizontal para procesamiento de eventos y proporciona otras características centradas en secuencias que no están disponibles en colas y temas. Una partición es una secuencia ordenada de eventos que se mantiene en un centro de eventos. A medida que llegan los eventos más recientes, se agregan al final de esta secuencia.La figura 4-19 muestra la creación de particiones en un centro de eventos.

![Partición del centro de eventos](./media/event-hub-partitioning.png)

**Figura 4-19**. Partición del centro de eventos

En lugar de leer desde el mismo recurso, cada grupo de consumidores lee en un subconjunto o partición de la secuencia de mensajes.

Para las aplicaciones nativas de la nube que deben transmitir un gran número de eventos, Azure Event Hub puede ser una solución sólida y asequible.

>[!div class="step-by-step"]
>[Anterior](front-end-communication.md)
>[Siguiente](grpc.md)
