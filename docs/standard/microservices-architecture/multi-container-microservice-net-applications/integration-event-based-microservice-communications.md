---
title: "Implementación de la comunicación basada en eventos entre microservicios (eventos de integración)"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de la comunicación basada en eventos entre microservicios (eventos de integración)"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e438607ab3549d63b89bef6af64c6723a4cac950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementación de la comunicación basada en eventos entre microservicios (eventos de integración)

Como se describió anteriormente, si utiliza comunicación basado en eventos, un microservicio publica un evento cuando ocurra algo importantes, como cuando actualiza una entidad de negocio. Otros microservicios suscriben a esos eventos. Cuando un microservicio recibe un evento, pueden actualizar sus propio entidades de negocio, lo que podrían dar lugar a más eventos que se está publicados. Este sistema de publicación/suscripción normalmente se realiza mediante una implementación de un bus de eventos. El bus de eventos pueden diseñarse como una interfaz con la API de necesario para suscribir y cancelar la suscripción a eventos y para publicar los eventos. También puede tener uno o más implementaciones basadas en cualquier comunicación entre procesos o mensajería, como una cola de mensajes o un bus de servicio que admite la comunicación asincrónica y un modelo de publicación/suscripción.

Puede usar eventos para implementar las transacciones de negocio que abarcan varios servicios, lo cual proporciona coherencia definitiva entre dichos servicios. Una transacción coherente consta de una serie de acciones distribuidas. En cada acción, el microservicio actualiza una entidad de negocio y publica un evento que desencadena la acción siguiente.

![](./media/image19.PNG)

**Figura 8-18**. Comunicación orientada a eventos en función de un bus de eventos

Esta sección describe cómo puede implementar este tipo de comunicación con .NET mediante el uso de una interfaz de bus de eventos genéricos, como se muestra en la figura 8-18. Hay varias implementaciones posibles, cada uno con una tecnología distinta o infraestructura como RabbitMQ, Bus de servicio de Azure, u otros código abierto de terceros o bus de servicio comercial.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Uso de buses de agentes y servicios de mensaje para sistemas de producción

Como se indicó en la sección de arquitectura, dispone de varias tecnologías de mensajería para implementar el bus de eventos abstractos. Pero estas tecnologías se encuentran en distintos niveles. Por ejemplo, RabbitMQ, un transporte de broker de mensajería, está en un nivel inferior a productos comerciales como Service Bus de Azure, NServiceBus, MassTransit o Brighter. La mayoría de estos productos puede trabajar en la parte superior RabbitMQ o Service Bus de Azure. La selección de producto depende de cuántas características y la escalabilidad de cuánto out-of-the-box necesita para la aplicación.

