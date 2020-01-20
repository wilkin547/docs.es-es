---
title: Implementación de comunicación basada en eventos entre microservicios (eventos de integración)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre los eventos de integración para implementar la comunicación basada en eventos entre microservicios.
ms.date: 10/02/2018
ms.openlocfilehash: 6d4e324a05def91935a82df41c971a75cb75c3f8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712408"
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementación de comunicación basada en eventos entre microservicios (eventos de integración)

Como se describió anteriormente, si utiliza una comunicación basada en eventos, un microservicio publica un evento cuando sucede algo importante, como cuando actualiza una entidad de negocio. Otros microservicios se suscriben a esos eventos. Cuando un microservicio recibe un evento, puede actualizar sus propias entidades de negocio, lo que puede comportar que se publiquen más eventos. Esta es la esencia del concepto de la coherencia final. Este sistema de publicación/suscripción normalmente se realiza mediante una implementación de un bus de eventos. El bus de eventos puede diseñarse como una interfaz con la API necesaria para suscribirse a eventos, cancelar las suscripciones y publicar eventos. También puede tener una o más implementaciones basadas en cualquier comunicación de mensajería o entre procesos, como una cola de mensajes o un bus de servicio que admita la comunicación asincrónica y un modelo de publicación/suscripción.

Puede usar eventos para implementar transacciones de negocio que abarquen varios servicios, lo cual proporciona una eventual coherencia entre dichos servicios. Una eventual transacción coherente consta de una serie de acciones distribuidas. En cada acción, el microservicio actualiza una entidad de negocio y publica un evento que desencadena la siguiente acción. En la figura 6-18 siguiente, se muestra un evento PriceUpdated publicado mediante un bus de eventos para que la actualización de los precios se propague a la cesta y a otros microservicios.

![Diagrama de comunicación asincrónica controlada por eventos con un bus de eventos.](./media/integration-event-based-microservice-communications/event-driven-communication.png)

**Figura 6-18**. Comunicación orientada a eventos basada en un bus de eventos

En esta sección se describe cómo puede implementar este tipo de comunicación con .NET mediante un bus de eventos genéricos, como se muestra en la Figura 6-18. Hay varias implementaciones posibles, cada una de las cuales usa una tecnología o infraestructura distinta, como RabbitMQ, Azure Service Bus o cualquier otro bus de servicio de código abierto de terceros o comercial.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Uso de buses de agentes y servicios de mensajería para sistemas de producción

Como se indicó en la sección de arquitectura, puede escoger entre diferentes tecnologías de mensajería para implementar el bus de eventos abstractos. Pero estas tecnologías se encuentran en distintos niveles. Por ejemplo, RabbitMQ, un transporte de agentes de mensajería, está en un nivel inferior al de productos comerciales como Azure Service Bus, NServiceBus, MassTransit o Brighter. La mayoría de estos productos puede trabajar encima de RabbitMQ o Azure Service Bus. La selección que haga del producto depende de la cantidad de características y de la escalabilidad de serie que necesite para la aplicación.

Para implementar solo una prueba de concepto de bus de eventos para su entorno de desarrollo, como en el ejemplo de eShopOnContainers, una implementación sencilla encima de RabbitMQ ejecutándose como contenedor podría ser suficiente. Pero para sistemas importantes y de producción que necesiten alta escalabilidad, se recomienda evaluar y usar Azure Service Bus.

