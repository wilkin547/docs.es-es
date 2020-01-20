---
title: Suscripción a eventos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga más información sobre los detalles de la publicación y la suscripción a eventos de integración.
ms.date: 10/02/2018
ms.openlocfilehash: facbb04d322c5df03498a0313556dd9b5b3161d2
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937147"
---
# <a name="subscribing-to-events"></a>Suscripción a eventos

El primer paso para usar el bus de eventos es suscribir los microservicios a los eventos que quieren recibir. Eso debe realizarse en los microservicios de receptor.

En el siguiente código simple se muestra lo que cada microservicio de receptor debe implementar al iniciar el servicio (es decir, en la clase `Startup`) para que se suscriba a los eventos que necesita. En este caso, el microservicio `basket.api` necesita suscribirse a los mensajes `ProductPriceChangedIntegrationEvent` y `OrderStartedIntegrationEvent`.

Por ejemplo, la suscripción al evento `ProductPriceChangedIntegrationEvent` hace que el microservicio de cesta sea consciente de los cambios en el precio del producto y le permite advertir al usuario sobre el cambio si ese producto está en la cesta de la compra del usuario.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

Después de ejecutar este código, el microservicio de suscriptor escuchará a través de los canales de RabbitMQ. Cuando llega algún mensaje de tipo ProductPriceChangedIntegrationEvent, el código invoca el controlador de eventos que se le pasa y procesa el evento.

## <a name="publishing-events-through-the-event-bus"></a>Publicación de eventos a través del bus de eventos

Por último, el remitente del mensaje (el microservicio de origen) publica los eventos de integración con código similar al del ejemplo siguiente. (Es un ejemplo simplificado que no tiene en cuenta la atomicidad). Debería implementar un código similar cada vez que un evento se tenga que propagar entre varios microservicios, normalmente inmediatamente después de confirmar datos o transacciones desde el microservicio de origen.

En primer lugar, el objeto de implementación del bus de eventos (basado en RabbitMQ o en un Service Bus) se insertará en el constructor del controlador, como se muestra en el código siguiente:

```csharp
[Route("api/v1/[controller]")]
public class CatalogController : ControllerBase
{
    private readonly CatalogContext _context;
    private readonly IOptionsSnapshot<Settings> _settings;
    private readonly IEventBus _eventBus;

    public CatalogController(CatalogContext context,
        IOptionsSnapshot<Settings> settings,
        IEventBus eventBus)
    {
        _context = context;
        _settings = settings;
        _eventBus = eventBus;
    }
    // ...
}
```

Después, se usa desde los métodos del dispositivo, como en el método UpdateProduct:

```csharp
[Route("items")]
[HttpPost]
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem product)
{
    var item = await _context.CatalogItems.SingleOrDefaultAsync(
        i => i.Id == product.Id);
    // ...
    if (item.Price != product.Price)
    {
        var oldPrice = item.Price;
        item.Price = product.Price;
        _context.CatalogItems.Update(item);
        var @event = new ProductPriceChangedIntegrationEvent(item.Id,
            item.Price,
            oldPrice);
        // Commit changes in original transaction
        await _context.SaveChangesAsync();
        // Publish integration event to the event bus
        // (RabbitMQ or a service bus underneath)
        _eventBus.Publish(@event);
        // ...
    }
    // ...
}
```

En este caso, como el microservicio de origen es un microservicio CRUD simple, ese código se coloca directamente en un controlador de API web.

En microservicios más avanzados, como cuando se usan enfoques de CQRS, se puede implementar en la clase `CommandHandler`, dentro del método `Handle()`.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>Diseño de la atomicidad y la resistencia al publicar en el bus de eventos

Al publicar eventos de integración a través de un sistema de mensajería distribuido como el bus de eventos, tiene el problema de actualizar la base de datos original de forma atómica y de publicar un evento (es decir, se completan las dos operaciones o ninguna de ellas). Por ejemplo, en el ejemplo simplificado mostrado anteriormente, el código confirma los datos en la base de datos cuando cambia el precio del producto y, después, publica un mensaje ProductPriceChangedIntegrationEvent. En principio, es posible que parezca fundamental que estas dos operaciones se realicen de forma atómica. Pero si está usando una transacción distribuida que implique la base de datos y el agente de mensajes, como se hace en sistemas anteriores como [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), no se recomienda por las razones descritas por el [Teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).