Para implementar solo una evento bus prueba de concepto para su entorno de desarrollo, como en el ejemplo eShopOnContainers, una implementación sencilla en la parte superior RabbitMQ que se ejecuta como un contenedor puede ser suficiente. Pero para una importancia decisiva y sistemas de producción que necesitan alta escalabilidad, es recomendable evaluar y usar Azure Service Fabric. Si necesita abstracciones de alto nivel y características más enriquecidas como [sagas](https://docs.particular.net/nservicebus/sagas/) para los procesos de larga duración que hacen buses más fácil y otros servicios comerciales y de código abierto como NServiceBus, MassTransit, de desarrollo distribuidos y Son brillantes que vale la pena evaluar. Por supuesto, siempre puede crear sus propias características de bus de servicio sobre tecnologías de nivel inferior como RabbitMQ y Docker, pero el trabajo necesario para inventar la rueda podría ser demasiado costoso para una aplicación de empresa personalizados.

Para reiterar: el abstracciones de bus de eventos de ejemplo y la implementación expuesta en el ejemplo eShopOnContainers están diseñados para usarse solo como una prueba de concepto. Una vez que haya decidido que desea conseguir una comunicación asincrónica y orientada a eventos, como se explica en la sección actual, debe elegir el producto de bus de servicio que mejor se adapte a sus necesidades.

## <a name="integration-events"></a>Eventos de integración

Eventos de integración se utilizan para poner el estado del dominio sincronizada en varios microservicios o sistemas externos. Esto se realiza mediante la publicación de eventos de integración de fuera de la microservicio. Cuando se publica un evento en varios microservicios de receptor (para tantos microservicios tal y como está suscrito al evento de integración), el controlador de eventos apropiado en cada receptor microservicio controla el evento.

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

La clase de eventos de integración puede ser simple; Por ejemplo, es posible que contengan un GUID para su identificador.

Los eventos de integración pueden definirse en el nivel de aplicación de cada microservicio, por lo que se separan de otras microservicios, de forma comparable a cómo ViewModels se definen en el servidor y el cliente. Lo que se recomienda no comparte una biblioteca de eventos de integración comunes entre varios microservicios; hacer se puede acoplar esos microservicios con una biblioteca de datos de la definición de evento único. ¿Desea hacerlo por la misma razón que no desea compartir un modelo de dominio comunes entre varios microservicios: microservicios deben ser completamente autónomo.

Hay solo unos tipos de bibliotecas que deben compartir a través de microservicios. Una es que las bibliotecas que son bloques de aplicación final, al igual que el [API de cliente de Bus de eventos](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), como en eShopOnContainers. Other es bibliotecas que constituyen las herramientas que pudieron compartirse como componentes de NuGet, al igual que los serializadores JSON.

## <a name="the-event-bus"></a>El bus de eventos

Un bus de eventos permite publicar/suscribir-estilo de comunicación entre microservicios sin necesidad de los componentes que desea explícitamente tenga entre sí, tal como se muestra en la figura 8-19.

![](./media/image20.png)

**Figura 8-19**. Aspectos básicos con un bus de eventos de publicación/suscripción

El bus de eventos está relacionado con el patrón de observador y la publicación-suscribirse patrón.

### <a name="observer-pattern"></a>Modelo de observador

En el [modelo observador](https://en.wikipedia.org/wiki/Observer_pattern), su objeto primario (conocido como el objeto Observable) notifica a otros objetos interesados (conocidos como observadores) con la información pertinente (eventos).

### <a name="publish-subscribe-pubsub-pattern"></a>Patrón de publicación y suscripción (Pub/Sub) 

El propósito de la [patrón Pub/Sub](https://msdn.microsoft.com/en-us/library/ff649664.aspx) es el mismo que el modelo de observador: desea notificar a otros servicios cuando determinados eventos tienen lugar. Pero hay una diferencia importante semántica entre los patrones de observador y Pub/Sub. En el patrón de Pub/Sub, el foco está en los mensajes de difusión. En cambio, en el patrón de observador, el Observable no sabe que los eventos se van a, simplemente que hayan out. En otras palabras, el Observable (el publicador) no saber quiénes son los observadores (los suscriptores).

### <a name="the-middleman-or-event-bus"></a>El bus de intermediario o evento 

¿Cómo se consigue anonimato entre el publicador y suscriptor? Una manera fácil es permitir que un intermediario ocuparse de toda la comunicación. Un bus de eventos es uno de estos intermediarios.

Un bus de eventos normalmente se compone de dos partes:

-   La abstracción o la interfaz.

-   Una o varias implementaciones.

En la figura 8-19 puede ver cómo hacerlo, desde un punto de vista de aplicación, el bus de eventos es nada más que un canal de Pub/Sub. Puede modificar la forma de implementar este tipo de comunicación asincrónica. Puede tener varias implementaciones para que se pueden intercambiar entre ellas, dependiendo de los requisitos de entorno (por ejemplo, producción frente a los entornos de desarrollo).

En la figura 8-20 puede ver una abstracción de un bus de eventos con varias implementaciones basadas en la infraestructura de mensajería tecnologías como RabbitMQ, Service Bus de Azure u otros bus de servicio como NServiceBus, MassTransit, etcetera.

![](./media/image21.png)

**Figura 8 - 20.** Varias implementaciones de un bus de eventos

Sin embargo, como se indica anteriormente, con abstracciones (la interfaz de bus de eventos) es posible únicamente si necesita características de bus de eventos básico admitidas por sus abstracciones. Si necesita características más completos del bus de servicio, probablemente debe usar la API proporcionada por el bus de servicio preferido en lugar de sus propio abstracciones.

### <a name="defining-an-event-bus-interface"></a>Define una interfaz de bus de eventos

Comencemos con algún código de implementación para la interfaz de bus de eventos e implementaciones posibles para fines de exploración. La interfaz debe ser sencillo, como se muestra en la siguiente interfaz y no genéricos.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);
    void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T: IntegrationEvent;

    void Unsubscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent;
}
```

El método de publicación es sencillo. El bus de eventos difunden el evento de integración pasado a cualquier microservicio suscrito a ese evento. Este método se usa por la microservicio que está publicando el evento.

El método Subscribe se usa por la microservicios que van a recibir eventos. Este método tiene dos partes. El primero es el evento de integración para suscribirse a (IntegrationEvent). La segunda parte es el controlador de eventos de integración (o el método de devolución de llamada) que se llame a (IIntegrationEventHandler&lt;T&gt;) cuando el microservicio recibe ese mensaje de evento de integración.


>[!div class="step-by-step"]
[Anterior] (base de datos-server-container.md) [siguiente] (rabbitmq-event-bus-development-test-environment.md)
