---
title: Suscripción a eventos
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Suscripción a eventos
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 5e53e0a3578c19b09f5327f444d1a5c013ad4cd9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194077"
---
# <a name="subscribing-to-events"></a><span data-ttu-id="e82b6-103">Suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-103">Subscribing to events</span></span>

<span data-ttu-id="e82b6-104">El primer paso para usar el bus de eventos es suscribir los microservicios a los eventos que quieren recibir.</span><span class="sxs-lookup"><span data-stu-id="e82b6-104">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="e82b6-105">Eso debe realizarse en los microservicios de receptor.</span><span class="sxs-lookup"><span data-stu-id="e82b6-105">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="e82b6-106">En el siguiente código simple se muestra lo que cada microservicio de receptor debe implementar al iniciar el servicio (es decir, en la clase `Startup`) para que se suscriba a los eventos que necesita.</span><span class="sxs-lookup"><span data-stu-id="e82b6-106">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the `Startup` class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="e82b6-107">En este caso, el microservicio `basket.api` necesita suscribirse a los mensajes `ProductPriceChangedIntegrationEvent` y `OrderStartedIntegrationEvent`.</span><span class="sxs-lookup"><span data-stu-id="e82b6-107">In this case, the `basket.api` microservice needs to subscribe to `ProductPriceChangedIntegrationEvent` and the `OrderStartedIntegrationEvent` messages.</span></span> 

<span data-ttu-id="e82b6-108">Por ejemplo, la suscripción al evento `ProductPriceChangedIntegrationEvent` hace que el microservicio de cesta sea consciente de los cambios en el precio del producto y le permite advertir al usuario sobre el cambio si ese producto está en la cesta de la compra del usuario.</span><span class="sxs-lookup"><span data-stu-id="e82b6-108">For instance, when subscribing to the `ProductPriceChangedIntegrationEvent` event, that makes the basket microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();

eventBus.Subscribe<ProductPriceChangedIntegrationEvent, 
                   ProductPriceChangedIntegrationEventHandler>();

eventBus.Subscribe<OrderStartedIntegrationEvent, 
                   OrderStartedIntegrationEventHandler>();

