---
title: "Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3505cb993c736165d4aff4ce8fad38cfa14ed417
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="7012a-104">Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba</span><span class="sxs-lookup"><span data-stu-id="7012a-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="7012a-105">Para empezar, hay que decir que si crea el bus de eventos personalizado basado en RabbitMQ que se ejecuta en un contenedor, como hace la aplicación eShopOnContainers, debe usarse únicamente para los entornos de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="7012a-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="7012a-106">No debe usarlo para el entorno de producción, salvo que lo cree como parte de un bus de servicio para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="7012a-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="7012a-107">En un bus de eventos personalizado simple pueden faltar muchas de las características críticas para entornos de producción que tiene un bus de servicio comercial.</span><span class="sxs-lookup"><span data-stu-id="7012a-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="7012a-108">Una de las implementaciones personalizadas de bus de eventos en eShopOnContainers es básicamente una biblioteca que usa la API de RabbitMQ (hay otra implementación basada en Azure Service Bus).</span><span class="sxs-lookup"><span data-stu-id="7012a-108">One of the event bus custom implementation in eShopOnContainers is basically a library using the RabbitMQ API (There’s another implementation based on Azure Service Bus).</span></span> 

<span data-ttu-id="7012a-109">La implementación del bus de eventos con RabbitMQ permite que los microservicios se suscriban a eventos, los publiquen y los reciban, tal como se muestra en la figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="7012a-109">The event bus implementation with RabbitMQ lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="7012a-110">**Figura 8-21.**</span><span class="sxs-lookup"><span data-stu-id="7012a-110">**Figure 8-21.**</span></span> <span data-ttu-id="7012a-111">Implementación de RabbitMQ de un bus de eventos</span><span class="sxs-lookup"><span data-stu-id="7012a-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="7012a-112">En el código, la clase EventBusRabbitMQ implementa la interfaz genérica de IEventBus.</span><span class="sxs-lookup"><span data-stu-id="7012a-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="7012a-113">Esto se basa en la inserción de dependencias para que pueda cambiar de esta versión de desarrollo/pruebas a una versión de producción.</span><span class="sxs-lookup"><span data-stu-id="7012a-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="7012a-114">La implementación de RabbitMQ de un bus de eventos de desarrollo/pruebas de ejemplo es un código reutilizable.</span><span class="sxs-lookup"><span data-stu-id="7012a-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="7012a-115">Tiene que controlar la conexión con el servidor RabbitMQ y proporcionar código para publicar un evento de mensaje a las colas.</span><span class="sxs-lookup"><span data-stu-id="7012a-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="7012a-116">También debe implementar un diccionario de las colecciones de controladores de eventos de integración para cada tipo de evento; estos tipos de eventos pueden tener una instancia diferente y diferentes suscripciones para cada microservicio receptor, tal como se muestra en la figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="7012a-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="7012a-117">Implementar un método de publicación sencillo con RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="7012a-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="7012a-118">El siguiente código es parte de una implementación del bus de eventos simplificada para RabbitMQ, mejorado en el [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="7012a-118">The following code is part is a simplified event bus implementation for RabbitMQ, improved in the [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of eShopOnContainers.</span></span> <span data-ttu-id="7012a-119">Normalmente, no es necesario escribir el código, salvo que esté realizando mejoras.</span><span class="sxs-lookup"><span data-stu-id="7012a-119">You usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="7012a-120">El código obtiene una conexión y un canal para RabbitMQ, crea un mensaje y, después, publica el mensaje en la cola.</span><span class="sxs-lookup"><span data-stu-id="7012a-120">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Publish(IntegrationEvent @event)
    {
        var eventName = @event.GetType().Name;
        var factory = new ConnectionFactory() { HostName = _connectionString };
        using (var connection = factory.CreateConnection())
        using (var channel = connection.CreateModel())
        {
            channel.ExchangeDeclare(exchange: _brokerName,
                type: "direct");
            string message = JsonConvert.SerializeObject(@event);
            var body = Encoding.UTF8.GetBytes(message);
            channel.BasicPublish(exchange: _brokerName,
                routingKey: eventName,
                basicProperties: null,
                body: body);
       }
    }
}
```

<span data-ttu-id="7012a-121">El [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) del método Publish en la aplicación eShopOnContainers se ha mejorado con una directiva de reintentos de [Polly](https://github.com/App-vNext/Polly), que vuelve a intentar la tarea un número determinado de veces en caso de que el contenedor RabbitMQ no esté listo.</span><span class="sxs-lookup"><span data-stu-id="7012a-121">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="7012a-122">Esto puede ocurrir cuando docker-compose inicia los contenedores; por ejemplo, el contenedor de RabbitMQ puede iniciarse más lentamente que los otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="7012a-122">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="7012a-123">Como se ha mencionado anteriormente, hay muchas configuraciones posibles en RabbitMQ, por lo que este código debe usarse únicamente para entornos de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="7012a-123">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="7012a-124">Implementar el código de suscripción con la API de RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="7012a-124">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="7012a-125">Al igual que con el código de publicación, el código siguiente es una simplificación de parte de la implementación del bus de eventos para RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="7012a-125">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="7012a-126">Una vez más, normalmente no deberá cambiarlo a menos que lo esté mejorando.</span><span class="sxs-lookup"><span data-stu-id="7012a-126">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...

    public void Subscribe<T, TH>()
        where T : IntegrationEvent
        where TH : IIntegrationEventHandler<T>
    {
        var eventName = _subsManager.GetEventKey<T>();
        
        var containsKey = _subsManager.HasSubscriptionsForEvent(eventName);
        if (!containsKey)
        {
            if (!_persistentConnection.IsConnected)
            {
                _persistentConnection.TryConnect();
            }

            using (var channel = _persistentConnection.CreateModel())
            {
                channel.QueueBind(queue: _queueName,
                                    exchange: BROKER_NAME,
                                    routingKey: eventName);
            }
        }

        _subsManager.AddSubscription<T, TH>();
    }
}
```

<span data-ttu-id="7012a-127">Cada tipo de evento tiene un canal relacionado para obtener eventos de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="7012a-127">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="7012a-128">Puede tener tantos controladores de eventos por tipo de canal y evento como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="7012a-128">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="7012a-129">El método Subscribe acepta un objeto IIntegrationEventHandler, que es similar a un método de devolución de llamada en el microservicio actual, además de su objeto IntegrationEvent relacionado.</span><span class="sxs-lookup"><span data-stu-id="7012a-129">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="7012a-130">Después, el código agrega ese controlador de eventos a la lista de controladores de eventos que puede tener cada tipo de evento de integración por microservicio cliente.</span><span class="sxs-lookup"><span data-stu-id="7012a-130">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="7012a-131">Si el código cliente ya no se ha suscrito al evento, el código crea un canal para el tipo de evento de forma que pueda recibir eventos en un estilo de inserción de RabbitMQ cuando ese evento se publique desde cualquier otro servicio.</span><span class="sxs-lookup"><span data-stu-id="7012a-131">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7012a-132">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span><span class="sxs-lookup"><span data-stu-id="7012a-132">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
