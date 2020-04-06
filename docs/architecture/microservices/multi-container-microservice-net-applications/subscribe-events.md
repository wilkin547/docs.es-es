---
title: Suscripción a eventos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga más información sobre los detalles de la publicación y la suscripción a eventos de integración.
ms.date: 01/30/2020
ms.openlocfilehash: 3bfcdb1766a15b1a8e8deab46055f14e1791c2cc
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523592"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="d0fec-103">Suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-103">Subscribing to events</span></span>

<span data-ttu-id="d0fec-104">El primer paso para usar el bus de eventos es suscribir los microservicios a los eventos que quieren recibir.</span><span class="sxs-lookup"><span data-stu-id="d0fec-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="d0fec-105">Eso debe realizarse en los microservicios de receptor.</span><span class="sxs-lookup"><span data-stu-id="d0fec-105">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="d0fec-106">En el siguiente código simple se muestra lo que cada microservicio de receptor debe implementar al iniciar el servicio (es decir, en la clase `Startup`) para que se suscriba a los eventos que necesita.</span><span class="sxs-lookup"><span data-stu-id="d0fec-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="d0fec-107">En este caso, el microservicio `basket-api` necesita suscribirse a los mensajes `ProductPriceChangedIntegrationEvent` y `OrderStartedIntegrationEvent`.</span><span class="sxs-lookup"><span data-stu-id="d0fec-107">In this case, the `basket-api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span>

<span data-ttu-id="d0fec-108">Por ejemplo, la suscripción al evento `ProductPriceChangedIntegrationEvent` hace que el microservicio de cesta sea consciente de los cambios en el precio del producto y le permite advertir al usuario sobre el cambio si ese producto está en la cesta de la compra del usuario.</span><span class="sxs-lookup"><span data-stu-id="d0fec-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent,
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent,
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="d0fec-109">Después de ejecutar este código, el microservicio de suscriptor escuchará a través de los canales de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="d0fec-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="d0fec-110">Cuando llega algún mensaje de tipo ProductPriceChangedIntegrationEvent, el código invoca el controlador de eventos que se le pasa y procesa el evento.</span><span class="sxs-lookup"><span data-stu-id="d0fec-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="d0fec-111">Publicación de eventos a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-111">Publishing events through the event bus</span></span>

<span data-ttu-id="d0fec-112">Por último, el remitente del mensaje (el microservicio de origen) publica los eventos de integración con código similar al del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="d0fec-113">(Es un ejemplo simplificado que no tiene en cuenta la atomicidad). Debería implementar un código similar cada vez que un evento se tenga que propagar entre varios microservicios, normalmente inmediatamente después de confirmar datos o transacciones desde el microservicio de origen.</span><span class="sxs-lookup"><span data-stu-id="d0fec-113">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="d0fec-114">En primer lugar, el objeto de implementación del bus de eventos (basado en RabbitMQ o en un Service Bus) se insertará en el constructor del controlador, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0fec-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="d0fec-115">Después, se usa desde los métodos del dispositivo, como en el método UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="d0fec-115">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="d0fec-116">En este caso, como el microservicio de origen es un microservicio CRUD simple, ese código se coloca directamente en un controlador de API web.</span><span class="sxs-lookup"><span data-stu-id="d0fec-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span>

<span data-ttu-id="d0fec-117">En microservicios más avanzados, como cuando se usan enfoques de CQRS, se puede implementar en la clase `CommandHandler`, dentro del método `Handle()`.</span><span class="sxs-lookup"><span data-stu-id="d0fec-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="d0fec-118">Diseño de la atomicidad y la resistencia al publicar en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="d0fec-119">Al publicar eventos de integración a través de un sistema de mensajería distribuido como el bus de eventos, tiene el problema de actualizar la base de datos original de forma atómica y de publicar un evento (es decir, se completan las dos operaciones o ninguna de ellas).</span><span class="sxs-lookup"><span data-stu-id="d0fec-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event (that is, either both operations complete or none of them).</span></span> <span data-ttu-id="d0fec-120">Por ejemplo, en el ejemplo simplificado mostrado anteriormente, el código confirma los datos en la base de datos cuando cambia el precio del producto y, después, publica un mensaje ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="d0fec-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="d0fec-121">En principio, es posible que parezca fundamental que estas dos operaciones se realicen de forma atómica.</span><span class="sxs-lookup"><span data-stu-id="d0fec-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="d0fec-122">Pero si está usando una transacción distribuida que implique la base de datos y el agente de mensajes, como se hace en sistemas anteriores como [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), no se recomienda por las razones descritas por el [Teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="d0fec-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="d0fec-123">Básicamente, los microservicios se usan para crear sistemas escalables y de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="d0fec-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="d0fec-124">Para simplificarlo de algún modo, el teorema CAP afirma que no se puede crear una base de datos (distribuida), o un microservicio que posea su modelo, que esté continuamente disponible, tenga coherencia fuerte *y* sea tolerante a cualquier partición.</span><span class="sxs-lookup"><span data-stu-id="d0fec-124">Simplifying somewhat, the CAP theorem says that you cannot build a (distributed) database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="d0fec-125">Debe elegir dos de estas tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="d0fec-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="d0fec-126">En las arquitecturas basadas en microservicios, debe elegir la disponibilidad y la tolerancia, y quitar énfasis a la coherencia fuerte.</span><span class="sxs-lookup"><span data-stu-id="d0fec-126">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="d0fec-127">Por tanto, en las aplicaciones basadas en microservicios más modernas, normalmente no le interesará usar transacciones distribuidas en la mensajería, como haría al implementar [transacciones distribuidas](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) basadas en el Coordinador de transacciones distribuidas (DTC) de Windows con [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="d0fec-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://docs.microsoft.com/previous-versions/windows/desktop/ms681205(v=vs.85)) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/windows/desktop/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="d0fec-128">Volvamos al problema inicial y su ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-128">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="d0fec-129">Si el servicio se bloquea después de que se actualice la base de datos (en este caso, justo después de la línea de código con \_context.SaveChangesAsync()) pero antes de que se publique el evento de integración, el sistema global puede volverse incoherente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-129">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="d0fec-130">Esto podría ser crítico para la empresa, según la operación empresarial específica con la que se esté tratando.</span><span class="sxs-lookup"><span data-stu-id="d0fec-130">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="d0fec-131">Como se mencionó anteriormente en la sección sobre arquitectura, puede tener varios enfoques para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="d0fec-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

- <span data-ttu-id="d0fec-132">Uso del [patrón de orígenes de eventos](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) completo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-132">Using the full [Event Sourcing pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).</span></span>

- <span data-ttu-id="d0fec-133">Uso de la [minería del registro de transacciones](https://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="d0fec-133">Using [transaction log mining](https://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

- <span data-ttu-id="d0fec-134">Uso del [patrón de bandeja de salida](https://www.kamilgrzybek.com/design/the-outbox-pattern/).</span><span class="sxs-lookup"><span data-stu-id="d0fec-134">Using the [Outbox pattern](https://www.kamilgrzybek.com/design/the-outbox-pattern/).</span></span> <span data-ttu-id="d0fec-135">Se trata de una tabla transaccional para almacenar los eventos de integración (extendiendo la transacción local).</span><span class="sxs-lookup"><span data-stu-id="d0fec-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="d0fec-136">En este escenario, el uso del modelo de orígenes de evento (ES) completo es uno de los mejores métodos, si no *el* mejor.</span><span class="sxs-lookup"><span data-stu-id="d0fec-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="d0fec-137">Pero en muchas situaciones, es posible que no pueda implementar un sistema de ES completo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="d0fec-138">Con los orígenes de evento solo se almacenan los eventos de dominio en la base de datos transaccional, en lugar de almacenar los datos de estado actuales.</span><span class="sxs-lookup"><span data-stu-id="d0fec-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="d0fec-139">Almacenar solo los eventos de dominio puede tener grandes ventajas, como tener el historial del sistema disponible y poder determinar el estado del sistema en cualquier momento del pasado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="d0fec-140">Pero la implementación de un sistema de ES completo requiere que se cambie la arquitectura de la mayor parte del sistema y presenta otras muchas complejidades y requisitos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="d0fec-141">Por ejemplo, le interesaría usar una base de datos creada específicamente para los orígenes de eventos, como [Event Store](https://eventstore.org/), o bien una base de datos orientada a documentos como Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB.</span><span class="sxs-lookup"><span data-stu-id="d0fec-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://eventstore.org/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="d0fec-142">Los orígenes de evento son un buen enfoque para este problema, pero no es la solución más sencilla a menos que ya esté familiarizado con los orígenes de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="d0fec-143">La opción de usar la minería del registro de transacciones parece muy transparente en un principio.</span><span class="sxs-lookup"><span data-stu-id="d0fec-143">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="d0fec-144">Pero para usar este enfoque, el microservicio debe acoplarse al registro de transacciones de RDBMS, como el registro de transacciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0fec-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="d0fec-145">Esto probablemente no sea deseable.</span><span class="sxs-lookup"><span data-stu-id="d0fec-145">This is probably not desirable.</span></span> <span data-ttu-id="d0fec-146">Otra desventaja es que es posible que las actualizaciones de bajo nivel en el registro de transacciones no estén al mismo nivel que los eventos de integración generales.</span><span class="sxs-lookup"><span data-stu-id="d0fec-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="d0fec-147">En ese caso, el proceso de utilización de técnicas de ingeniería inversa en esas operaciones de registro de transacciones puede ser complicado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="d0fec-148">Un enfoque equilibrado es una combinación de una tabla de base de datos transaccional y un patrón de ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="d0fec-149">Puede usar un estado como "listo para publicar el evento" que se establece en el evento original cuando se confirma en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="d0fec-149">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="d0fec-150">Después, intente publicar el evento en el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="d0fec-151">Si la acción de publicación de evento se realiza correctamente, inicie otra transacción en el servicio de origen y cambie el estado de "listo para publicar el evento" a "evento ya publicado".</span><span class="sxs-lookup"><span data-stu-id="d0fec-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="d0fec-152">Si se produce un error en la acción de publicación del evento en el bus de eventos, los datos todavía no serán incoherentes en el microservicio de origen (seguirán marcados como "listo para publicar el evento") y, con respecto al resto de los servicios, eventualmente serán coherentes.</span><span class="sxs-lookup"><span data-stu-id="d0fec-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="d0fec-153">Siempre puede tener trabajos en segundo plano que comprueben el estado de las transacciones o los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="d0fec-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="d0fec-154">Si el trabajo encuentra un evento en el estado "listo para publicar el evento", puede intentar volver a publicarlo en el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-154">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="d0fec-155">Tenga en cuenta que, con este enfoque, solo se conservan los eventos de integración para cada microservicio de origen y solo los eventos que le interesa comunicar con otros microservicios o sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="d0fec-156">Por el contrario, en un sistema de ES completo, también se almacenan todos los eventos de dominio.</span><span class="sxs-lookup"><span data-stu-id="d0fec-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="d0fec-157">Por tanto, este enfoque equilibrado es un sistema de ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="d0fec-158">Necesita una lista de eventos de integración con su estado actual ("listo para publicar" frente a "publicado").</span><span class="sxs-lookup"><span data-stu-id="d0fec-158">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="d0fec-159">Pero solo tiene que implementar estos estados para los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="d0fec-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="d0fec-160">Y en este enfoque, no tendrá que almacenar todos los datos de dominio como eventos en la base de datos transaccional, tal y como haría en un sistema de ES completo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="d0fec-161">Si ya usa una base de datos relacional, puede usar una tabla transaccional para almacenar los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="d0fec-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="d0fec-162">Para lograr la atomicidad en la aplicación, se usa un proceso de dos pasos basado en transacciones locales.</span><span class="sxs-lookup"><span data-stu-id="d0fec-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="d0fec-163">Básicamente, dispone de una tabla IntegrationEvent en la misma base de datos donde se encuentren las entidades de dominio.</span><span class="sxs-lookup"><span data-stu-id="d0fec-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="d0fec-164">Esa tabla funciona como un seguro para lograr la atomicidad, de modo que los eventos de integración guardados se incluyan en las mismas transacciones con las que se confirman los datos de dominio.</span><span class="sxs-lookup"><span data-stu-id="d0fec-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="d0fec-165">Paso a paso, el proceso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="d0fec-165">Step by step, the process goes like this:</span></span>

1. <span data-ttu-id="d0fec-166">La aplicación inicia una transacción de base de datos local.</span><span class="sxs-lookup"><span data-stu-id="d0fec-166">The application begins a local database transaction.</span></span>

2. <span data-ttu-id="d0fec-167">Después, actualiza el estado de las entidades de dominio e inserta un evento en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="d0fec-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span>

3. <span data-ttu-id="d0fec-168">Finalmente, confirma la transacción, por lo que obtiene la atomicidad deseada.</span><span class="sxs-lookup"><span data-stu-id="d0fec-168">Finally, it commits the transaction, so you get the desired atomicity and then</span></span>

4. <span data-ttu-id="d0fec-169">A continuación, publique el evento de algún modo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-169">You publish the event somehow (next).</span></span>

<span data-ttu-id="d0fec-170">Al implementar los pasos necesarios para publicar los eventos, dispone de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0fec-170">When implementing the steps of publishing the events, you have these choices:</span></span>

- <span data-ttu-id="d0fec-171">Publicar el evento de integración justo después de confirmar la transacción y usar otra transacción local para marcar los eventos en la tabla como "en proceso de publicación".</span><span class="sxs-lookup"><span data-stu-id="d0fec-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="d0fec-172">Después, usar la tabla como si fuera un artefacto para realizar el seguimiento de los eventos de integración en el caso de que se produzcan problemas en los microservicios remotos y realizar acciones de compensación en función de los eventos de integración almacenados.</span><span class="sxs-lookup"><span data-stu-id="d0fec-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

- <span data-ttu-id="d0fec-173">Usar la tabla como una especie de cola.</span><span class="sxs-lookup"><span data-stu-id="d0fec-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="d0fec-174">Un proceso o subproceso de aplicación independiente consulta la tabla de eventos de integración, publica los eventos en el bus de eventos y, después, usa una transacción local para marcar los eventos como publicados.</span><span class="sxs-lookup"><span data-stu-id="d0fec-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="d0fec-175">En la figura 6-22 se muestra la arquitectura para el primero de estos enfoques.</span><span class="sxs-lookup"><span data-stu-id="d0fec-175">Figure 6-22 shows the architecture for the first of these approaches.</span></span>

![Diagrama de atomicidad cuando se publica sin un microservicio de trabajo.](./media/subscribe-events/atomicity-publish-event-bus.png)

<span data-ttu-id="d0fec-177">**Figura 6-22**.</span><span class="sxs-lookup"><span data-stu-id="d0fec-177">**Figure 6-22**.</span></span> <span data-ttu-id="d0fec-178">Atomicidad al publicar eventos en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-178">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="d0fec-179">En el enfoque que se muestra en la figura 6-22 falta un microservicio de trabajo adicional que se encarga de comprobar y confirmar que los eventos de integración se han publicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-179">The approach illustrated in Figure 6-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="d0fec-180">En caso de error, ese microservicio de trabajo de comprobación adicional puede leer los eventos de la tabla y volver a publicarlos, es decir, repetir el paso 2.</span><span class="sxs-lookup"><span data-stu-id="d0fec-180">In case of failure, that additional checker worker microservice can read events from the table and republish them, that is, repeat step number 2.</span></span>

<span data-ttu-id="d0fec-181">Sobre el segundo enfoque: se usa la tabla EventLog como una cola y siempre se usa un microservicio de trabajo para publicar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d0fec-181">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="d0fec-182">En ese caso, el proceso es similar al que se muestra en la figura 6-23.</span><span class="sxs-lookup"><span data-stu-id="d0fec-182">In that case, the process is like that shown in Figure 6-23.</span></span> <span data-ttu-id="d0fec-183">Esto muestra un microservicio adicional y la tabla es el único origen cuando se publican los eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-183">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![Diagrama de atomicidad cuando se publica con un microservicio de trabajo.](./media/subscribe-events/atomicity-publish-worker-microservice.png)

<span data-ttu-id="d0fec-185">**Figura 6-23**.</span><span class="sxs-lookup"><span data-stu-id="d0fec-185">**Figure 6-23**.</span></span> <span data-ttu-id="d0fec-186">Atomicidad al publicar eventos en el bus de eventos con un microservicio de trabajo</span><span class="sxs-lookup"><span data-stu-id="d0fec-186">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="d0fec-187">Para simplificar, en el ejemplo eShopOnContainers se usa el primer enfoque (sin procesos adicionales ni microservicios de comprobador) junto con el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-187">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="d0fec-188">Pero en eShopOnContainers no se controlan todos los casos de error posibles.</span><span class="sxs-lookup"><span data-stu-id="d0fec-188">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="d0fec-189">En una aplicación real implementada en la nube, debe asumir el hecho de que con el tiempo van a surgir problemas, y debe implementar esa lógica de comprobación y reenvío.</span><span class="sxs-lookup"><span data-stu-id="d0fec-189">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="d0fec-190">El uso de la tabla como una cola puede ser más eficaz que el primer enfoque si tiene esa tabla como un único origen de eventos cuando los publica (con el trabajo) a través del bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-190">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them (with the worker) through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="d0fec-191">Implementación de la atomicidad al publicar eventos de integración a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-191">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="d0fec-192">En el código siguiente se muestra la forma de crear una única transacción que implica varios objetos DbContext, un contexto relacionado con los datos originales que se van a actualizar y el segundo relacionado con la tabla IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="d0fec-192">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="d0fec-193">Tenga en cuenta que la transacción en el código de ejemplo siguiente no será resistente si las conexiones a la base de datos tienen algún problema cuando se ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="d0fec-193">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="d0fec-194">Esto puede ocurrir en sistemas de servidor basados en la nube como Azure SQL DB, en los que es posible que las bases de datos se muevan entre servidores.</span><span class="sxs-lookup"><span data-stu-id="d0fec-194">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="d0fec-195">Para implementar transacciones resistentes entre varios contextos, vea la sección [Implementación de conexiones resistentes de Entity Framework Core SQL](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="d0fec-195">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="d0fec-196">Para evitar confusiones, en el ejemplo siguiente se muestra el proceso completo en un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="d0fec-196">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="d0fec-197">Pero la implementación de eShopOnContainers realmente se refactoriza y divide esta lógica en varias clases para que sea más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="d0fec-197">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

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

      _integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent);
  }

  return Ok();
}

```