```

<span data-ttu-id="e82b6-109">Después de ejecutar este código, el microservicio de suscriptor escuchará a través de los canales de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="e82b6-109">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="e82b6-110">Cuando llega algún mensaje de tipo ProductPriceChangedIntegrationEvent, el código invoca el controlador de eventos que se le pasa y procesa el evento.</span><span class="sxs-lookup"><span data-stu-id="e82b6-110">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="e82b6-111">Publicación de eventos a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-111">Publishing events through the event bus</span></span>

<span data-ttu-id="e82b6-112">Por último, el remitente del mensaje (el microservicio de origen) publica los eventos de integración con código similar al del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-112">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="e82b6-113">(Es un ejemplo simplificado que no tiene en cuenta la atomicidad). Debería implementar un código similar cada vez que un evento se tenga que propagar entre varios microservicios, normalmente inmediatamente después de confirmar datos o transacciones desde el microservicio de origen.</span><span class="sxs-lookup"><span data-stu-id="e82b6-113">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="e82b6-114">En primer lugar, el objeto de implementación del bus de eventos (basado en RabbitMQ o en un Service Bus) se insertará en el constructor del controlador, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e82b6-114">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="e82b6-115">Después, se usa desde los métodos del dispositivo, como en el método UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="e82b6-115">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="e82b6-116">En este caso, como el microservicio de origen es un microservicio CRUD simple, ese código se coloca directamente en un controlador de API web.</span><span class="sxs-lookup"><span data-stu-id="e82b6-116">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> 
 
<span data-ttu-id="e82b6-117">En microservicios más avanzados, como cuando se usan enfoques de CQRS, se puede implementar en la clase `CommandHandler`, dentro del método `Handle()`.</span><span class="sxs-lookup"><span data-stu-id="e82b6-117">In more advanced microservices, like when using CQRS approaches, it can be implemented in the `CommandHandler` class, within the `Handle()` method.</span></span> 


### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="e82b6-118">Diseño de la atomicidad y la resistencia al publicar en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-118">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="e82b6-119">Al publicar eventos de integración a través de un sistema de mensajería distribuido como el bus de eventos, tiene el problema de actualizar la base de datos original de forma atómica y de publicar un evento.</span><span class="sxs-lookup"><span data-stu-id="e82b6-119">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="e82b6-120">Por ejemplo, en el ejemplo simplificado mostrado anteriormente, el código confirma los datos en la base de datos cuando cambia el precio del producto y, después, publica un mensaje ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="e82b6-120">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="e82b6-121">En principio, es posible que parezca fundamental que estas dos operaciones se realicen de forma atómica.</span><span class="sxs-lookup"><span data-stu-id="e82b6-121">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="e82b6-122">Pero si está usando una transacción distribuida que implique la base de datos y el agente de mensajes, como se hace en sistemas anteriores como [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), no se recomienda por las razones descritas por el [Teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="e82b6-122">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="e82b6-123">Básicamente, los microservicios se usan para crear sistemas escalables y de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e82b6-123">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="e82b6-124">Para simplificar relativamente, el teorema CAP afirma que no se puede crear una base de datos (o un microservicio que posea su modelo) que esté continuamente disponible, tenga coherencia fuerte *y* sea tolerante a cualquier partición.</span><span class="sxs-lookup"><span data-stu-id="e82b6-124">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="e82b6-125">Debe elegir dos de estas tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="e82b6-125">You must choose two of these three properties.</span></span>

<span data-ttu-id="e82b6-126">En las arquitecturas basadas en microservicios, debe elegir la disponibilidad y la tolerancia, y quitar énfasis a la coherencia fuerte.</span><span class="sxs-lookup"><span data-stu-id="e82b6-126">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="e82b6-127">Por tanto, en las aplicaciones basadas en microservicios más modernas, normalmente no le interesará usar transacciones distribuidas en la mensajería, como haría al implementar [transacciones distribuidas](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) basadas en el Coordinador de transacciones distribuidas (DTC) de Windows con [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="e82b6-127">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="e82b6-128">Volvamos al problema inicial y su ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-128">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="e82b6-129">Si el servicio se bloquea después de que se actualice la base de datos (en este caso, justo después de la línea de código con \_context.SaveChangesAsync()) pero antes de que se publique el evento de integración, el sistema global puede volverse incoherente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-129">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="e82b6-130">Esto podría ser crítico para la empresa, según la operación empresarial específica con la que se esté tratando.</span><span class="sxs-lookup"><span data-stu-id="e82b6-130">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="e82b6-131">Como se mencionó anteriormente en la sección sobre arquitectura, puede tener varios enfoques para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="e82b6-131">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="e82b6-132">Uso del [patrón de orígenes de eventos](https://msdn.microsoft.com/library/dn589792.aspx) completo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-132">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="e82b6-133">Uso de la [minería del registro de transacciones](https://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="e82b6-133">Using [transaction log mining](https://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="e82b6-134">Uso del [patrón de bandeja de salida](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="e82b6-134">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="e82b6-135">Se trata de una tabla transaccional para almacenar los eventos de integración (extendiendo la transacción local).</span><span class="sxs-lookup"><span data-stu-id="e82b6-135">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="e82b6-136">En este escenario, el uso del modelo de orígenes de evento (ES) completo es uno de los mejores métodos, si no *el* mejor.</span><span class="sxs-lookup"><span data-stu-id="e82b6-136">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="e82b6-137">Pero en muchas situaciones, es posible que no pueda implementar un sistema de ES completo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-137">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="e82b6-138">Con los orígenes de evento solo se almacenan los eventos de dominio en la base de datos transaccional, en lugar de almacenar los datos de estado actuales.</span><span class="sxs-lookup"><span data-stu-id="e82b6-138">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="e82b6-139">Almacenar solo los eventos de dominio puede tener grandes ventajas, como tener el historial del sistema disponible y poder determinar el estado del sistema en cualquier momento del pasado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-139">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="e82b6-140">Pero la implementación de un sistema de ES completo requiere que se cambie la arquitectura de la mayor parte del sistema y presenta otras muchas complejidades y requisitos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-140">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="e82b6-141">Por ejemplo, le interesaría usar una base de datos creada específicamente para los orígenes de eventos, como [Event Store](https://geteventstore.com/), o bien una base de datos orientada a documentos como Azure Cosmos DB, MongoDB, Cassandra, CouchDB o RavenDB.</span><span class="sxs-lookup"><span data-stu-id="e82b6-141">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="e82b6-142">Los orígenes de evento son un buen enfoque para este problema, pero no es la solución más sencilla a menos que ya esté familiarizado con los orígenes de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-142">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="e82b6-143">La opción de usar la minería del registro de transacciones parece muy transparente en un principio.</span><span class="sxs-lookup"><span data-stu-id="e82b6-143">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="e82b6-144">Pero para usar este enfoque, el microservicio debe acoplarse al registro de transacciones de RDBMS, como el registro de transacciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e82b6-144">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="e82b6-145">Esto probablemente no sea deseable.</span><span class="sxs-lookup"><span data-stu-id="e82b6-145">This is probably not desirable.</span></span> <span data-ttu-id="e82b6-146">Otra desventaja es que es posible que las actualizaciones de bajo nivel en el registro de transacciones no estén al mismo nivel que los eventos de integración generales.</span><span class="sxs-lookup"><span data-stu-id="e82b6-146">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="e82b6-147">En ese caso, el proceso de utilización de técnicas de ingeniería inversa en esas operaciones de registro de transacciones puede ser complicado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-147">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="e82b6-148">Un enfoque equilibrado es una combinación de una tabla de base de datos transaccional y un patrón de ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-148">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="e82b6-149">Puede usar un estado como "listo para publicar el evento" que se establece en el evento original cuando se confirma en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="e82b6-149">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="e82b6-150">Después, intente publicar el evento en el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-150">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="e82b6-151">Si la acción de publicación de evento se realiza correctamente, inicie otra transacción en el servicio de origen y cambie el estado de "listo para publicar el evento" a "evento ya publicado".</span><span class="sxs-lookup"><span data-stu-id="e82b6-151">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="e82b6-152">Si se produce un error en la acción de publicación del evento en el bus de eventos, los datos todavía no serán incoherentes en el microservicio de origen (seguirán marcados como "listo para publicar el evento") y, con respecto al resto de los servicios, eventualmente serán coherentes.</span><span class="sxs-lookup"><span data-stu-id="e82b6-152">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="e82b6-153">Siempre puede tener trabajos en segundo plano que comprueben el estado de las transacciones o los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="e82b6-153">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="e82b6-154">Si el trabajo encuentra un evento en el estado "listo para publicar el evento", puede intentar volver a publicarlo en el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-154">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="e82b6-155">Tenga en cuenta que, con este enfoque, solo se conservan los eventos de integración para cada microservicio de origen y solo los eventos que le interesa comunicar con otros microservicios o sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-155">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="e82b6-156">Por el contrario, en un sistema de ES completo, también se almacenan todos los eventos de dominio.</span><span class="sxs-lookup"><span data-stu-id="e82b6-156">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="e82b6-157">Por tanto, este enfoque equilibrado es un sistema de ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-157">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="e82b6-158">Necesita una lista de eventos de integración con su estado actual ("listo para publicar" frente a "publicado").</span><span class="sxs-lookup"><span data-stu-id="e82b6-158">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="e82b6-159">Pero solo tiene que implementar estos estados para los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="e82b6-159">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="e82b6-160">Y en este enfoque, no tendrá que almacenar todos los datos de dominio como eventos en la base de datos transaccional, tal y como haría en un sistema de ES completo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-160">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="e82b6-161">Si ya usa una base de datos relacional, puede usar una tabla transaccional para almacenar los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="e82b6-161">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="e82b6-162">Para lograr la atomicidad en la aplicación, se usa un proceso de dos pasos basado en transacciones locales.</span><span class="sxs-lookup"><span data-stu-id="e82b6-162">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="e82b6-163">Básicamente, dispone de una tabla IntegrationEvent en la misma base de datos donde se encuentren las entidades de dominio.</span><span class="sxs-lookup"><span data-stu-id="e82b6-163">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="e82b6-164">Esa tabla funciona como un seguro para lograr la atomicidad, de modo que los eventos de integración guardados se incluyan en las mismas transacciones con las que se confirman los datos de dominio.</span><span class="sxs-lookup"><span data-stu-id="e82b6-164">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="e82b6-165">Paso a paso, el proceso es el siguiente: la aplicación inicia una transacción de base de datos local.</span><span class="sxs-lookup"><span data-stu-id="e82b6-165">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="e82b6-166">Después, actualiza el estado de las entidades de dominio e inserta un evento en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="e82b6-166">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="e82b6-167">Por último, confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="e82b6-167">Finally, it commits the transaction.</span></span> <span data-ttu-id="e82b6-168">Con esto se obtiene la atomicidad deseada.</span><span class="sxs-lookup"><span data-stu-id="e82b6-168">You get the desired atomicity.</span></span>

<span data-ttu-id="e82b6-169">Al implementar los pasos necesarios para publicar los eventos, dispone de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e82b6-169">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="e82b6-170">Publicar el evento de integración justo después de confirmar la transacción y usar otra transacción local para marcar los eventos en la tabla como "en proceso de publicación".</span><span class="sxs-lookup"><span data-stu-id="e82b6-170">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="e82b6-171">Después, usar la tabla como si fuera un artefacto para realizar el seguimiento de los eventos de integración en el caso de que se produzcan problemas en los microservicios remotos y realizar acciones de compensación en función de los eventos de integración almacenados.</span><span class="sxs-lookup"><span data-stu-id="e82b6-171">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="e82b6-172">Usar la tabla como una especie de cola.</span><span class="sxs-lookup"><span data-stu-id="e82b6-172">Use the table as a kind of queue.</span></span> <span data-ttu-id="e82b6-173">Un proceso o subproceso de aplicación independiente consulta la tabla de eventos de integración, publica los eventos en el bus de eventos y, después, usa una transacción local para marcar los eventos como publicados.</span><span class="sxs-lookup"><span data-stu-id="e82b6-173">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="e82b6-174">En la figura 8-22 se muestra la arquitectura para el primero de estos enfoques.</span><span class="sxs-lookup"><span data-stu-id="e82b6-174">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="e82b6-175">**Figura 8-22**.</span><span class="sxs-lookup"><span data-stu-id="e82b6-175">**Figure 8-22**.</span></span> <span data-ttu-id="e82b6-176">Atomicidad al publicar eventos en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-176">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="e82b6-177">En el enfoque que se muestra en la figura 8-22 falta un microservicio de trabajo adicional que se encarga de comprobar y confirmar que los eventos de integración se han publicado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-177">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="e82b6-178">En caso de error, ese microservicio de trabajo de comprobación adicional puede leer los eventos de la tabla y volver a publicarlos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-178">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="e82b6-179">Sobre el segundo enfoque: se usa la tabla EventLog como una cola y siempre se usa un microservicio de trabajo para publicar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e82b6-179">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="e82b6-180">En ese caso, el proceso es similar al que se muestra en la figura 8-23.</span><span class="sxs-lookup"><span data-stu-id="e82b6-180">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="e82b6-181">Esto muestra un microservicio adicional y la tabla es el único origen cuando se publican los eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-181">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="e82b6-182">**Figura 8-23**.</span><span class="sxs-lookup"><span data-stu-id="e82b6-182">**Figure 8-23**.</span></span> <span data-ttu-id="e82b6-183">Atomicidad al publicar eventos en el bus de eventos con un microservicio de trabajo</span><span class="sxs-lookup"><span data-stu-id="e82b6-183">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="e82b6-184">Para simplificar, en el ejemplo eShopOnContainers se usa el primer enfoque (sin procesos adicionales ni microservicios de comprobador) junto con el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-184">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="e82b6-185">Pero en eShopOnContainers no se controlan todos los casos de error posibles.</span><span class="sxs-lookup"><span data-stu-id="e82b6-185">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="e82b6-186">En una aplicación real implementada en la nube, debe asumir el hecho de que con el tiempo van a surgir problemas, y debe implementar esa lógica de comprobación y reenvío.</span><span class="sxs-lookup"><span data-stu-id="e82b6-186">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="e82b6-187">El uso de la tabla como una cola puede ser más eficaz que el primer enfoque si tiene esa tabla como un único origen de eventos cuando los publica a través del bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-187">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="e82b6-188">Implementación de la atomicidad al publicar eventos de integración a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-188">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="e82b6-189">En el código siguiente se muestra la forma de crear una única transacción que implica varios objetos DbContext, un contexto relacionado con los datos originales que se van a actualizar y el segundo relacionado con la tabla IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="e82b6-189">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="e82b6-190">Tenga en cuenta que la transacción en el código de ejemplo siguiente no será resistente si las conexiones a la base de datos tienen algún problema cuando se ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="e82b6-190">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="e82b6-191">Esto puede ocurrir en sistemas de servidor basados en la nube como Azure SQL DB, en los que es posible que las bases de datos se muevan entre servidores.</span><span class="sxs-lookup"><span data-stu-id="e82b6-191">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="e82b6-192">Para implementar transacciones resistentes entre varios contextos, vea la sección [Implementación de conexiones resistentes de Entity Framework Core SQL](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="e82b6-192">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](../implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md) section later in this guide.</span></span>

<span data-ttu-id="e82b6-193">Para evitar confusiones, en el ejemplo siguiente se muestra el proceso completo en un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="e82b6-193">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="e82b6-194">Pero la implementación de eShopOnContainers realmente se refactoriza y divide esta lógica en varias clases para que sea más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="e82b6-194">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

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

      // Publish the intergation event through the event bus
      _eventBus.Publish(priceChangedEvent); 

      integrationEventLogService.MarkEventAsPublishedAsync(
                                                priceChangedEvent); 
  }

  return Ok();
}

```

