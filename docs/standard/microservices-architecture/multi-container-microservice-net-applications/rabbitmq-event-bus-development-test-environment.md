---
title: Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: e2b0f1a6152df5d323164fb2eca102fcb973667e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba

Para empezar, hay que decir que si crea el bus de eventos personalizado basado en RabbitMQ que se ejecuta en un contenedor, como hace la aplicación eShopOnContainers, debe usarse únicamente para los entornos de desarrollo y prueba. No debe usarlo para el entorno de producción, salvo que lo cree como parte de un bus de servicio para entornos de producción. En un bus de eventos personalizado simple pueden faltar muchas de las características críticas para entornos de producción que tiene un bus de servicio comercial.

Una de las implementaciones personalizadas de bus de eventos en eShopOnContainers es básicamente una biblioteca que usa la API de RabbitMQ (hay otra implementación basada en Azure Service Bus). 

La implementación del bus de eventos con RabbitMQ permite que los microservicios se suscriban a eventos, los publiquen y los reciban, tal como se muestra en la figura 8-21.

![](./media/image22.png)

**Figura 8-21.** Implementación de RabbitMQ de un bus de eventos

En el código, la clase EventBusRabbitMQ implementa la interfaz genérica de IEventBus. Esto se basa en la inserción de dependencias para que pueda cambiar de esta versión de desarrollo/pruebas a una versión de producción.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
```

La implementación de RabbitMQ de un bus de eventos de desarrollo/pruebas de ejemplo es un código reutilizable. Tiene que controlar la conexión con el servidor RabbitMQ y proporcionar código para publicar un evento de mensaje a las colas. También debe implementar un diccionario de las colecciones de controladores de eventos de integración para cada tipo de evento; estos tipos de eventos pueden tener una instancia diferente y diferentes suscripciones para cada microservicio receptor, tal como se muestra en la figura 8-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementar un método de publicación sencillo con RabbitMQ

El siguiente código es parte de una implementación del bus de eventos simplificada para RabbitMQ, mejorado en el [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) de eShopOnContainers. Normalmente, no es necesario escribir el código, salvo que esté realizando mejoras. El código obtiene una conexión y un canal para RabbitMQ, crea un mensaje y, después, publica el mensaje en la cola.

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

El [código real](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs) del método Publish en la aplicación eShopOnContainers se ha mejorado con una directiva de reintentos de [Polly](https://github.com/App-vNext/Polly), que vuelve a intentar la tarea un número determinado de veces en caso de que el contenedor RabbitMQ no esté listo. Esto puede ocurrir cuando docker-compose inicia los contenedores; por ejemplo, el contenedor de RabbitMQ puede iniciarse más lentamente que los otros contenedores.

Como se ha mencionado anteriormente, hay muchas configuraciones posibles en RabbitMQ, por lo que este código debe usarse únicamente para entornos de desarrollo y pruebas.

## <a name="implementing-the-subscription-code-with-the-rabbitmq-api"></a>Implementar el código de suscripción con la API de RabbitMQ

Al igual que con el código de publicación, el código siguiente es una simplificación de parte de la implementación del bus de eventos para RabbitMQ. Una vez más, normalmente no deberá cambiarlo a menos que lo esté mejorando.

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

Cada tipo de evento tiene un canal relacionado para obtener eventos de RabbitMQ. Puede tener tantos controladores de eventos por tipo de canal y evento como sea necesario.

El método Subscribe acepta un objeto IIntegrationEventHandler, que es similar a un método de devolución de llamada en el microservicio actual, además de su objeto IntegrationEvent relacionado. Después, el código agrega ese controlador de eventos a la lista de controladores de eventos que puede tener cada tipo de evento de integración por microservicio cliente. Si el código cliente ya no se ha suscrito al evento, el código crea un canal para el tipo de evento de forma que pueda recibir eventos en un estilo de inserción de RabbitMQ cuando ese evento se publique desde cualquier otro servicio.


>[!div class="step-by-step"]
[Previous] (integration-event-based-microservice-communications.md) [Next] (subscribe-events.md)