<span data-ttu-id="d0fec-198">Después de crear el evento de integración ProductPriceChangedIntegrationEvent, la transacción que almacena la operación de dominio original (la actualización del elemento de catálogo) también incluye la persistencia del evento en la tabla EventLog.</span><span class="sxs-lookup"><span data-stu-id="d0fec-198">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="d0fec-199">Esto crea una única transacción y siempre se podrá comprobar si los mensajes de eventos se han enviado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-199">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="d0fec-200">La tabla de registro de eventos se actualiza de forma atómica con la operación de base de datos original, mediante una transacción local en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-200">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="d0fec-201">Si se produce un error en cualquiera de las operaciones, se inicia una excepción y la transacción revierte cualquier operación completada, lo que mantiene la coherencia entre las operaciones de dominio y los mensajes de eventos que se guardan en la tabla.</span><span class="sxs-lookup"><span data-stu-id="d0fec-201">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages saved to the table.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="d0fec-202">Recepción de mensajes desde suscripciones: controladores de eventos en microservicios de receptor</span><span class="sxs-lookup"><span data-stu-id="d0fec-202">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="d0fec-203">Además de la lógica de suscripción de eventos, debe implementar el código interno para los controladores de eventos de integración (por ejemplo, un método de devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="d0fec-203">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="d0fec-204">En el controlador de eventos se especifica dónde se reciben y procesan los mensajes de eventos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-204">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="d0fec-205">Un controlador de eventos recibe por primera vez una instancia de evento desde el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-205">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="d0fec-206">Después, busca el componente que se va a procesar relacionado con ese evento de integración y lo propaga y conserva como un cambio de estado en el microservicio de receptor.</span><span class="sxs-lookup"><span data-stu-id="d0fec-206">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="d0fec-207">Por ejemplo, si un evento ProductPriceChanged se origina en el microservicio de catálogo, se controla en el microservicio de cesta de la compra y también cambia el estado en este microservicio de receptor, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-207">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="d0fec-208">El controlador de eventos debe comprobar si el producto existe en cualquiera de las instancias de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="d0fec-208">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="d0fec-209">También actualiza el precio del artículo para cada artículo de línea de la cesta de la compra relacionado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-209">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="d0fec-210">Por último, crea una alerta que se mostrará al usuario sobre el cambio de precio, como se muestra en la figura 6-24.</span><span class="sxs-lookup"><span data-stu-id="d0fec-210">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 6-24.</span></span>

![Captura de pantalla de un explorador que muestra la notificación de cambio de precio en el carro del usuario.](./media/subscribe-events/display-item-price-change.png)

<span data-ttu-id="d0fec-212">**Figura 6-24**.</span><span class="sxs-lookup"><span data-stu-id="d0fec-212">**Figure 6-24**.</span></span> <span data-ttu-id="d0fec-213">Representación de un cambio del precio de un artículo en una cesta, comunicado por eventos de integración</span><span class="sxs-lookup"><span data-stu-id="d0fec-213">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="d0fec-214">Idempotencia en los eventos de mensajes de actualización</span><span class="sxs-lookup"><span data-stu-id="d0fec-214">Idempotency in update message events</span></span>

<span data-ttu-id="d0fec-215">Un aspecto importante de los eventos de mensaje de actualización es que un error en cualquier punto de la comunicación debe hacer que se vuelva a intentar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0fec-215">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="d0fec-216">En caso contrario, es posible que una tarea en segundo plano intente publicar un evento que ya se ha publicado, lo que genera una condición de carrera.</span><span class="sxs-lookup"><span data-stu-id="d0fec-216">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="d0fec-217">Es necesario asegurarse de que las actualizaciones son idempotentes o que proporcionan información suficiente para garantizar que un duplicado se pueda detectar, descartarlo y devolver una sola respuesta.</span><span class="sxs-lookup"><span data-stu-id="d0fec-217">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="d0fec-218">Como se indicó anteriormente, idempotencia significa que una operación se puede realizar varias veces sin cambiar el resultado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-218">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="d0fec-219">En un entorno de mensajería, como al comunicar eventos, un evento es idempotente si se puede entregar varias veces sin cambiar el resultado del microservicio receptor.</span><span class="sxs-lookup"><span data-stu-id="d0fec-219">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="d0fec-220">Esto puede ser necesario debido a la naturaleza del propio evento, o bien al modo en que el sistema controla el evento.</span><span class="sxs-lookup"><span data-stu-id="d0fec-220">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="d0fec-221">La idempotencia de mensajes es importante en cualquier aplicación en la que se use la mensajería, no solo en las aplicaciones que implementan el patrón de bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-221">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="d0fec-222">Un ejemplo de una operación idempotente es una instrucción SQL que inserta datos en una tabla solo si esos datos no están ya en la tabla.</span><span class="sxs-lookup"><span data-stu-id="d0fec-222">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="d0fec-223">No importa cuántas veces se ejecute esa instrucción SQL de inserción; el resultado será el mismo: la tabla contendrá esos datos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-223">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="d0fec-224">Este tipo de idempotencia también puede ser necesaria cuando se trabaja con mensajes si existe la posibilidad de que se envíen y, por tanto, se procesen más de una vez.</span><span class="sxs-lookup"><span data-stu-id="d0fec-224">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="d0fec-225">Por ejemplo, si la lógica de reintento hace que un remitente envíe exactamente el mismo mensaje más de una vez, tendrá que asegurarse de que sea idempotente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-225">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="d0fec-226">Se pueden diseñar mensajes idempotentes.</span><span class="sxs-lookup"><span data-stu-id="d0fec-226">It is possible to design idempotent messages.</span></span> <span data-ttu-id="d0fec-227">Por ejemplo, puede crear un evento que indique "establecer el precio del producto en 25 USD" en lugar de "sumar 5 USD al precio del producto".</span><span class="sxs-lookup"><span data-stu-id="d0fec-227">For example, you can create an event that says "set the product price to $25" instead of "add $5 to the product price."</span></span> <span data-ttu-id="d0fec-228">Podría procesar sin riesgos el primer mensaje cualquier número de veces y el resultado sería el mismo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-228">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="d0fec-229">Esto no es cierto para el segundo mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0fec-229">That is not true for the second message.</span></span> <span data-ttu-id="d0fec-230">Pero incluso en el primer caso, es posible que no le interese procesar el primer evento, porque el sistema también podría haber enviado un evento de cambio de precio más reciente y se podría sobrescribir el precio de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d0fec-230">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="d0fec-231">Otro ejemplo podría ser un evento de pedido completado que se propaga a varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="d0fec-231">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="d0fec-232">Es importante que la información del pedido se actualice una sola vez en otros sistemas, incluso si hay eventos de mensaje duplicados para el mismo evento de pedido completado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-232">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="d0fec-233">Es conveniente tener algún tipo de identidad por evento para poder crear lógica que exija que cada evento se procese solo una vez por cada receptor.</span><span class="sxs-lookup"><span data-stu-id="d0fec-233">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="d0fec-234">Algún procesamiento de mensajes es idempotente de forma inherente.</span><span class="sxs-lookup"><span data-stu-id="d0fec-234">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="d0fec-235">Por ejemplo, si un sistema genera imágenes en miniatura, es posible que no importe cuántas veces se procesa el mensaje sobre la miniatura generada; el resultado es que las miniaturas se generan y son iguales cada vez.</span><span class="sxs-lookup"><span data-stu-id="d0fec-235">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="d0fec-236">Por otra parte, las operaciones como la llamada a una pasarela de pagos para cobrar una tarjeta de crédito no pueden ser idempotentes.</span><span class="sxs-lookup"><span data-stu-id="d0fec-236">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="d0fec-237">En estos casos, debe asegurarse de que el procesamiento repetido de un mensaje tiene el efecto que se espera.</span><span class="sxs-lookup"><span data-stu-id="d0fec-237">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d0fec-238">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d0fec-238">Additional resources</span></span>

- <span data-ttu-id="d0fec-239">**Respeto de la idempotencia de los mensajes** </span><span class="sxs-lookup"><span data-stu-id="d0fec-239">**Honoring message idempotency** </span></span>\
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591565(v=pandp.10)#honoring-message-idempotency>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="d0fec-240">Desduplicación de mensajes de eventos de integración</span><span class="sxs-lookup"><span data-stu-id="d0fec-240">Deduplicating integration event messages</span></span>

<span data-ttu-id="d0fec-241">Puede asegurarse de que los eventos de mensajes se envían y se procesan una sola vez por cada suscriptor en niveles diferentes.</span><span class="sxs-lookup"><span data-stu-id="d0fec-241">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="d0fec-242">Una manera de hacerlo consiste en usar una característica de desduplicación que ofrece la infraestructura de mensajería en uso.</span><span class="sxs-lookup"><span data-stu-id="d0fec-242">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="d0fec-243">Otra consiste en implementar lógica personalizada en el microservicio de destino.</span><span class="sxs-lookup"><span data-stu-id="d0fec-243">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="d0fec-244">Lo mejor es tener validaciones en el nivel de transporte y el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0fec-244">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="d0fec-245">Desduplicación de eventos de mensaje en el nivel de controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="d0fec-245">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="d0fec-246">Una manera de asegurarse de que un evento se procesa solo una vez por cualquier receptor es mediante la implementación de cierta lógica al procesar los eventos de mensaje en controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="d0fec-246">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="d0fec-247">Por ejemplo, ese es el enfoque que se usa en la aplicación eShopOnContainers, como se aprecia en el [código fuente de la clase UserCheckoutAcceptedIntegrationEventHandler](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) cuando recibe un evento de integración UserCheckoutAcceptedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="d0fec-247">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code of the UserCheckoutAcceptedIntegrationEventHandler class](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/IntegrationEvents/EventHandling/UserCheckoutAcceptedIntegrationEventHandler.cs) when it receives an UserCheckoutAcceptedIntegrationEvent integration event.</span></span> <span data-ttu-id="d0fec-248">(En este caso se encapsula CreateOrderCommand con un elemento IdentifiedCommand, usando eventMsg.RequestId como un identificador, antes de enviarlo al controlador de comandos).</span><span class="sxs-lookup"><span data-stu-id="d0fec-248">(In this case we wrap the CreateOrderCommand with an IdentifiedCommand, using the eventMsg.RequestId as an identifier, before sending it to the command handler).</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="d0fec-249">Desduplicación de mensajes cuando se usa RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="d0fec-249">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="d0fec-250">Cuando se producen errores de red intermitentes, los mensajes se pueden duplicar y el receptor del mensaje debe estar listo para controlar estos mensajes duplicados.</span><span class="sxs-lookup"><span data-stu-id="d0fec-250">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="d0fec-251">Si es posible, los receptores deben controlar los mensajes de una manera idempotente, lo que es mejor que controlarlos de forma explícita mediante desduplicación.</span><span class="sxs-lookup"><span data-stu-id="d0fec-251">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="d0fec-252">Según la [documentación de RabbitMQ](https://www.rabbitmq.com/reliability.html#consumer), "si un mensaje se entrega a un consumidor y después se vuelve a poner en la cola (porque no se confirmó antes de desconectar la conexión del consumidor, por ejemplo), RabbitMQ establecerá la marca "entregado de nuevo" cuando se vuelva a entregar (con independencia de que sea al mismo consumidor o a otro)".</span><span class="sxs-lookup"><span data-stu-id="d0fec-252">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="d0fec-253">Si se establece la marca "entregado de nuevo", el receptor debe tenerlo en cuenta, dado que es posible que el mensaje ya se haya procesado.</span><span class="sxs-lookup"><span data-stu-id="d0fec-253">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="d0fec-254">Pero eso no está garantizado; es posible que el mensaje nunca llegara al receptor después de salir del agente de mensajes, quizás debido a problemas de red.</span><span class="sxs-lookup"><span data-stu-id="d0fec-254">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="d0fec-255">Por otro lado, si no se estableció la marca "entregado de nuevo", se garantiza que el mensaje no se ha enviado más de una vez.</span><span class="sxs-lookup"><span data-stu-id="d0fec-255">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="d0fec-256">Por tanto, el receptor debe desduplicar o procesar los mensajes de una manera idempotente solo si se establece la marca "entregado de nuevo" en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d0fec-256">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d0fec-257">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d0fec-257">Additional resources</span></span>

- <span data-ttu-id="d0fec-258">**Bifurcación de eShopOnContainers mediante NServiceBus [Particular Software]**  </span><span class="sxs-lookup"><span data-stu-id="d0fec-258">**Forked eShopOnContainers using NServiceBus (Particular Software)** </span></span>\
    <https://go.particular.net/eShopOnContainers>

- <span data-ttu-id="d0fec-259">**Mensajería controlada por eventos** </span><span class="sxs-lookup"><span data-stu-id="d0fec-259">**Event Driven Messaging** </span></span>\
    <https://patterns.arcitura.com/soa-patterns/design_patterns/event_driven_messaging>

- <span data-ttu-id="d0fec-260">**Jimmy Bogard. Refactorización hacia la resiliencia: evaluación del acoplamiento** </span><span class="sxs-lookup"><span data-stu-id="d0fec-260">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling** </span></span>\
    <https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/>

- <span data-ttu-id="d0fec-261">**Canal de publicación y suscripción** </span><span class="sxs-lookup"><span data-stu-id="d0fec-261">**Publish-Subscribe channel** </span></span>\
    <https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html>

- <span data-ttu-id="d0fec-262">**Comunicación entre contextos delimitados** </span><span class="sxs-lookup"><span data-stu-id="d0fec-262">**Communicating Between Bounded Contexts** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591572(v=pandp.10)>

- <span data-ttu-id="d0fec-263">**Coherencia de los eventos** </span><span class="sxs-lookup"><span data-stu-id="d0fec-263">**Eventual Consistency** </span></span>\
    <https://en.wikipedia.org/wiki/Eventual_consistency>

- <span data-ttu-id="d0fec-264">**Philip Brown. Estrategias para la integración de contextos delimitados** </span><span class="sxs-lookup"><span data-stu-id="d0fec-264">**Philip Brown. Strategies for Integrating Bounded Contexts** </span></span>\
    <https://www.culttt.com/2014/11/26/strategies-integrating-bounded-contexts/>

- <span data-ttu-id="d0fec-265">**Chris Richardson. Desarrollo de microservicios transaccionales mediante agregados, orígenes de eventos y CQRS: parte 2** </span><span class="sxs-lookup"><span data-stu-id="d0fec-265">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2** </span></span>\
    <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson>

- <span data-ttu-id="d0fec-266">**Chris Richardson. Patrón de orígenes de eventos** </span><span class="sxs-lookup"><span data-stu-id="d0fec-266">**Chris Richardson. Event Sourcing pattern** </span></span>\
    <https://microservices.io/patterns/data/event-sourcing.html>

- <span data-ttu-id="d0fec-267">**Introducción a los orígenes de eventos** </span><span class="sxs-lookup"><span data-stu-id="d0fec-267">**Introducing Event Sourcing** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/jj591559(v=pandp.10)>

- <span data-ttu-id="d0fec-268">**Base de datos Event Store**.</span><span class="sxs-lookup"><span data-stu-id="d0fec-268">**Event Store database**.</span></span> <span data-ttu-id="d0fec-269">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="d0fec-269">Official site.</span></span> \
    <https://geteventstore.com/>

- <span data-ttu-id="d0fec-270">**Patrick Nommensen. Administración de datos orientada a eventos para microservicios** </span><span class="sxs-lookup"><span data-stu-id="d0fec-270">**Patrick Nommensen. Event-Driven Data Management for Microservices** </span></span>\
    <https://dzone.com/articles/event-driven-data-management-for-microservices-1>

- <span data-ttu-id="d0fec-271">**Teorema CAP** </span><span class="sxs-lookup"><span data-stu-id="d0fec-271">**The CAP Theorem** </span></span>\
    <https://en.wikipedia.org/wiki/CAP_theorem>

- <span data-ttu-id="d0fec-272">**¿Qué es el teorema CAP?**</span><span class="sxs-lookup"><span data-stu-id="d0fec-272">**What is CAP Theorem?**</span></span> \
    <https://www.quora.com/What-Is-CAP-Theorem-1>

- <span data-ttu-id="d0fec-273">**Manual de coherencia de datos** </span><span class="sxs-lookup"><span data-stu-id="d0fec-273">**Data Consistency Primer** </span></span>\
    <https://docs.microsoft.com/previous-versions/msp-n-p/dn589800(v=pandp.10)>

- <span data-ttu-id="d0fec-274">**Rick Saling. Teorema CAP: por qué "todo es diferente" con la nube e Internet** </span><span class="sxs-lookup"><span data-stu-id="d0fec-274">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet** </span></span>\
    <https://docs.microsoft.com/archive/blogs/rickatmicrosoft/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/>

- <span data-ttu-id="d0fec-275">**Eric Brewer. ¿cómo han cambiado las "normas"? CAP doce años más tarde:**  </span><span class="sxs-lookup"><span data-stu-id="d0fec-275">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed** </span></span>\
    <https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed>

- <span data-ttu-id="d0fec-276">**Azure Service Bus. Mensajería asincrónica: Detección de duplicados**  </span><span class="sxs-lookup"><span data-stu-id="d0fec-276">**Azure Service Bus. Brokered Messaging: Duplicate Detection**  </span></span>\
    <https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25>

- <span data-ttu-id="d0fec-277">**Guía de confiabilidad**[documentación de RabbitMQ] </span><span class="sxs-lookup"><span data-stu-id="d0fec-277">**Reliability Guide** (RabbitMQ documentation) </span></span>\
    <https://www.rabbitmq.com/reliability.html#consumer>

> [!div class="step-by-step"]
> <span data-ttu-id="d0fec-278">[Anterior](rabbitmq-event-bus-development-test-environment.md)
> [Siguiente](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="d0fec-278">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
