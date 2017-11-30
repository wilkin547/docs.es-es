---
title: "Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f58d355b6f5fd31a21791d3b072c77f70f90c387
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a><span data-ttu-id="b8884-104">Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba</span><span class="sxs-lookup"><span data-stu-id="b8884-104">Implementing an event bus with RabbitMQ for the development or test environment</span></span>

<span data-ttu-id="b8884-105">Se debe iniciar el diciendo que si crea el bus de eventos personalizado basado en RabbitMQ que se ejecuta en un contenedor, como hace la aplicación eShopOnContainers, debe usarse únicamente para los entornos de prueba y desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b8884-105">We should start by saying that if you create your custom event bus based on RabbitMQ running in a container, as the eShopOnContainers application does, it should be used only for your development and test environments.</span></span> <span data-ttu-id="b8884-106">No se debe usar para el entorno de producción, a menos que se crea como parte de un bus de servicio para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="b8884-106">You should not use it for your production environment, unless you are building it as a part of a production-ready service bus.</span></span> <span data-ttu-id="b8884-107">Un bus de eventos personalizado simple que le falte muchas características críticas para entornos de producción con un bus de servicio comercial.</span><span class="sxs-lookup"><span data-stu-id="b8884-107">A simple custom event bus might be missing many production-ready critical features that a commercial service bus has.</span></span>

<span data-ttu-id="b8884-108">La implementación personalizada de eShopOnContainers de un bus de eventos es básicamente una biblioteca mediante la API de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b8884-108">The eShopOnContainers custom implementation of an event bus is basically a library using the RabbitMQ API.</span></span> <span data-ttu-id="b8884-109">La implementación permite microservicios suscribirse a eventos, puede publicar eventos y recibir eventos, como se muestra en la figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="b8884-109">The implementation lets microservices subscribe to events, publish events, and receive events, as shown in Figure 8-21.</span></span>

![](./media/image22.png)

<span data-ttu-id="b8884-110">**Figura 8-21.**</span><span class="sxs-lookup"><span data-stu-id="b8884-110">**Figure 8-21.**</span></span> <span data-ttu-id="b8884-111">Implementación de RabbitMQ de un bus de eventos</span><span class="sxs-lookup"><span data-stu-id="b8884-111">RabbitMQ implementation of an event bus</span></span>

<span data-ttu-id="b8884-112">En el código, la clase EventBusRabbitMQ implementa la interfaz genérica de IEventBus.</span><span class="sxs-lookup"><span data-stu-id="b8884-112">In the code, the EventBusRabbitMQ class implements the generic IEventBus interface.</span></span> <span data-ttu-id="b8884-113">Esto se basa en la inserción de dependencias para que se pueda cambiar desde esta versión de desarrollo/pruebas a una versión de producción.</span><span class="sxs-lookup"><span data-stu-id="b8884-113">This is based on Dependency Injection so that you can swap from this dev/test version to a production version.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

<span data-ttu-id="b8884-114">La implementación de RabbitMQ de un bus de eventos de desarrollo/pruebas de ejemplo es código reutilizable.</span><span class="sxs-lookup"><span data-stu-id="b8884-114">The RabbitMQ implementation of a sample dev/test event bus is boilerplate code.</span></span> <span data-ttu-id="b8884-115">Tiene que controlar la conexión con el servidor RabbitMQ y proporcione código para la publicación de un evento de mensaje a las colas.</span><span class="sxs-lookup"><span data-stu-id="b8884-115">It has to handle the connection to the RabbitMQ server and provide code for publishing a message event to the queues.</span></span> <span data-ttu-id="b8884-116">También debe implementar un diccionario de las colecciones de controladores de eventos de integración para cada tipo de evento; estos tipos de evento pueden tener una instancia diferente y diferentes suscripciones de cada microservicio receptor, tal como se muestra en la figura 8-21.</span><span class="sxs-lookup"><span data-stu-id="b8884-116">It also has to implement a dictionary of collections of integration event handlers for each event type; these event types can have a different instantiation and different subscriptions for each receiver microservice, as shown in Figure 8-21.</span></span>

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a><span data-ttu-id="b8884-117">Implementar un sencillo método con RabbitMQ de publicación</span><span class="sxs-lookup"><span data-stu-id="b8884-117">Implementing a simple publish method with RabbitMQ</span></span>

<span data-ttu-id="b8884-118">El siguiente código es parte de la implementación del bus de eventos eShopOnContainers para RabbitMQ, por lo que normalmente no es necesario escribir el código, a menos que se están realizando mejoras.</span><span class="sxs-lookup"><span data-stu-id="b8884-118">The following code is part of the eShopOnContainers event bus implementation for RabbitMQ, so you usually do not need to code it unless you are making improvements.</span></span> <span data-ttu-id="b8884-119">El código obtiene una conexión y el canal para RabbitMQ, crea un mensaje y, a continuación, publica el mensaje en la cola.</span><span class="sxs-lookup"><span data-stu-id="b8884-119">The code gets a connection and channel to RabbitMQ, creates a message, and then publishes the message into the queue.</span></span>

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

