---
title: Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Uso de RabbitMQ para implementar la mensajería de un bus de eventos para entornos de integración con fines de desarrollo de entornos de prueba.
ms.date: 10/02/2018
ms.openlocfilehash: 32259c76fe81d324ba3ea9b35f7fddc6a0f9cdbc
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144297"
---
# <a name="implementing-an-event-bus-with-rabbitmq-for-the-development-or-test-environment"></a>Implementación de un bus de eventos con RabbitMQ para el entorno de desarrollo o de prueba

Para empezar, hay que decir que si crea el bus de eventos personalizado basado en RabbitMQ que se ejecuta en un contenedor, como hace la aplicación eShopOnContainers, debe usarse únicamente para los entornos de desarrollo y prueba. No debe usarlo para el entorno de producción, salvo que lo cree como parte de un bus de servicio para entornos de producción. En un bus de eventos personalizado simple pueden faltar muchas de las características críticas para entornos de producción que tiene un bus de servicio comercial.

Una de las implementaciones personalizadas de bus de eventos en eShopOnContainers es básicamente una biblioteca que usa la API de RabbitMQ. (Hay otra implementación basada en Azure Service Bus).

La implementación del bus de eventos con RabbitMQ permite que los microservicios se suscriban a eventos, los publiquen y los reciban, tal como se muestra en la figura 6-21.

![Diagrama que muestra RabbitMQ entre el remitente y el receptor del mensaje.](./media/rabbitmq-event-bus-development-test-environment/rabbitmq-implementation.png)

**Figura 6-21.** Implementación de RabbitMQ de un bus de eventos

Para controlar la distribución, RabbitMQ funciona como intermediario entre el publicador de mensajes y los suscriptores. En el código, la clase EventBusRabbitMQ implementa la interfaz genérica de IEventBus. Esto se basa en la inserción de dependencias para que pueda cambiar de esta versión de desarrollo/pruebas a una versión de producción.

```csharp
public class EventBusRabbitMQ : IEventBus, IDisposable
{
    // Implementation using RabbitMQ API
    //...
}
```

La implementación de RabbitMQ de un bus de eventos de desarrollo/pruebas de ejemplo es un código reutilizable. Tiene que controlar la conexión con el servidor RabbitMQ y proporcionar código para publicar un evento de mensaje a las colas. También debe implementar un diccionario de las colecciones de controladores de eventos de integración para cada tipo de evento; estos tipos de eventos pueden tener una instancia diferente y diferentes suscripciones para cada microservicio receptor, tal como se muestra en la figura 6-21.

## <a name="implementing-a-simple-publish-method-with-rabbitmq"></a>Implementar un método de publicación sencillo con RabbitMQ

El código siguiente es una versión ***simplificada*** de una implementación de bus de eventos de RabbitMQ con el objetivo de presentar todo el escenario. Lo cierto es que este no es el modo de controlar la conexión. Para ver la implementación completa, consulte el código real en el repositorio [dotnet-architecture/eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.cs).

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

Como se mencionó anteriormente, el bus de eventos implementado en eShopOnContainers solo tiene fines educativos, ya que únicamente controla los escenarios principales y, por tanto, no está listo para la producción.

En escenarios de producción, compruebe los recursos adicionales siguientes, específicos para RabbitMQ, y la sección [Implementación de comunicación basada en eventos entre microservicios](./integration-event-based-microservice-communications.md#additional-resources).

## <a name="additional-resources"></a>Recursos adicionales

Soluciones listas para la producción compatibles con RabbitMQ.

- **EasyNetQ**: cliente de la API de .NET de código abierto para RabbitMQ \
  <https://easynetq.com/>

- **MassTransit** \
  <https://masstransit-project.com/>
  
> [!div class="step-by-step"]
> [Anterior](integration-event-based-microservice-communications.md)
> [Siguiente](subscribe-events.md)
