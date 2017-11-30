---
title: Suscribirse a eventos
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Suscribirse a eventos
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: fe17b53a39ff2964cd60183e291e2936d3ba28df
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="subscribing-to-events"></a>Suscribirse a eventos

El primer paso para usar el bus de eventos es suscribirse el microservicios a los eventos que se desean recibir. Que debe realizarse en el microservicios de receptor.

El siguiente código simple muestra lo que cada microservicio receptor se debe implementar al iniciar el servicio (es decir, en el inicio de la clase) para que suscribe a los eventos necesita. Por ejemplo, el microservicio basket.api debe suscribirse a mensajes ProductPriceChangedIntegrationEvent. Esto hace que el microservicio consciente de los cambios en el precio del producto y le permite advertir al usuario sobre el cambio si ése es el producto en la cesta de compra del usuario.

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

Después de ejecuta este código, el suscriptor microservicio escucharán a través de canales de RabbitMQ. Cuando llega algún mensaje de tipo ProductPriceChangedIntegrationEvent, el código invoca el controlador de eventos que recibe y procesa el evento.

## <a name="publishing-events-through-the-event-bus"></a>Publicación de eventos a través del bus de eventos

Por último, el remitente del mensaje (origen microservicio) publica los eventos de integración con código similar al ejemplo siguiente. (Esto es un ejemplo simplificado que no tome atomicidad en cuenta). Debería implementar código similar cada vez que un evento se debe difundir a través de varios microservicios, normalmente inmediatamente después de confirmar los datos o transacciones desde el origen de microservicio.

En primer lugar, el objeto de implementación del bus de eventos (basada en RabbitMQ o en un bus de servicio) se insertará en el constructor del controlador, como se muestra en el código siguiente:

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

A continuación, se usa entre métodos de su dispositivo, como en el método UpdateProduct:

```csharp
[Route("update")]
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

En este caso, puesto que la microservicio de origen es un microservicio CRUD simple, ese código se coloca derecha en un controlador de Web API. En microservicios más avanzadas, se puede implementar en la clase CommandHandler, derecho después de que se confirmen los datos originales.

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a>Diseñar la atomicidad y la resistencia al publicar en el bus de eventos

Al publicar eventos de integración a través de un marco de mensajería distribuida sistema al igual que el bus de eventos, tiene el problema de actualización de la base de datos original de forma atómica y publica un evento. Por ejemplo, en el ejemplo simplificado que se muestra anteriormente, el código confirma los datos a la base de datos el precio del producto se cambia y, a continuación, publica un mensaje ProductPriceChangedIntegrationEvent. En principio, puede tener un aspecto fundamental que estas dos operaciones puede realizar de forma atómica. Sin embargo, si está utilizando una transacción distribuida que implican la base de datos y el mensaje de broker, como se hace en sistemas anteriores como [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), no se recomienda por las razones descritas por el [Teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).

Básicamente, use microservicios para crear sistemas de alta disponibilidad y escalables. Simplificar un poco, el teorema CAP indica que no se puede crear una base de datos (o un microservicio que posee su modelo) que está continuamente disponible, muy coherente, *y* tolerante a cualquier otra partición. Debe elegir dos de estas tres propiedades.

En las arquitecturas basadas en microservicios, debe elegir disponibilidad y tolerancia y debe caso homogeneidad. Por lo tanto, en las aplicaciones más modernas basada en microservicio, normalmente no desea usar transacciones distribuidas en mensajería, tal y como haría al implementar [transacciones distribuidas](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) en función de la transacción distribuida de Windows DTC (Coordinador) con [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).

Volvamos a su ejemplo y el problema inicial. Si el servicio se bloquea después de actualiza la base de datos (en este caso, justo después de la línea de código con \_contexto. SaveChangesAsync()), pero antes de que se publica el evento de integración, el sistema global puede volverse incoherente. Esto podría ser empresariales críticas, dependiendo de la operación empresarial específica que está tratando con.

Como se mencionó anteriormente en la sección de arquitectura, puede tener varios enfoques para tratar este problema:

-   La completo [patrón de eventos de origen](https://msdn.microsoft.com/en-us/library/dn589792.aspx).

-   Usar [minería de datos del registro de transacciones](http://www.scoop.it/t/sql-server-transaction-log-mining).

-   Mediante el [patrón de bandeja de salida](http://gistlabs.com/2014/05/the-outbox/). Se trata de una tabla transaccional para almacenar los eventos de integración (extendiendo la transacción local).

En este escenario, utilizando el modelo de origen de evento (ES) completa es uno de los mejores métodos, si no *el* mejor. Sin embargo, en muchas situaciones, es posible que no pueda implementar completa del sistema ES. ES significa almacenar solo los eventos de dominio en la base de datos transaccional, en lugar de almacenar los datos de estado actual. Almacenar solo los eventos de dominio puede tener grandes ventajas, como tener el historial del sistema disponible y ser capaz de determinar el estado del sistema en cualquier momento en el pasado. Sin embargo, la implementación completa del sistema ES requiere que cambie la arquitectura de la mayor parte de su sistema y presenta muchas otras complejidades y requisitos. Por ejemplo, ¿desea usar una base de datos que realizó específicamente para originar el evento, como [almacén de eventos](https://geteventstore.com/), o una base de datos orientada a servicios de documento como base de datos de Azure Cosmos, MongoDB, Casandra, CouchDB o RavenDB. ES es un buen método para este problema, pero no la solución más fácil a menos que ya está familiarizado con el origen de eventos.

La opción para usar el registro de transacciones inicialmente de minería de datos tiene un aspecto muy transparente. Sin embargo, para utilizar este enfoque, el microservicio debe acoplarse en el registro de transacciones de RDBMS, como el registro de transacciones de SQL Server. Esto probablemente no es deseable. Otra desventaja es que las actualizaciones de bajo nivel en el registro de transacciones pueden no ser el mismo nivel que los eventos de integración de alto nivel. Si es así, el proceso de ingeniería inversa esas operaciones de registro de transacciones pueden ser difíciles.

Un enfoque equilibrado es una combinación de una tabla de base de datos transaccional y un patrón ES simplificado. Puede usar un estado como "listo para publicar el evento" que se establece en el evento original cuando se confirma en la tabla de eventos de integración. A continuación, intente publicar el evento en el bus de eventos. Si la acción de evento de publicación se realiza correctamente, inicie otra transacción en el servicio de origen y mover el estado de "listo para publicar el evento" a "evento ya se han publicado".

Si la acción de evento de la publicación de bus en el evento se produce un error, los datos aún no serán incoherentes en la microservicio de origen, se marca como "listo para publicar el evento", y con respecto al resto de los servicios, eventualmente será coherente. Siempre puede tener la comprobación del estado de las transacciones o eventos de integración de trabajos en segundo plano. Si el trabajo encuentra un evento en el estado "listo para publicar el evento", puede intentar volver a publicar ese evento para el bus de eventos.

Tenga en cuenta que con este enfoque, vaya a conservar sólo los eventos de integración para cada microservicio de origen y solo los eventos que desea comunicarse con otros microservicios o sistemas externos. En cambio, en un sistema ES completo, almacenar todos los eventos de dominio.

Por lo tanto, este enfoque equilibrado es un sistema ES simplificado. Se necesita una lista de eventos de integración con su estado actual ("listo para publicar" frente a "publicar"). Pero sólo necesita implementar estos Estados para los eventos de integración. Y en este enfoque, no deberá almacenar todos los datos de dominio como los eventos de la base de datos transaccional, tal y como lo haría en un sistema ES completo.

Si ya se usa una base de datos relacional, puede usar una tabla transaccional para almacenar eventos de integración. Para lograr la atomicidad en la aplicación, utilice un proceso de dos pasos basado en transacciones locales. Básicamente, dispone de una tabla IntegrationEvent en la misma base de datos donde haya las entidades de dominio. Esa tabla funciona como un seguro para lograr la atomicidad para que incluyan guardar eventos de integración en las mismas transacciones que se están confirmando los datos de dominio.

Paso a paso, el proceso se pasa como el siguiente: la aplicación inicia una transacción de base de datos local. A continuación, se actualiza el estado de las entidades de dominio y se inserta un evento en la tabla de eventos de integración. Por último, confirma la transacción. Obtener la atomicidad deseada.

Al implementar los pasos necesarios para publicar los eventos, tienes estas opciones:

-   Publicar el evento integración justo después de confirmar la transacción y usar otra transacción local para marcar los eventos en la tabla que está publicando. A continuación, utilice la tabla al igual que un artefacto para realizar un seguimiento de los eventos de integración en el caso de problemas en el remoto microservicios y realizar acciones de compensación en función de los eventos de integración almacenado.

-   Use la tabla como un tipo de cola. Un proceso o subproceso de aplicación independiente consulta la tabla de eventos de integración, publica los eventos en el bus de eventos y, a continuación, usa una transacción local para marcar los eventos como publicada.

Figura 8-22 muestra la arquitectura para el primero de estos enfoques.

![](./media/image23.png)

**Figura 8-22**. Atomicidad al publicar eventos en el bus de eventos

El enfoque se muestra en la figura 8-22 falta un microservicio trabajo adicional que está a cargo de comprobación y confirmar el éxito de los eventos de integración publicado. En caso de error, ese microservicio de trabajo adicional Comprobador puede leer los eventos de la tabla y volver a publicarlos.

Acerca del segundo enfoque: use la tabla de registro de eventos como una cola y siempre utilizan un microservicio de trabajo para publicar los mensajes. En ese caso, el proceso que se muestra en la figura 8-23. Esto muestra un microservicio adicional y la tabla es el único origen cuando se publica los eventos.

![](./media/image24.png)

**Figura 8-23**. Atomicidad al publicar eventos en el bus de eventos con un microservicio de trabajo

Para simplificar, el ejemplo eShopOnContainers usa el primer enfoque (con no hay procesos adicionales o Comprobador microservicios) junto con el bus de eventos. Sin embargo, la eShopOnContainers no controla todos los casos de error posibles. En una aplicación real que se implementan en la nube, debe adoptar el hecho de que se van a surgir problemas al final, y debe implementar que comprobar y volver a enviar lógica. Con la tabla como una cola puede ser más eficaz que el primer enfoque si tiene esa tabla como un único origen de eventos al publicarlos a través del bus de eventos.

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a>Implementar atomicidad al publicar eventos de integración a través del bus de eventos

El código siguiente muestra cómo puede crear una única transacción que implican varios objetos de DbContext, un contexto relacionado con los datos originales que se está actualizados y el segundo contexto relacionadas con la tabla IntegrationEventLog.

Tenga en cuenta que la transacción en el código de ejemplo siguiente no será resistente a errores si las conexiones a la base de datos tienen algún problema en el momento cuando se ejecuta el código. Esto puede ocurrir en sistemas de servidor basada en la nube como Azure SQL DB, que puede mover bases de datos entre servidores. Para implementar las transacciones resistentes en varios contextos, consulte el [implementar conexiones de Entity Framework Core SQL resistentes](#implementing_resilient_EFCore_SQL_conns) sección más adelante en esta guía.

Para evitar confusiones, en el ejemplo siguiente se muestra todo el proceso en un único fragmento de código. Sin embargo, la implementación de eShopOnContainers realmente se refactoriza y divide esta lógica en varias clases, por lo que es más fácil de mantener.

```csharp
// Update Product from the Catalog microservice
//
public async Task<IActionResult>
    UpdateProduct([FromBody]CatalogItem productToUpdate)
{
    var catalogItem = await _catalogContext.CatalogItems
        .SingleOrDefaultAsync(i => i.Id == productToUpdate.Id);

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

   // Publish to event bus only if product price changed

   if (raiseProductPriceChangedEvent)
   {
       _eventBus.Publish(priceChangedEvent);
       integrationEventLogService.MarkEventAsPublishedAsync(
           priceChangedEvent);
   }

   return Ok();
}
```

Después de crea el evento de integración de ProductPriceChangedIntegrationEvent, la transacción que almacena la operación de dominio original (actualizar el elemento de catálogo) también incluye la persistencia del evento en la tabla de registro de eventos. Esto facilita una única transacción, y siempre podrá comprobar si se envían mensajes de eventos.

La tabla de registro de eventos se actualiza de forma atómica con la operación de base de datos original, usa una transacción local en la misma base de datos. Si se produce un error en cualquiera de las operaciones, se produce una excepción y la transacción revierte cualquier operación completada, lo que mantiene la coherencia entre las operaciones de dominio y los mensajes de eventos enviados.

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a>Recibir mensajes de las suscripciones: controladores de eventos de receptor microservicios

Además de la lógica de suscripción de eventos, debe implementar el código interno para los controladores de eventos de integración (por ejemplo, un método de devolución de llamada). El controlador de eventos es donde se especifican donde se se recibe y procesa los mensajes de eventos de un tipo determinado.

Un controlador de eventos recibe por primera vez una instancia de evento desde el bus de eventos. A continuación, busca el componente para procesarse relacionados con ese evento de integración, propagación y conservar el evento como un cambio de estado en el receptor de microservicio. Por ejemplo, si un evento ProductPriceChanged se origina en el catálogo de microservicio, se controla en el microservicio de la cesta de compras y cambia el estado en este microservicio de la cesta de compras de receptor, tal y como se muestra en el código siguiente.

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

El controlador de eventos debe comprobar si existe el producto en cualquiera de las instancias de la cesta de compra. También actualiza el precio del artículo para cada artículo de línea de la cesta de compra relacionados. Por último, crea una alerta que se mostrará al usuario sobre el cambio de precio, tal como se muestra en la figura 8-24.

![](./media/image25.png)

**Figura 8-24**. Mostrar un cambio de precio de artículo en una cesta comunicado por eventos de integración

## <a name="idempotency-in-update-message-events"></a>Idempotencia en eventos de mensaje de actualización

Un aspecto importante de eventos de mensaje de actualización es que un error en cualquier punto de la comunicación debe hacer que el mensaje que volver a intentarse. En caso contrario, una tarea en segundo plano que pueden intentar publicar un evento que ya se ha publicado, crear una condición de carrera. Es necesario para asegurarse de que las actualizaciones son idempotentes o que proporcionan información suficiente para garantizar que puede detectar un duplicado, descartar los cambios y Enviar atrás solo una respuesta.

Como se indicó anteriormente, Idempotencia significa que una operación se puede realizar varias veces sin cambiar el resultado. En un entorno de mensajería, como cuando se comunica eventos, un evento es idempotente si puede entregarse varias veces sin cambiar el resultado para el receptor de microservicio. Esto puede ser necesario debido a la naturaleza del propio evento, o debido al modo en el sistema controla el evento. Mensaje idempotencia es importante en cualquier aplicación que utilice la mensajería, no solo en las aplicaciones que implementan el patrón de bus de eventos.

Un ejemplo de una operación idempotente es una instrucción SQL que inserta datos en una tabla solo si esos datos no están ya en la tabla. No importa cuántas veces se ejecuta que inserción la instrucción SQL; el resultado será el mismo, la tabla contendrá esos datos. También puede ser idempotencia parecido a esto es necesario cuando se trabaja con mensajes si los mensajes podrían ser potencialmente enviados y, por tanto, procesado más de una vez. Por ejemplo, si la lógica de reintento hace que un remitente enviar exactamente el mismo mensaje más de una vez, tiene que asegurarse de que es idempotente.

Es posible diseño idempotente mensajes. Por ejemplo, puede crear un evento que indica que "establecer el precio del producto \$25" en lugar de "agregar \$5 para el precio del producto." Sin ningún riesgo pudo procesar el primer mensaje de cualquier número de veces y el resultado será el mismo. Esto no es cierto para el segundo mensaje. Pero incluso en el primer caso, no puede procesar el primer evento, porque el sistema también han podido enviar un evento de cambio de precio más recientes y se puede sobrescribir el precio de nuevo.

Otro ejemplo podría ser un evento completado por el orden que se ha propagado a varios suscriptores. Es importante que orden se actualiza la información en otros sistemas de una sola vez, incluso si hay eventos de mensaje duplicado para el mismo evento completado por orden.

Es conveniente tener algún tipo de identidad por evento para que pueda crear lógica que exige que cada evento se procesa solo una vez por cada receptor.

Algún procesamiento de mensajes es idempotente en Sí. Por ejemplo, si un sistema genera imágenes en miniatura, podría ser importante no cuántas veces se procesa el mensaje sobre la miniatura generada; el resultado es que se generan las miniaturas y son iguales cada vez. Por otro lado, las operaciones como llamar a una puerta de enlace de pago que se le cobrará una tarjeta de crédito no pueden ser idempotente en absoluto. En estos casos, debe asegurarse de que procesar un mensaje varias veces tiene el efecto que se espera.

### <a name="additional-resources"></a>Recursos adicionales

-   **Respetando mensaje idempotencia** (subtítulo en esta página) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)

## <a name="deduplicating-integration-event-messages"></a>Desduplicar los mensajes de eventos de integración

Puede asegurarse de que los eventos de mensajes se envían y se procesase sólo una vez por cada suscriptor en niveles diferentes. Una manera es utilizar una característica de desduplicación que ofrece la infraestructura de mensajería que usa. Otro consiste en implementar lógica personalizada en su microservicio de destino. Lo mejor es tener validaciones en el nivel de transporte y el nivel de aplicación.

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a>Desduplicar eventos de mensaje en el nivel de controlador de eventos

Una manera de asegurarse de que un evento se procesa solo una vez por cualquier receptor es implementando cierta lógica al procesar los eventos de mensaje en controladores de eventos. Por ejemplo, que es el enfoque usado en la aplicación eShopOnContainers, como puede ver en la [código fuente](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) de la clase OrdersController cuando recibe un comando CreateOrderCommand. (En este caso se utiliza un comando de solicitud HTTP, no un comando basada en mensajes, pero la lógica que necesita para realizar un comando basada en mensaje idempotente es similar).

### <a name="deduplicating-messages-when-using-rabbitmq"></a>Desduplicar mensajes cuando se usa RabbitMQ

Cuando se producen errores de red intermitentes, se pueden duplicar los mensajes y el receptor del mensaje debe estar listo para controlar estos mensajes duplicados. Si es posible, receptores deben controlar los mensajes de una manera idempotente, lo que es mejor que tratándolos explícitamente con la desduplicación.

Según la [RabbitMQ documentación](https://www.rabbitmq.com/reliability.html#consumer), "si un mensaje se entrega a un consumidor y, a continuación, poner en cola (porque no se ha confirmado antes de quita la conexión del consumidor, por ejemplo), a continuación, RabbitMQ establecerá la marca entregados de nuevo en que se entrega de nuevo (si en el mismo consumidor o uno diferente).

Si se establece la marca "entregados de nuevo", el receptor debe tener en cuenta, ya que es posible ya que se ha procesado el mensaje. Pero que no se garantiza; el mensaje nunca haya alcanzado el receptor después deja al agente de mensajes, quizás debido a problemas de red. Por otro lado, si no se estableció el marcador "entregados de nuevo", se garantiza que el mensaje no se ha enviado más de una vez. Por lo tanto, el receptor debe desduplicar mensajes o procesan los mensajes de una manera idempotente únicamente si se establece la marca "entregados de nuevo" en el mensaje.

### <a name="additional-resources"></a>Recursos adicionales

-   **Evento controlado por mensajería**
    [*http://soapatterns.org/design\_patrones/evento\_controlada por\_de mensajería*](http://soapatterns.org/design_patterns/event_driven_messaging)

-   **Jimmy Bogard. Refactorización hacia resistencia: Evaluación de acoplamiento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)

-   **Canal de la publicación y suscripción**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)

-   **Comunicación entre limitado contextos**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)

-   **Coherencia definitiva**
    [*https://en.wikipedia.org/wiki/Eventual\_coherencia*](https://en.wikipedia.org/wiki/Eventual_consistency)

-   **Philip Brown. Estrategias para integrar limitado contextos**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)

-   **Chris Richardson. Desarrollar Microservicios transaccional con agregados, orígenes de eventos y CQRS - parte 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)

-   **Chris Richardson. Modelo de origen de evento**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)

-   **Introducción a eventos de origen**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)

-   **Base de datos de almacén de eventos**. Sitio oficial.
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   **Patrick Nommensen. Orientadas a eventos administración de datos para Microservicios**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*

-   **El teorema CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)

-   **¿Qué es teorema de extremo? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)

-   **Manual de coherencia de datos**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)

-   **Rick Saling. El teorema CAP: Razón "Todo lo que se diferencian" con la nube e Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)

-   **Eric Brewer. CAP de doce años más tarde: cómo han cambiado las "reglas"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)

-   **Participar en transacciones externas (DTC)** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)

-   **Bus de servicio de Azure. Mensajería asíncrona: Detección de duplicados**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)

-   **Guía de confiabilidad** (documentación de RabbitMQ) [ *https://www.rabbitmq.com/reliability.html\#consumidor*](https://www.rabbitmq.com/reliability.html%23consumer)




>[!div class="step-by-step"]
[Anterior] (rabbitmq-event-bus-development-test-environment.md) [siguiente] (test-aspnet-core-services-web-apps.md)
