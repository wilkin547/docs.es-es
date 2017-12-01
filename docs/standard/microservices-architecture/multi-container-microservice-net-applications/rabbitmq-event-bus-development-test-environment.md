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
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba

Se debe iniciar el diciendo que si crea el bus de eventos personalizado basado en RabbitMQ que se ejecuta en un contenedor, como hace la aplicación eShopOnContainers, debe usarse únicamente para los entornos de prueba y desarrollo. No se debe usar para el entorno de producción, a menos que se crea como parte de un bus de servicio para entornos de producción. Un bus de eventos personalizado simple que le falte muchas características críticas para entornos de producción con un bus de servicio comercial.

La implementación personalizada de eShopOnContainers de un bus de eventos es básicamente una biblioteca mediante la API de RabbitMQ. La implementación permite microservicios suscribirse a eventos, puede publicar eventos y recibir eventos, como se muestra en la figura 8-21.

![](./media/image22.png)

**Figura 8-21.** Implementación de RabbitMQ de un bus de eventos

En el código, la clase EventBusRabbitMQ implementa la interfaz genérica de IEventBus. Esto se basa en la inserción de dependencias para que se pueda cambiar desde esta versión de desarrollo/pruebas a una versión de producción.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

La implementación de RabbitMQ de un bus de eventos de desarrollo/pruebas de ejemplo es código reutilizable. Tiene que controlar la conexión con el servidor RabbitMQ y proporcione código para la publicación de un evento de mensaje a las colas. También debe implementar un diccionario de las colecciones de controladores de eventos de integración para cada tipo de evento; estos tipos de evento pueden tener una instancia diferente y diferentes suscripciones de cada microservicio receptor, tal como se muestra en la figura 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementar un sencillo método con RabbitMQ de publicación

El siguiente código es parte de la implementación del bus de eventos eShopOnContainers para RabbitMQ, por lo que normalmente no es necesario escribir el código, a menos que se están realizando mejoras. El código obtiene una conexión y el canal para RabbitMQ, crea un mensaje y, a continuación, publica el mensaje en la cola.

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

El [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) de la publicación se ha mejorado mediante el uso de método en la aplicación de eShopOnContainers un [Polly](https://github.com/App-vNext/Polly) directiva, que vuelve a intentar la tarea de un número determinado de veces en caso de que el contenedor RabbitMQ de reintentos no está listo. Esto puede ocurrir cuando redacte de docker a partir de los contenedores; Por ejemplo, el contenedor de RabbitMQ puede comenzar más lentamente que los otros contenedores.

Como se mencionó anteriormente, hay muchas configuraciones posibles en RabbitMQ, por lo que este código debe usarse únicamente para entornos de desarrollo y pruebas.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Implementar el código de suscripción con la API de RabbitMQ

Como con el código de la publicación, el código siguiente es una simplificación de la parte de la implementación del bus de eventos para RabbitMQ. Una vez más, normalmente no necesitará cambiarla a menos que se mejorarlo.

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

Cada tipo de evento tiene un canal relacionado para obtener eventos de RabbitMQ. A continuación, puede tener tantos controladores de eventos por tipo de canal y de evento según sea necesario.

El método Subscribe acepta un objeto IIntegrationEventHandler, que es similar a un método de devolución de llamada en el microservicio actual, además de su objeto IntegrationEvent relacionado. El código, a continuación, agrega ese controlador de eventos a la lista de controladores de eventos que puede tener cada tipo de evento de integración por cliente microservicio. Si el código de cliente ya no se ha suscrito al evento, el código crea un canal para el tipo de evento de forma que pueda recibir eventos en un estilo de inserción de RabbitMQ cuando ese evento se publica desde cualquier otro servicio.


>[!div class="step-by-step"]
[Anterior] (integración-eventos-según-microservicio-communications.md) [siguiente] (events.md suscribirse)