<span data-ttu-id="e82b6-195">Después de crear el evento de integración ProductPriceChangedIntegrationEvent, la transacción que almacena la operación de dominio original (la actualización del elemento de catálogo) también incluye la persistencia del evento en la tabla EventLog.</span><span class="sxs-lookup"><span data-stu-id="e82b6-195">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="e82b6-196">Esto crea una única transacción y siempre se podrá comprobar si los mensajes de eventos se han enviado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-196">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="e82b6-197">La tabla de registro de eventos se actualiza de forma atómica con la operación de base de datos original, mediante una transacción local en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-197">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="e82b6-198">Si se produce un error en alguna de las operaciones, se produce una excepción y la transacción revierte cualquier operación completada, lo que mantiene la coherencia entre las operaciones de dominio y los mensajes de eventos enviados.</span><span class="sxs-lookup"><span data-stu-id="e82b6-198">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="e82b6-199">Recepción de mensajes desde suscripciones: controladores de eventos en microservicios de receptor</span><span class="sxs-lookup"><span data-stu-id="e82b6-199">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="e82b6-200">Además de la lógica de suscripción de eventos, debe implementar el código interno para los controladores de eventos de integración (por ejemplo, un método de devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="e82b6-200">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="e82b6-201">En el controlador de eventos se especifica dónde se reciben y procesan los mensajes de eventos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-201">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="e82b6-202">Un controlador de eventos recibe por primera vez una instancia de evento desde el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-202">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="e82b6-203">Después, busca el componente que se va a procesar relacionado con ese evento de integración y lo propaga y conserva como un cambio de estado en el microservicio de receptor.</span><span class="sxs-lookup"><span data-stu-id="e82b6-203">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="e82b6-204">Por ejemplo, si un evento ProductPriceChanged se origina en el microservicio de catálogo, se controla en el microservicio de cesta de la compra y también cambia el estado en este microservicio de receptor, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-204">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="e82b6-205">El controlador de eventos debe comprobar si el producto existe en cualquiera de las instancias de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="e82b6-205">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="e82b6-206">También actualiza el precio del artículo para cada artículo de línea de la cesta de la compra relacionado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-206">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="e82b6-207">Por último, crea una alerta que se mostrará al usuario sobre el cambio de precio, como se muestra en la figura 8-24.</span><span class="sxs-lookup"><span data-stu-id="e82b6-207">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="e82b6-208">**Figura 8-24**.</span><span class="sxs-lookup"><span data-stu-id="e82b6-208">**Figure 8-24**.</span></span> <span data-ttu-id="e82b6-209">Representación de un cambio del precio de un artículo en una cesta, comunicado por eventos de integración</span><span class="sxs-lookup"><span data-stu-id="e82b6-209">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="e82b6-210">Idempotencia en los eventos de mensajes de actualización</span><span class="sxs-lookup"><span data-stu-id="e82b6-210">Idempotency in update message events</span></span>

<span data-ttu-id="e82b6-211">Un aspecto importante de los eventos de mensaje de actualización es que un error en cualquier punto de la comunicación debe hacer que se vuelva a intentar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e82b6-211">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="e82b6-212">En caso contrario, es posible que una tarea en segundo plano intente publicar un evento que ya se ha publicado, lo que genera una condición de carrera.</span><span class="sxs-lookup"><span data-stu-id="e82b6-212">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="e82b6-213">Es necesario asegurarse de que las actualizaciones son idempotentes o que proporcionan información suficiente para garantizar que un duplicado se pueda detectar, descartarlo y devolver una sola respuesta.</span><span class="sxs-lookup"><span data-stu-id="e82b6-213">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="e82b6-214">Como se indicó anteriormente, idempotencia significa que una operación se puede realizar varias veces sin cambiar el resultado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-214">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="e82b6-215">En un entorno de mensajería, como al comunicar eventos, un evento es idempotente si se puede entregar varias veces sin cambiar el resultado del microservicio receptor.</span><span class="sxs-lookup"><span data-stu-id="e82b6-215">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="e82b6-216">Esto puede ser necesario debido a la naturaleza del propio evento, o bien al modo en que el sistema controla el evento.</span><span class="sxs-lookup"><span data-stu-id="e82b6-216">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="e82b6-217">La idempotencia de mensajes es importante en cualquier aplicación en la que se use la mensajería, no solo en las aplicaciones que implementan el patrón de bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-217">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="e82b6-218">Un ejemplo de una operación idempotente es una instrucción SQL que inserta datos en una tabla solo si esos datos no están ya en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e82b6-218">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="e82b6-219">No importa cuántas veces se ejecute esa instrucción SQL de inserción; el resultado será el mismo: la tabla contendrá esos datos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-219">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="e82b6-220">Este tipo de idempotencia también puede ser necesaria cuando se trabaja con mensajes si existe la posibilidad de que se envíen y, por tanto, se procesen más de una vez.</span><span class="sxs-lookup"><span data-stu-id="e82b6-220">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="e82b6-221">Por ejemplo, si la lógica de reintento hace que un remitente envíe exactamente el mismo mensaje más de una vez, tendrá que asegurarse de que sea idempotente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-221">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="e82b6-222">Se pueden diseñar mensajes idempotentes.</span><span class="sxs-lookup"><span data-stu-id="e82b6-222">It is possible to design idempotent messages.</span></span> <span data-ttu-id="e82b6-223">Por ejemplo, puede crear un evento que indique "establecer el precio del producto en 25 USD" en lugar de "sumar 5 USD al precio del producto."</span><span class="sxs-lookup"><span data-stu-id="e82b6-223">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="e82b6-224">Podría procesar sin riesgos el primer mensaje cualquier número de veces y el resultado sería el mismo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-224">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="e82b6-225">Esto no es cierto para el segundo mensaje.</span><span class="sxs-lookup"><span data-stu-id="e82b6-225">That is not true for the second message.</span></span> <span data-ttu-id="e82b6-226">Pero incluso en el primer caso, es posible que no le interese procesar el primer evento, porque el sistema también podría haber enviado un evento de cambio de precio más reciente y se podría sobrescribir el precio de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e82b6-226">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="e82b6-227">Otro ejemplo podría ser un evento de pedido completado que se propaga a varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e82b6-227">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="e82b6-228">Es importante que la información del pedido se actualice una sola vez en otros sistemas, incluso si hay eventos de mensaje duplicados para el mismo evento de pedido completado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-228">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="e82b6-229">Es conveniente tener algún tipo de identidad por evento para poder crear lógica que exija que cada evento se procese solo una vez por cada receptor.</span><span class="sxs-lookup"><span data-stu-id="e82b6-229">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="e82b6-230">Algún procesamiento de mensajes es idempotente de forma inherente.</span><span class="sxs-lookup"><span data-stu-id="e82b6-230">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="e82b6-231">Por ejemplo, si un sistema genera imágenes en miniatura, es posible que no importe cuántas veces se procesa el mensaje sobre la miniatura generada; el resultado es que las miniaturas se generan y son iguales cada vez.</span><span class="sxs-lookup"><span data-stu-id="e82b6-231">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="e82b6-232">Por otra parte, las operaciones como la llamada a una pasarela de pagos para cobrar una tarjeta de crédito no pueden ser idempotentes.</span><span class="sxs-lookup"><span data-stu-id="e82b6-232">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="e82b6-233">En estos casos, debe asegurarse de que el procesamiento repetido de un mensaje tiene el efecto que se espera.</span><span class="sxs-lookup"><span data-stu-id="e82b6-233">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e82b6-234">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e82b6-234">Additional resources</span></span>

-   <span data-ttu-id="e82b6-235">**Honoring message idempotency** (Respetar la idempotencia de los mensajes; subencabezado de esta página) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="e82b6-235">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/library/jj591565.aspx*](https://msdn.microsoft.com/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="e82b6-236">Desduplicación de mensajes de eventos de integración</span><span class="sxs-lookup"><span data-stu-id="e82b6-236">Deduplicating integration event messages</span></span>

<span data-ttu-id="e82b6-237">Puede asegurarse de que los eventos de mensajes se envían y se procesan una sola vez por cada suscriptor en niveles diferentes.</span><span class="sxs-lookup"><span data-stu-id="e82b6-237">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="e82b6-238">Una manera de hacerlo consiste en usar una característica de desduplicación que ofrece la infraestructura de mensajería en uso.</span><span class="sxs-lookup"><span data-stu-id="e82b6-238">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="e82b6-239">Otra consiste en implementar lógica personalizada en el microservicio de destino.</span><span class="sxs-lookup"><span data-stu-id="e82b6-239">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="e82b6-240">Lo mejor es tener validaciones en el nivel de transporte y el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e82b6-240">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="e82b6-241">Desduplicación de eventos de mensaje en el nivel de controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="e82b6-241">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="e82b6-242">Una manera de asegurarse de que un evento se procesa solo una vez por cualquier receptor es mediante la implementación de cierta lógica al procesar los eventos de mensaje en controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="e82b6-242">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="e82b6-243">Por ejemplo, es el enfoque que se usa en la aplicación eShopOnContainers, como se puede ver en el [código fuente](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) de la clase OrdersController cuando recibe un comando CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="e82b6-243">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="e82b6-244">(En este caso se usa un comando de solicitud HTTP, no un comando basado en mensajes, pero la lógica que se necesita para que un comando basado en mensajes sea idempotente es similar).</span><span class="sxs-lookup"><span data-stu-id="e82b6-244">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="e82b6-245">Desduplicación de mensajes cuando se usa RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="e82b6-245">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="e82b6-246">Cuando se producen errores de red intermitentes, los mensajes se pueden duplicar y el receptor del mensaje debe estar listo para controlar estos mensajes duplicados.</span><span class="sxs-lookup"><span data-stu-id="e82b6-246">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="e82b6-247">Si es posible, los receptores deben controlar los mensajes de una manera idempotente, lo que es mejor que controlarlos de forma explícita mediante desduplicación.</span><span class="sxs-lookup"><span data-stu-id="e82b6-247">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="e82b6-248">Según la [documentación de RabbitMQ](https://www.rabbitmq.com/reliability.html#consumer), "si un mensaje se entrega a un consumidor y después se vuelve a poner en la cola (porque no se confirmó antes de desconectar la conexión del consumidor, por ejemplo), RabbitMQ establecerá la marca "entregado de nuevo" cuando se vuelva a entregar (con independencia de que sea al mismo consumidor o a otro)".</span><span class="sxs-lookup"><span data-stu-id="e82b6-248">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="e82b6-249">Si se establece la marca "entregado de nuevo", el receptor debe tenerlo en cuenta, dado que es posible que el mensaje ya se haya procesado.</span><span class="sxs-lookup"><span data-stu-id="e82b6-249">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="e82b6-250">Pero eso no está garantizado; es posible que el mensaje nunca llegara al receptor después de salir del agente de mensajes, quizás debido a problemas de red.</span><span class="sxs-lookup"><span data-stu-id="e82b6-250">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="e82b6-251">Por otro lado, si no se estableció la marca "entregado de nuevo", se garantiza que el mensaje no se ha enviado más de una vez.</span><span class="sxs-lookup"><span data-stu-id="e82b6-251">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="e82b6-252">Por tanto, el receptor debe desduplicar o procesar los mensajes de una manera idempotente solo si se establece la marca "entregado de nuevo" en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e82b6-252">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="e82b6-253">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e82b6-253">Additional resources</span></span>

-   <span data-ttu-id="e82b6-254">**Forked eShopOnContainers using NServiceBus (Particular Software) [Bifurcación de eShopOnContainers mediante NServiceBus (Particular Software)]**
    [*https://go.particular.net/eShopOnContainers*](https://go.particular.net/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="e82b6-254">**Forked eShopOnContainers using NServiceBus (Particular Software)**
[*https://go.particular.net/eShopOnContainers*](https://go.particular.net/eShopOnContainers)</span></span>

-   <span data-ttu-id="e82b6-255">**Event Driven Messaging**
    [*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging) (Mensajería controlada por eventos)</span><span class="sxs-lookup"><span data-stu-id="e82b6-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="e82b6-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling (Refactorización hacia la resiliencia: evaluar el acoplamiento)**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="e82b6-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="e82b6-257">**Publish-Subscribe channel (Canal de publicación y suscripción)**
    [*https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="e82b6-257">**Publish-Subscribe channel**
[*https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](https://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="e82b6-258">**Communicating Between Bounded Contexts (Comunicación entre contextos delimitados)**
    [*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="e82b6-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/library/jj591572.aspx*](https://msdn.microsoft.com/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="e82b6-259">**Eventual Consistency**
    [*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency) (Coherencia eventual)</span><span class="sxs-lookup"><span data-stu-id="e82b6-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="e82b6-260">**Philip Brown. Strategies for Integrating Bounded Contexts (Estrategias para integrar contextos delimitados)**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="e82b6-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="e82b6-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2 (Desarrollar microservicios transaccionales mediante agregados, orígenes de eventos y CQRS: parte 2)**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="e82b6-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="e82b6-262">**Chris Richardson. Event Sourcing pattern (Patrón de orígenes de eventos)**
    [*https://microservices.io/patterns/data/event-sourcing.html*](https://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="e82b6-262">**Chris Richardson. Event Sourcing pattern**
[*https://microservices.io/patterns/data/event-sourcing.html*](https://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="e82b6-263">**Introducing Event Sourcing (Introducción a los orígenes de eventos)**
    [*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="e82b6-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/library/jj591559.aspx*](https://msdn.microsoft.com/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="e82b6-264">**Base de datos Event Store**.</span><span class="sxs-lookup"><span data-stu-id="e82b6-264">**Event Store database**.</span></span> <span data-ttu-id="e82b6-265">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="e82b6-265">Official site.</span></span>
    [*https://geteventstore.com/*](https://geteventstore.com/)

-   <span data-ttu-id="e82b6-266">**Patrick Nommensen. Event-Driven Data Management for Microservices (Administración de datos orientada a eventos para microservicios)**
    \*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> \*</span><span class="sxs-lookup"><span data-stu-id="e82b6-266">**Patrick Nommensen. Event-Driven Data Management for Microservices**
\*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> \*</span></span>

-   <span data-ttu-id="e82b6-267">**Teorema CAP**
    [*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="e82b6-267">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="e82b6-268">**What is CAP Theorem? (¿Qué es el teorema CAP?)**
    [*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="e82b6-268">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="e82b6-269">**Data Consistency Primer (Manual de coherencia de datos)**
    [*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="e82b6-269">**Data Consistency Primer**
[*https://msdn.microsoft.com/library/dn589800.aspx*](https://msdn.microsoft.com/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="e82b6-270">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet (Teorema CAP: por qué “todo es diferente” con la nube e Internet)**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="e82b6-270">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="e82b6-271">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed (CAP doce años después: cómo han cambiado las “reglas”)**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="e82b6-271">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="e82b6-272">**Participating in External (DTC) Transactions** (MSMQ)[*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c) (Participación en transacciones externas (DTC) (MSMQ))</span><span class="sxs-lookup"><span data-stu-id="e82b6-272">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="e82b6-273">**Azure Service Bus. Brokered Messaging: Duplicate Detection (Mensajería asincrónica: detección de duplicados)**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="e82b6-273">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="e82b6-274">**Reliability Guide** (RabbitMQ documentation)[*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer) (Guía de confiabilidad (documentación de RabbitMQ))</span><span class="sxs-lookup"><span data-stu-id="e82b6-274">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="e82b6-275">[Anterior](rabbitmq-event-bus-development-test-environment.md)
[Siguiente](test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e82b6-275">[Previous](rabbitmq-event-bus-development-test-environment.md)
[Next](test-aspnet-core-services-web-apps.md)</span></span>