<span data-ttu-id="b8884-120">El [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) de la publicación se ha mejorado mediante el uso de método en la aplicación de eShopOnContainers un [Polly](https://github.com/App-vNext/Polly) directiva, que vuelve a intentar la tarea de un número determinado de veces en caso de que el contenedor RabbitMQ de reintentos no está listo.</span><span class="sxs-lookup"><span data-stu-id="b8884-120">The [actual code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) of the Publish method in the eShopOnContainers application is improved by using a [Polly](https://github.com/App-vNext/Polly) retry policy, which retries the task a certain number of times in case the RabbitMQ container is not ready.</span></span> <span data-ttu-id="b8884-121">Esto puede ocurrir cuando redacte de docker a partir de los contenedores; Por ejemplo, el contenedor de RabbitMQ puede comenzar más lentamente que los otros contenedores.</span><span class="sxs-lookup"><span data-stu-id="b8884-121">This can occur when docker-compose is starting the containers; for example, the RabbitMQ container might start more slowly than the other containers.</span></span>

<span data-ttu-id="b8884-122">Como se mencionó anteriormente, hay muchas configuraciones posibles en RabbitMQ, por lo que este código debe usarse únicamente para entornos de desarrollo y pruebas.</span><span class="sxs-lookup"><span data-stu-id="b8884-122">As mentioned earlier, there are many possible configurations in RabbitMQ, so this code should be used only for dev/test environments.</span></span>

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a><span data-ttu-id="b8884-123">Implementar el código de suscripción con la API de RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="b8884-123">Implementing the subscription code with the RabbitMQ API</span></span>

<span data-ttu-id="b8884-124">Como con el código de la publicación, el código siguiente es una simplificación de la parte de la implementación del bus de eventos para RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b8884-124">As with the publish code, the following code is a simplification of part of the event bus implementation for RabbitMQ.</span></span> <span data-ttu-id="b8884-125">Una vez más, normalmente no necesitará cambiarla a menos que se mejorarlo.</span><span class="sxs-lookup"><span data-stu-id="b8884-125">Again, you usually do not need to change it unless you are improving it.</span></span>

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Member objects and other methods ...
    // ...
    public void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent
    {
        var eventName = typeof(T).Name;
        if (_handlers.ContainsKey(eventName))
        {
            _handlers[eventName].Add(handler);
        }
        else
        {
            var channel = GetChannel();
            channel.QueueBind(queue: _queueName,
                exchange: _brokerName,
                routingKey: eventName);
            _handlers.Add(eventName, new List<IIntegrationEventHandler>());
            _handlers[eventName].Add(handler);
            _eventTypes.Add(typeof(T));
        }
    }
}
```

<span data-ttu-id="b8884-126">Cada tipo de evento tiene un canal relacionado para obtener eventos de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="b8884-126">Each event type has a related channel to get events from RabbitMQ.</span></span> <span data-ttu-id="b8884-127">A continuación, puede tener tantos controladores de eventos por tipo de canal y de evento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b8884-127">You can then have as many event handlers per channel and event type as needed.</span></span>

<span data-ttu-id="b8884-128">El método Subscribe acepta un objeto IIntegrationEventHandler, que es similar a un método de devolución de llamada en el microservicio actual, además de su objeto IntegrationEvent relacionado.</span><span class="sxs-lookup"><span data-stu-id="b8884-128">The Subscribe method accepts an IIntegrationEventHandler object, which is like a callback method in the current microservice, plus its related IntegrationEvent object.</span></span> <span data-ttu-id="b8884-129">El código, a continuación, agrega ese controlador de eventos a la lista de controladores de eventos que puede tener cada tipo de evento de integración por cliente microservicio.</span><span class="sxs-lookup"><span data-stu-id="b8884-129">The code then adds that event handler to the list of event handlers that each integration event type can have per client microservice.</span></span> <span data-ttu-id="b8884-130">Si el código de cliente ya no se ha suscrito al evento, el código crea un canal para el tipo de evento de forma que pueda recibir eventos en un estilo de inserción de RabbitMQ cuando ese evento se publica desde cualquier otro servicio.</span><span class="sxs-lookup"><span data-stu-id="b8884-130">If the client code has not already been subscribed to the event, the code creates a channel for the event type so it can receive events in a push style from RabbitMQ when that event is published from any other service.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b8884-131">[Anterior] (integración-eventos-según-microservicio-communications.md) [siguiente] (events.md suscribirse)</span><span class="sxs-lookup"><span data-stu-id="b8884-131">[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)</span></span>