Básicamente, los microservicios se usan para crear sistemas escalables y de alta disponibilidad. Para simplificarlo de algún modo, el teorema CAP afirma que no se puede crear una base de datos (distribuida), o un microservicio que posea su modelo, que esté continuamente disponible, tenga coherencia fuerte *y* sea tolerante a cualquier partición. Debe elegir dos de estas tres propiedades.

En las arquitecturas basadas en microservicios, debe elegir la disponibilidad y la tolerancia, y quitar énfasis a la coherencia fuerte. Por tanto, en las aplicaciones basadas en microservicios más modernas, normalmente no le interesará usar transacciones distribuidas en la mensajería, como haría al implementar [transacciones distribuidas](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) basadas en el Coordinador de transacciones distribuidas (DTC) de Windows con [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).

Volvamos al problema inicial y su ejemplo. Si el servicio se bloquea después de que se actualice la base de datos (en este caso, justo después de la línea de código con \_context.SaveChangesAsync()) pero antes de que se publique el evento de integración, el sistema global puede volverse incoherente. Esto podría ser crítico para la empresa, según la operación empresarial específica con la que se esté tratando.

Como se mencionó anteriormente en la sección sobre arquitectura, puede tener varios enfoques para solucionar este problema:

- Uso del [patrón de orígenes de eventos](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) completo.