Si necesita abstracciones de alto nivel y características más potentes, como [Sagas](https://docs.particular.net/nservicebus/sagas/), para procesos de larga duración que faciliten el desarrollo distribuido, vale la pena tener en cuenta otros buses de servicio comerciales y de código abierto, como NServiceBus, MassTransit y Brighter. En este caso, las abstracciones y la API que se van a utilizar suelen ser las proporcionadas directamente por los buses de servicio de alto nivel, en vez de las propias abstracciones (como las [abstracciones de bus de eventos sencillos proporcionadas en eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/BuildingBlocks/EventBus/EventBus/Abstractions/IEventBus.cs)). Con este propósito, puede analizar [eShopOnContainers bifurcado con NServiceBus](https://go.particular.net/eShopOnContainers) (ejemplo derivado adicional implementado por Particular Software).

Obviamente, siempre puede crear sus propias características de bus de servicio sobre tecnologías de nivel inferior, como RabbitMQ y Docker, pero el trabajo necesario para "volver a inventar la rueda" puede ser demasiado costoso para una aplicación de empresa personalizada.

Para reiterar: las abstracciones de bus de eventos de ejemplo y la implementación presentada en el ejemplo de eShopOnContainers están diseñadas para usarse solo como una prueba de concepto. Una vez que haya decidido que quiere tener comunicación asincrónica y controlada por eventos, como se explica en la sección actual, debe elegir el producto de bus de servicio que mejor se adapte a sus necesidades de producción.

## <a name="integration-events"></a>Eventos de integración

Los eventos de integración se utilizan para sincronizar el estado de dominio en varios microservicios o sistemas externos. Esto se realiza mediante la publicación de eventos de integración fuera del microservicio. Cuando se publica un evento en varios microservicios de receptor (en tantos microservicios como estén suscritos al evento de integración), el controlador de eventos correspondiente en cada microservicio de receptor controla el evento.

Un evento de integración es básicamente una clase de almacenamiento de datos, como en el ejemplo siguiente:

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

Los eventos de integración pueden definirse en el nivel de aplicación de cada microservicio, por lo que se separan de otros microservicios de una forma comparable a cómo se define ViewModels en el servidor y en el cliente. Lo que no se recomienda es compartir una biblioteca de eventos de integración común entre varios microservicios. De hacerlo, podría estar acoplando esos microservicios a una biblioteca de datos de definición de eventos únicos. Esto no le interesa por el mismo motivo que no le interesa compartir un modelo de dominio común entre varios microservicios: los microservicios deben ser completamente autónomos.

Solo hay unos cuantos tipos de bibliotecas que debería compartir entre microservicios. Por un lado, las bibliotecas que son bloques de aplicaciones finales, como la [API de cliente de bus de eventos](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), como en eShopOnContainers. Por otro lado, las bibliotecas que constituyen herramientas que también se podrían compartir como componentes de NuGet, igual que los serializadores JSON.

## <a name="the-event-bus"></a>El bus de eventos

Un bus de eventos permite una comunicación de estilo de suscripción/publicación entre microservicios, sin requerir que los componentes se reconozcan entre sí, como se muestra en la Figura 6-19.

![Diagrama que muestra el patrón de publicación/suscripción básico.](./media/integration-event-based-microservice-communications/publish-subscribe-basics.png)

**Figura 6-19**. Aspectos básicos de publicación/suscripción con un bus de eventos

En el diagrama anterior se muestra que el microservicio A se publica en el bus de eventos, que lo distribuye a los microservicios B y C suscritos, sin que el editor tenga que conocer a los suscriptores. El bus de eventos está relacionado con el patrón de observador y con el patrón de publicación/suscripción.

### <a name="observer-pattern"></a>Patrón de observador

En el [patrón de observador](https://en.wikipedia.org/wiki/Observer_pattern), su objeto principal (conocido como "Observable") proporciona información pertinente (eventos) a otros objetos interesados (conocidos como "Observadores").

### <a name="publishsubscribe-pubsub-pattern"></a>Patrón de publicación/suscripción (Pub/Sus)

El propósito del [patrón de publicación/suscripción ](https://docs.microsoft.com/previous-versions/msp-n-p/ff649664(v=pandp.10)) es el mismo que el del modelo de observador: informar a otros servicios de la realización de determinados eventos. Pero hay una diferencia importante entre los patrones Observador y Pub/Sus. En el patrón de observador, la difusión se realiza directamente desde el objeto observable a los observadores, por lo que "se reconocen" entre sí. Pero cuando se usa un patrón Pub/Sus, hay un tercer componente, denominado "agente", "mensaje de agente" o "bus de eventos", que tanto el publicador como el suscriptor conocen. Por lo tanto, al utilizar el patrón Pub/Sus, el publicador y los suscriptores se desvinculan precisamente gracias al bus de eventos o al mensaje de agente mencionados.

### <a name="the-middleman-or-event-bus"></a>El intermediario o bus de eventos

¿Cómo se consigue el anonimato entre el publicador y el suscriptor? Una forma sencilla de hacerlo es permitir que un intermediario se ocupe de toda la comunicación. Un bus de eventos es un intermediario de este tipo.

Normalmente, los buses de eventos están compuestos de dos partes:

- La abstracción o interfaz.

- Una o varias implementaciones.

En la Figura 6-19 puede ver cómo, desde el punto de vista de la aplicación, el bus de eventos no es más que un canal de Pub/Sus. La forma de implementar este tipo de comunicación asincrónica puede variar. Puede tener varias implementaciones para intercambiarlas dependiendo de los requisitos del entorno (por ejemplo, entornos de producción frente a entornos de desarrollo).

En la Figura 6-20 puede ver una abstracción de un bus de eventos con varias implementaciones basadas en tecnologías de mensajería de infraestructura, como RabbitMQ, Azure Service Bus u otro agente de eventos o de mensajería.

![Diagrama que muestra la adición de una capa de abstracción de bus de eventos.](./media/integration-event-based-microservice-communications/multiple-implementations-event-bus.png)

**Figura 6-20**. Varias implementaciones de un bus de eventos

Es conveniente definir el bus de eventos través de una interfaz, de forma que pueda implementarse con varias tecnologías, como RabbitMQ y Azure Service Bus entre otras. Pero, como se ha mencionado anteriormente, usar sus propias abstracciones (la interfaz del bus de eventos) solo es una buena opción si necesita características de bus de eventos compatibles con sus abstracciones. Si necesita características más completas del bus de servicio, probablemente tendrá que usar la API y las abstracciones proporcionadas por el bus de servicio comercial que prefiera, en vez de usar sus propias abstracciones.

### <a name="defining-an-event-bus-interface"></a>Definición de una interfaz de bus de eventos

Comencemos con código de implementación para la interfaz de bus de eventos y las posibles implementaciones para fines de exploración. La interfaz debe ser sencilla y genérica, como la interfaz siguiente.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);

    void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>;

    void SubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void UnsubscribeDynamic<TH>(string eventName)
        where TH : IDynamicIntegrationEventHandler;

    void Unsubscribe<T, TH>()
        where TH : IIntegrationEventHandler<T>
        where T : IntegrationEvent;
}
```

El método `Publish` es sencillo. El bus de eventos difunde el evento de integración que ha recibido a cualquier microservicio, o incluso a una aplicación externa, que se haya suscrito a ese evento. El microservicio que está publicando el evento utiliza este método.

Los microservicios que quieren recibir eventos utilizan los métodos `Subscribe` (puede tener varias implementaciones dependiendo de los argumentos). Este método tiene dos argumentos. El primero es el evento de integración para suscribirse a (`IntegrationEvent`). El segundo es el controlador del evento de integración (o el método de devolución de llamada), denominado `IIntegrationEventHandler<T>`, que se ejecuta cuando el microservicio receptor recibe ese mensaje de evento de integración.

## <a name="additional-resources"></a>Recursos adicionales

Algunas soluciones de mensajería listas para producción:

- **Azure Service Bus** \
  <https://docs.microsoft.com/azure/service-bus-messaging/>
  
- **NServiceBus** \
  <https://particular.net/nservicebus>
  
- **MassTransit** \
  <https://masstransit-project.com/>

> [!div class="step-by-step"]
> [Anterior](database-server-container.md)
> [Siguiente](rabbitmq-event-bus-development-test-environment.md)