- Uso de la [minería del registro de transacciones](https://www.scoop.it/t/sql-server-transaction-log-mining).

- Uso del [patrón de bandeja de salida](https://www.kamilgrzybek.com/design/the-outbox-pattern/). Se trata de una tabla transaccional para almacenar los eventos de integración (extendiendo la transacción local).

En este escenario, el uso del modelo de orígenes de evento (ES) completo es uno de los mejores métodos, si no *el* mejor. Pero en muchas situaciones, es posible que no pueda implementar un sistema de ES completo. Con los orígenes de evento solo se almacenan los eventos de dominio en la base de datos transaccional, en lugar de almacenar los datos de estado actuales. Almacenar solo los eventos de dominio puede tener grandes ventajas, como tener el historial del sistema disponible y poder determinar el estado del sistema en cualquier momento del pasado. Pero la implementación de un sistema de ES completo requiere que se cambie la arquitectura de la mayor parte del sistema y presenta otras muchas complejidades y requisitos. Por ejemplo, le interesaría usar una base de datos creada específicamente para los orígenes de eventos, como [Event Store](https://eventstore.org/), o bien una base de datos orientada a documentos como Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB. Los orígenes de evento son un buen enfoque para este problema, pero no es la solución más sencilla a menos que ya esté familiarizado con los orígenes de eventos.

La opción de usar la minería del registro de transacciones parece muy transparente en un principio. Pero para usar este enfoque, el microservicio debe acoplarse al registro de transacciones de RDBMS, como el registro de transacciones de SQL Server. Esto probablemente no sea deseable. Otra desventaja es que es posible que las actualizaciones de bajo nivel en el registro de transacciones no estén al mismo nivel que los eventos de integración generales. En ese caso, el proceso de utilización de técnicas de ingeniería inversa en esas operaciones de registro de transacciones puede ser complicado.

Un enfoque equilibrado es una combinación de una tabla de base de datos transaccional y un patrón de ES simplificado. Puede usar un estado como "listo para publicar el evento" que se establece en el evento original cuando se confirma en la tabla de eventos de integración. Después, intente publicar el evento en el bus de eventos. Si la acción de publicación de evento se realiza correctamente, inicie otra transacción en el servicio de origen y cambie el estado de "listo para publicar el evento" a "evento ya publicado".

Si se produce un error en la acción de publicación del evento en el bus de eventos, los datos todavía no serán incoherentes en el microservicio de origen (seguirán marcados como "listo para publicar el evento") y, con respecto al resto de los servicios, eventualmente serán coherentes. Siempre puede tener trabajos en segundo plano que comprueben el estado de las transacciones o los eventos de integración. Si el trabajo encuentra un evento en el estado "listo para publicar el evento", puede intentar volver a publicarlo en el bus de eventos.

Tenga en cuenta que, con este enfoque, solo se conservan los eventos de integración para cada microservicio de origen y solo los eventos que le interesa comunicar con otros microservicios o sistemas externos. Por el contrario, en un sistema de ES completo, también se almacenan todos los eventos de dominio.

Por tanto, este enfoque equilibrado es un sistema de ES simplificado. Necesita una lista de eventos de integración con su estado actual ("listo para publicar" frente a "publicado"). Pero solo tiene que implementar estos estados para los eventos de integración. Y en este enfoque, no tendrá que almacenar todos los datos de dominio como eventos en la base de datos transaccional, tal y como haría en un sistema de ES completo.

Si ya usa una base de datos relacional, puede usar una tabla transaccional para almacenar los eventos de integración. Para lograr la atomicidad en la aplicación, se usa un proceso de dos pasos basado en transacciones locales. Básicamente, dispone de una tabla IntegrationEvent en la misma base de datos donde se encuentren las entidades de dominio. Esa tabla funciona como un seguro para lograr la atomicidad, de modo que los eventos de integración guardados se incluyan en las mismas transacciones con las que se confirman los datos de dominio.

Paso a paso, el proceso es el siguiente:

1. La aplicación inicia una transacción de base de datos local.

2. Después, actualiza el estado de las entidades de dominio e inserta un evento en la tabla de eventos de integración.

3. Finalmente, confirma la transacción, por lo que obtiene la atomicidad deseada.

4. A continuación, publique el evento de algún modo.

Al implementar los pasos necesarios para publicar los eventos, dispone de las opciones siguientes:

- Publicar el evento de integración justo después de confirmar la transacción y usar otra transacción local para marcar los eventos en la tabla como "en proceso de publicación". Después, usar la tabla como si fuera un artefacto para realizar el seguimiento de los eventos de integración en el caso de que se produzcan problemas en los microservicios remotos y realizar acciones de compensación en función de los eventos de integración almacenados.

- Usar la tabla como una especie de cola. Un proceso o subproceso de aplicación independiente consulta la tabla de eventos de integración, publica los eventos en el bus de eventos y, después, usa una transacción local para marcar los eventos como publicados.

En la figura 6-22 se muestra la arquitectura para el primero de estos enfoques.

![Diagrama de atomicidad cuando se publica sin un microservicio de trabajo.](./media/subscribe-events/atomicity-publish-event-bus.png)

**Figura 6-22**. Atomicidad al publicar eventos en el bus de eventos

En el enfoque que se muestra en la figura 6-22 falta un microservicio de trabajo adicional que se encarga de comprobar y confirmar que los eventos de integración se han publicado correctamente. En caso de error, ese microservicio de trabajo de comprobación adicional puede leer los eventos de la tabla y volver a publicarlos, es decir, repetir el paso 2.

Sobre el segundo enfoque: se usa la tabla EventLog como una cola y siempre se usa un microservicio de trabajo para publicar los mensajes. En ese caso, el proceso es similar al que se muestra en la figura 6-23. Esto muestra un microservicio adicional y la tabla es el único origen cuando se publican los eventos.

![Diagrama de atomicidad cuando se publica con un microservicio de trabajo.](./media/subscribe-events/atomicity-publish-worker-microservice.png)

**Figura 6-23**. Atomicidad al publicar eventos en el bus de eventos con un microservicio de trabajo

Para simplificar, en el ejemplo eShopOnContainers se usa el primer enfoque (sin procesos adicionales ni microservicios de comprobador) junto con el bus de eventos. Pero en eShopOnContainers no se controlan todos los casos de error posibles. En una aplicación real implementada en la nube, debe asumir el hecho de que con el tiempo van a surgir problemas, y debe implementar esa lógica de comprobación y reenvío. El uso de la tabla como una cola puede ser más eficaz que el primer enfoque si tiene esa tabla como un único origen de eventos cuando los publica (con el trabajo) a través del bus de eventos.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>Implementación de la atomicidad al publicar eventos de integración a través del bus de eventos

En el código siguiente se muestra la forma de crear una única transacción que implica varios objetos DbContext, un contexto relacionado con los datos originales que se van a actualizar y el segundo relacionado con la tabla IntegrationEventLog.

Tenga en cuenta que la transacción en el código de ejemplo siguiente no será resistente si las conexiones a la base de datos tienen algún problema cuando se ejecute el código. Esto puede ocurrir en sistemas de servidor basados en la nube como Azure SQL DB, en los que es posible que las bases de datos se muevan entre servidores. Para implementar transacciones resistentes entre varios contextos, vea la sección [Implementación de conexiones resistentes de Entity Framework Core SQL](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) más adelante en esta guía.

Para evitar confusiones, en el ejemplo siguiente se muestra el proceso completo en un único fragmento de código. Pero la implementación de eShopOnContainers realmente se refactoriza y divide esta lógica en varias clases para que sea más fácil de mantener.

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult> UpdateProduct([FromBody]CatalogItem productToUpdate)
{
  var catalogItem =
       await _catalogContext.CatalogItems.SingleOrDefaultAsync(i => i.Id ==
                                                               productToUpdate.Id);
  if (catalogItem == null) return NotFound();

  bool raiseProductPriceChangedEvent = false;
  IntegrationEvent priceChangedEvent = null;

  if (catalogItem.Price != productToUpdate.Price)
          raiseProductPriceChangedEvent = true;

  if (raiseProductPriceChangedEvent) // Create event if price has changed
  {
      var oldPrice = catalogItem.Price;
      priceChangedEvent = new ProductPriceChangedIntegrationEvent(catalogItem.Id,
                                                                  productToUpdate.Price,
                                                                  oldPrice);
  }
  // Update current product
  catalogItem = productToUpdate;

  // Just save the updated product if the Product's Price hasn't changed.
  if (!raiseProductPriceChangedEvent)
  {
      await _catalogContext.SaveChangesAsync();
  }
  else  // Publish to event bus only if product price changed
  {
        // Achieving atomicity between original DB and the IntegrationEventLog
        // with a local transaction
        using (var transaction = _catalogContext.Database.BeginTransaction())
        {
           _catalogContext.CatalogItems.Update(catalogItem);
           await _catalogContext.SaveChangesAsync();

           // Save to EventLog only if product price changed
           if(raiseProductPriceChangedEvent)
               await _integrationEventLogService.SaveEventAsync(priceChangedEvent);

           transaction.Commit();
        }

      // Publish the integration event through the event bus
      _eventBus.Publish(priceChangedEvent);

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

Después de crear el evento de integración ProductPriceChangedIntegrationEvent, la transacción que almacena la operación de dominio original (la actualización del elemento de catálogo) también incluye la persistencia del evento en la tabla EventLog. Esto crea una única transacción y siempre se podrá comprobar si los mensajes de eventos se han enviado.

La tabla de registro de eventos se actualiza de forma atómica con la operación de base de datos original, mediante una transacción local en la misma base de datos. Si se produce un error en cualquiera de las operaciones, se inicia una excepción y la transacción revierte cualquier operación completada, lo que mantiene la coherencia entre las operaciones de dominio y los mensajes de eventos que se guardan en la tabla.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>Recepción de mensajes desde suscripciones: controladores de eventos en microservicios de receptor

Además de la lógica de suscripción de eventos, debe implementar el código interno para los controladores de eventos de integración (por ejemplo, un método de devolución de llamada). En el controlador de eventos se especifica dónde se reciben y procesan los mensajes de eventos de un tipo determinado.

Un controlador de eventos recibe por primera vez una instancia de evento desde el bus de eventos. Después, busca el componente que se va a procesar relacionado con ese evento de integración y lo propaga y conserva como un cambio de estado en el microservicio de receptor. Por ejemplo, si un evento ProductPriceChanged se origina en el microservicio de catálogo, se controla en el microservicio de cesta de la compra y también cambia el estado en este microservicio de receptor, como se muestra en el código siguiente.

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.IntegrationEvents.EventHandling
{
    public class ProductPriceChangedIntegrationEventHandler :
        IIntegrationEventHandler<ProductPriceChangedIntegrationEvent>
    {
        private readonly IBasketRepository _repository;

        public ProductPriceChangedIntegrationEventHandler(
            IBasketRepository repository)
        {
            _repository = repository;
        }

        public async Task Handle(ProductPriceChangedIntegrationEvent @event)
        {
            var userIds = await _repository.GetUsers();
            foreach (var id in userIds)
            {
                var basket = await _repository.GetBasket(id);
                await UpdatePriceInBasketItems(@event.ProductId, @event.NewPrice, basket);
            }
        }

        private async Task UpdatePriceInBasketItems(int productId, decimal newPrice,
            CustomerBasket basket)
        {
            var itemsToUpdate = basket?.Items?.Where(x => int.Parse(x.ProductId) ==
                productId).ToList();
            if (itemsToUpdate != null)
            {
                foreach (var item in itemsToUpdate)
                {
                    if(item.UnitPrice != newPrice)
                    {
                        var originalPrice = item.UnitPrice;
                        item.UnitPrice = newPrice;
                        item.OldUnitPrice = originalPrice;
                    }
                }
                await _repository.UpdateBasket(basket);
            }
        }
    }
}
```

El controlador de eventos debe comprobar si el producto existe en cualquiera de las instancias de la cesta de la compra. También actualiza el precio del artículo para cada artículo de línea de la cesta de la compra relacionado. Por último, crea una alerta que se mostrará al usuario sobre el cambio de precio, como se muestra en la figura 6-24.

![Captura de pantalla de un explorador que muestra la notificación de cambio de precio en el carro del usuario.](./media/subscribe-events/display-item-price-change.png)

**Figura 6-24**. Representación de un cambio del precio de un artículo en una cesta, comunicado por eventos de integración

## <a name="idempotency-in-update-message-events"></a>Idempotencia en los eventos de mensajes de actualización

Un aspecto importante de los eventos de mensaje de actualización es que un error en cualquier punto de la comunicación debe hacer que se vuelva a intentar el mensaje. En caso contrario, es posible que una tarea en segundo plano intente publicar un evento que ya se ha publicado, lo que genera una condición de carrera. Es necesario asegurarse de que las actualizaciones son idempotentes o que proporcionan información suficiente para garantizar que un duplicado se pueda detectar, descartarlo y devolver una sola respuesta.

Como se indicó anteriormente, idempotencia significa que una operación se puede realizar varias veces sin cambiar el resultado. En un entorno de mensajería, como al comunicar eventos, un evento es idempotente si se puede entregar varias veces sin cambiar el resultado del microservicio receptor. Esto puede ser necesario debido a la naturaleza del propio evento, o bien al modo en que el sistema controla el evento. La idempotencia de mensajes es importante en cualquier aplicación en la que se use la mensajería, no solo en las aplicaciones que implementan el patrón de bus de eventos.

Un ejemplo de una operación idempotente es una instrucción SQL que inserta datos en una tabla solo si esos datos no están ya en la tabla. No importa cuántas veces se ejecute esa instrucción SQL de inserción; el resultado será el mismo: la tabla contendrá esos datos. Este tipo de idempotencia también puede ser necesaria cuando se trabaja con mensajes si existe la posibilidad de que se envíen y, por tanto, se procesen más de una vez. Por ejemplo, si la lógica de reintento hace que un remitente envíe exactamente el mismo mensaje más de una vez, tendrá que asegurarse de que sea idempotente.

Se pueden diseñar mensajes idempotentes. Por ejemplo, puede crear un evento que indique "establecer el precio del producto en 25 USD" en lugar de "sumar 5 USD al precio del producto". Podría procesar sin riesgos el primer mensaje cualquier número de veces y el resultado sería el mismo. Esto no es cierto para el segundo mensaje. Pero incluso en el primer caso, es posible que no le interese procesar el primer evento, porque el sistema también podría haber enviado un evento de cambio de precio más reciente y se podría sobrescribir el precio de nuevo.

Otro ejemplo podría ser un evento de pedido completado que se propaga a varios suscriptores. Es importante que la información del pedido se actualice una sola vez en otros sistemas, incluso si hay eventos de mensaje duplicados para el mismo evento de pedido completado.

Es conveniente tener algún tipo de identidad por evento para poder crear lógica que exija que cada evento se procese solo una vez por cada receptor.

Algún procesamiento de mensajes es idempotente de forma inherente. Por ejemplo, si un sistema genera imágenes en miniatura, es posible que no importe cuántas veces se procesa el mensaje sobre la miniatura generada; el resultado es que las miniaturas se generan y son iguales cada vez. Por otra parte, las operaciones como la llamada a una pasarela de pagos para cobrar una tarjeta de crédito no pueden ser idempotentes. En estos casos, debe asegurarse de que el procesamiento repetido de un mensaje tiene el efecto que se espera.

### <a name="additional-resources"></a>Recursos adicionales

- **Honoring message idempotency** (Respeto de la idempotencia de los mensajes)  
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a>Desduplicación de mensajes de eventos de integración

Puede asegurarse de que los eventos de mensajes se envían y se procesan una sola vez por cada suscriptor en niveles diferentes. Una manera de hacerlo consiste en usar una característica de desduplicación que ofrece la infraestructura de mensajería en uso. Otra consiste en implementar lógica personalizada en el microservicio de destino. Lo mejor es tener validaciones en el nivel de transporte y el nivel de aplicación.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>Desduplicación de eventos de mensaje en el nivel de controlador de eventos

Una manera de asegurarse de que un evento se procesa solo una vez por cualquier receptor es mediante la implementación de cierta lógica al procesar los eventos de mensaje en controladores de eventos. Por ejemplo, ese es el enfoque que se usa en la aplicación eShopOnContainers, como se aprecia en el [código fuente de la clase UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) cuando recibe un evento de integración UserCheckoutAcceptedIntegrationEvent. (En este caso se encapsula CreateOrderCommand con un elemento IdentifiedCommand, usando eventMsg.RequestId como un identificador, antes de enviarlo al controlador de comandos).

### <a name="deduplicating-messages-when-using-rabbitmq"></a>Desduplicación de mensajes cuando se usa RabbitMQ

Cuando se producen errores de red intermitentes, los mensajes se pueden duplicar y el receptor del mensaje debe estar listo para controlar estos mensajes duplicados. Si es posible, los receptores deben controlar los mensajes de una manera idempotente, lo que es mejor que controlarlos de forma explícita mediante desduplicación.

Según la [documentación de RabbitMQ](https://www.rabbitmq.com/reliability.html#consumer), "si un mensaje se entrega a un consumidor y después se vuelve a poner en la cola (porque no se confirmó antes de desconectar la conexión del consumidor, por ejemplo), RabbitMQ establecerá la marca "entregado de nuevo" cuando se vuelva a entregar (con independencia de que sea al mismo consumidor o a otro)".

Si se establece la marca "entregado de nuevo", el receptor debe tenerlo en cuenta, dado que es posible que el mensaje ya se haya procesado. Pero eso no está garantizado; es posible que el mensaje nunca llegara al receptor después de salir del agente de mensajes, quizás debido a problemas de red. Por otro lado, si no se estableció la marca "entregado de nuevo", se garantiza que el mensaje no se ha enviado más de una vez. Por tanto, el receptor debe desduplicar o procesar los mensajes de una manera idempotente solo si se establece la marca "entregado de nuevo" en el mensaje.

### <a name="additional-resources"></a>Recursos adicionales

- **Bifurcación de eShopOnContainers mediante NServiceBus [Particular Software]**  \
    <https://go.particular.net/eShopOnContainers>

- **Mensajería controlada por eventos** \
    <https://patterns.arcitura.com/soa-patterns/design_patterns/event_driven_messaging>

- **Jimmy Bogard. Refactorización hacia la resiliencia: evaluación del acoplamiento** \
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- **Canal de publicación y suscripción** \
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- **Comunicación entre contextos delimitados** \
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- **Coherencia de los eventos** \
    [https://en.wikipedia.org/wiki/Eventual\_consistency](https://en.wikipedia.org/wiki/Eventual_consistency)

- **Philip Brown. Estrategias para la integración de contextos delimitados** \
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- **Chris Richardson. Desarrollo de microservicios transaccionales mediante agregados, orígenes de eventos y CQRS: parte 2** \
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- **Chris Richardson. Patrón de orígenes de eventos** \
    <https://microservices.io/patterns/data/event-sourcing.html>

- **Introducción a los orígenes de eventos** \
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- **Base de datos Event Store**. Sitio oficial. \
    <https://geteventstore.com/>

- **Patrick Nommensen. Administración de datos orientada a eventos para microservicios** \
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- **Teorema CAP** \
    [https://en.wikipedia.org/wiki/CAP\_theorem](https://en.wikipedia.org/wiki/CAP_theorem)

- **¿Qué es el teorema CAP?** \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- **Manual de coherencia de datos** \
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- **Rick Saling. Teorema CAP: por qué "todo es diferente" con la nube e Internet** \
    <https://docs.microsoft.com/archive/blogs/rickatmicrosoft/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- **Eric Brewer. ¿cómo han cambiado las "normas"? CAP doce años más tarde:**  \
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- **Azure Service Bus. Mensajería asincrónica: Detección de duplicados**  \
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- **Guía de confiabilidad**[documentación de RabbitMQ] \
    [https://www.rabbitmq.com/reliability.html\#consumer](https://www.rabbitmq.com/reliability.html#consumer)

> [!div class="step-by-step"]
> [Anterior](rabbitmq-event-bus-development-test-environment.md)
> [Siguiente](test-aspnet-core-services-web-apps.md)
