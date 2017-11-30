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
# <a name="subscribing-to-events"></a><span data-ttu-id="49efa-104">Suscribirse a eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-104">Subscribing to events</span></span>

<span data-ttu-id="49efa-105">El primer paso para usar el bus de eventos es suscribirse el microservicios a los eventos que se desean recibir.</span><span class="sxs-lookup"><span data-stu-id="49efa-105">The first step for using the event bus is to subscribe the microservices to the events they want to receive.</span></span> <span data-ttu-id="49efa-106">Que debe realizarse en el microservicios de receptor.</span><span class="sxs-lookup"><span data-stu-id="49efa-106">That should be done in the receiver microservices.</span></span>

<span data-ttu-id="49efa-107">El siguiente código simple muestra lo que cada microservicio receptor se debe implementar al iniciar el servicio (es decir, en el inicio de la clase) para que suscribe a los eventos necesita.</span><span class="sxs-lookup"><span data-stu-id="49efa-107">The following simple code shows what each receiver microservice needs to implement when starting the service (that is, in the Startup class) so it subscribes to the events it needs.</span></span> <span data-ttu-id="49efa-108">Por ejemplo, el microservicio basket.api debe suscribirse a mensajes ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="49efa-108">For instance, the basket.api microservice needs to subscribe to ProductPriceChangedIntegrationEvent messages.</span></span> <span data-ttu-id="49efa-109">Esto hace que el microservicio consciente de los cambios en el precio del producto y le permite advertir al usuario sobre el cambio si ése es el producto en la cesta de compra del usuario.</span><span class="sxs-lookup"><span data-stu-id="49efa-109">This makes the microservice aware of any changes to the product price and lets it warn the user about the change if that product is in the user’s basket.</span></span>

```csharp
var eventBus = app.ApplicationServices.GetRequiredService<IEventBus>();
eventBus.Subscribe<ProductPriceChangedIntegrationEvent>(
    ProductPriceChangedIntegrationEventHandler);
```

<span data-ttu-id="49efa-110">Después de ejecuta este código, el suscriptor microservicio escucharán a través de canales de RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="49efa-110">After this code runs, the subscriber microservice will be listening through RabbitMQ channels.</span></span> <span data-ttu-id="49efa-111">Cuando llega algún mensaje de tipo ProductPriceChangedIntegrationEvent, el código invoca el controlador de eventos que recibe y procesa el evento.</span><span class="sxs-lookup"><span data-stu-id="49efa-111">When any message of type ProductPriceChangedIntegrationEvent arrives, the code invokes the event handler that is passed to it and processes the event.</span></span>

## <a name="publishing-events-through-the-event-bus"></a><span data-ttu-id="49efa-112">Publicación de eventos a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-112">Publishing events through the event bus</span></span>

<span data-ttu-id="49efa-113">Por último, el remitente del mensaje (origen microservicio) publica los eventos de integración con código similar al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="49efa-113">Finally, the message sender (origin microservice) publishes the integration events with code similar to the following example.</span></span> <span data-ttu-id="49efa-114">(Esto es un ejemplo simplificado que no tome atomicidad en cuenta). Debería implementar código similar cada vez que un evento se debe difundir a través de varios microservicios, normalmente inmediatamente después de confirmar los datos o transacciones desde el origen de microservicio.</span><span class="sxs-lookup"><span data-stu-id="49efa-114">(This is a simplified example that does not take atomicity into account.) You would implement similar code whenever an event must be propagated across multiple microservices, usually right after committing data or transactions from the origin microservice.</span></span>

<span data-ttu-id="49efa-115">En primer lugar, el objeto de implementación del bus de eventos (basada en RabbitMQ o en un bus de servicio) se insertará en el constructor del controlador, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="49efa-115">First, the event bus implementation object (based on RabbitMQ or based on a service bus) would be injected at the controller constructor, as in the following code:</span></span>

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

<span data-ttu-id="49efa-116">A continuación, se usa entre métodos de su dispositivo, como en el método UpdateProduct:</span><span class="sxs-lookup"><span data-stu-id="49efa-116">Then you use it from your controller’s methods, like in the UpdateProduct method:</span></span>

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

<span data-ttu-id="49efa-117">En este caso, puesto que la microservicio de origen es un microservicio CRUD simple, ese código se coloca derecha en un controlador de Web API.</span><span class="sxs-lookup"><span data-stu-id="49efa-117">In this case, since the origin microservice is a simple CRUD microservice, that code is placed right into a Web API controller.</span></span> <span data-ttu-id="49efa-118">En microservicios más avanzadas, se puede implementar en la clase CommandHandler, derecho después de que se confirmen los datos originales.</span><span class="sxs-lookup"><span data-stu-id="49efa-118">In more advanced microservices, it could be implemented in the CommandHandler class, right after the original data is committed.</span></span>

### <a name="designing-atomicity-and-resiliency-when-publishing-to-the-event-bus"></a><span data-ttu-id="49efa-119">Diseñar la atomicidad y la resistencia al publicar en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-119">Designing atomicity and resiliency when publishing to the event bus</span></span>

<span data-ttu-id="49efa-120">Al publicar eventos de integración a través de un marco de mensajería distribuida sistema al igual que el bus de eventos, tiene el problema de actualización de la base de datos original de forma atómica y publica un evento.</span><span class="sxs-lookup"><span data-stu-id="49efa-120">When you publish integration events through a distributed messaging system like your event bus, you have the problem of atomically updating the original database and publishing an event.</span></span> <span data-ttu-id="49efa-121">Por ejemplo, en el ejemplo simplificado que se muestra anteriormente, el código confirma los datos a la base de datos el precio del producto se cambia y, a continuación, publica un mensaje ProductPriceChangedIntegrationEvent.</span><span class="sxs-lookup"><span data-stu-id="49efa-121">For instance, in the simplified example shown earlier, the code commits data to the database when the product price is changed and then publishes a ProductPriceChangedIntegrationEvent message.</span></span> <span data-ttu-id="49efa-122">En principio, puede tener un aspecto fundamental que estas dos operaciones puede realizar de forma atómica.</span><span class="sxs-lookup"><span data-stu-id="49efa-122">Initially, it might look essential that these two operations be performed atomically.</span></span> <span data-ttu-id="49efa-123">Sin embargo, si está utilizando una transacción distribuida que implican la base de datos y el mensaje de broker, como se hace en sistemas anteriores como [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), no se recomienda por las razones descritas por el [Teorema CAP](https://www.quora.com/What-Is-CAP-Theorem-1).</span><span class="sxs-lookup"><span data-stu-id="49efa-123">However, if you are using a distributed transaction involving the database and the message broker, as you do in older systems like [Microsoft Message Queuing (MSMQ)](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx), this is not recommended for the reasons described by the [CAP theorem](https://www.quora.com/What-Is-CAP-Theorem-1).</span></span>

<span data-ttu-id="49efa-124">Básicamente, use microservicios para crear sistemas de alta disponibilidad y escalables.</span><span class="sxs-lookup"><span data-stu-id="49efa-124">Basically, you use microservices to build scalable and highly available systems.</span></span> <span data-ttu-id="49efa-125">Simplificar un poco, el teorema CAP indica que no se puede crear una base de datos (o un microservicio que posee su modelo) que está continuamente disponible, muy coherente, *y* tolerante a cualquier otra partición.</span><span class="sxs-lookup"><span data-stu-id="49efa-125">Simplifying somewhat, the CAP theorem says that you cannot build a database (or a microservice that owns its model) that is continually available, strongly consistent, *and* tolerant to any partition.</span></span> <span data-ttu-id="49efa-126">Debe elegir dos de estas tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="49efa-126">You must choose two of these three properties.</span></span>

<span data-ttu-id="49efa-127">En las arquitecturas basadas en microservicios, debe elegir disponibilidad y tolerancia y debe caso homogeneidad.</span><span class="sxs-lookup"><span data-stu-id="49efa-127">In microservices-based architectures, you should choose availability and tolerance, and you should deemphasize strong consistency.</span></span> <span data-ttu-id="49efa-128">Por lo tanto, en las aplicaciones más modernas basada en microservicio, normalmente no desea usar transacciones distribuidas en mensajería, tal y como haría al implementar [transacciones distribuidas](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) en función de la transacción distribuida de Windows DTC (Coordinador) con [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="49efa-128">Therefore, in most modern microservice-based applications, you usually do not want to use distributed transactions in messaging, as you do when you implement [distributed transactions](https://msdn.microsoft.com/library/ms978430.aspx#bdadotnetasync2_topic3c) based on the Windows Distributed Transaction Coordinator (DTC) with [MSMQ](https://msdn.microsoft.com/library/ms711472(v=vs.85).aspx).</span></span>

<span data-ttu-id="49efa-129">Volvamos a su ejemplo y el problema inicial.</span><span class="sxs-lookup"><span data-stu-id="49efa-129">Let’s go back to the initial issue and its example.</span></span> <span data-ttu-id="49efa-130">Si el servicio se bloquea después de actualiza la base de datos (en este caso, justo después de la línea de código con \_contexto. SaveChangesAsync()), pero antes de que se publica el evento de integración, el sistema global puede volverse incoherente.</span><span class="sxs-lookup"><span data-stu-id="49efa-130">If the service crashes after the database is updated (in this case, right after the line of code with \_context.SaveChangesAsync()), but before the integration event is published, the overall system could become inconsistent.</span></span> <span data-ttu-id="49efa-131">Esto podría ser empresariales críticas, dependiendo de la operación empresarial específica que está tratando con.</span><span class="sxs-lookup"><span data-stu-id="49efa-131">This might be business critical, depending on the specific business operation you are dealing with.</span></span>

<span data-ttu-id="49efa-132">Como se mencionó anteriormente en la sección de arquitectura, puede tener varios enfoques para tratar este problema:</span><span class="sxs-lookup"><span data-stu-id="49efa-132">As mentioned earlier in the architecture section, you can have several approaches for dealing with this issue:</span></span>

-   <span data-ttu-id="49efa-133">La completo [patrón de eventos de origen](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span><span class="sxs-lookup"><span data-stu-id="49efa-133">Using the full [Event Sourcing pattern](https://msdn.microsoft.com/en-us/library/dn589792.aspx).</span></span>

-   <span data-ttu-id="49efa-134">Usar [minería de datos del registro de transacciones](http://www.scoop.it/t/sql-server-transaction-log-mining).</span><span class="sxs-lookup"><span data-stu-id="49efa-134">Using [transaction log mining](http://www.scoop.it/t/sql-server-transaction-log-mining).</span></span>

-   <span data-ttu-id="49efa-135">Mediante el [patrón de bandeja de salida](http://gistlabs.com/2014/05/the-outbox/).</span><span class="sxs-lookup"><span data-stu-id="49efa-135">Using the [Outbox pattern](http://gistlabs.com/2014/05/the-outbox/).</span></span> <span data-ttu-id="49efa-136">Se trata de una tabla transaccional para almacenar los eventos de integración (extendiendo la transacción local).</span><span class="sxs-lookup"><span data-stu-id="49efa-136">This is a transactional table to store the integration events (extending the local transaction).</span></span>

<span data-ttu-id="49efa-137">En este escenario, utilizando el modelo de origen de evento (ES) completa es uno de los mejores métodos, si no *el* mejor.</span><span class="sxs-lookup"><span data-stu-id="49efa-137">For this scenario, using the full Event Sourcing (ES) pattern is one of the best approaches, if not *the* best.</span></span> <span data-ttu-id="49efa-138">Sin embargo, en muchas situaciones, es posible que no pueda implementar completa del sistema ES.</span><span class="sxs-lookup"><span data-stu-id="49efa-138">However, in many application scenarios, you might not be able to implement a full ES system.</span></span> <span data-ttu-id="49efa-139">ES significa almacenar solo los eventos de dominio en la base de datos transaccional, en lugar de almacenar los datos de estado actual.</span><span class="sxs-lookup"><span data-stu-id="49efa-139">ES means storing only domain events in your transactional database, instead of storing current state data.</span></span> <span data-ttu-id="49efa-140">Almacenar solo los eventos de dominio puede tener grandes ventajas, como tener el historial del sistema disponible y ser capaz de determinar el estado del sistema en cualquier momento en el pasado.</span><span class="sxs-lookup"><span data-stu-id="49efa-140">Storing only domain events can have great benefits, such as having the history of your system available and being able to determine the state of your system at any moment in the past.</span></span> <span data-ttu-id="49efa-141">Sin embargo, la implementación completa del sistema ES requiere que cambie la arquitectura de la mayor parte de su sistema y presenta muchas otras complejidades y requisitos.</span><span class="sxs-lookup"><span data-stu-id="49efa-141">However, implementing a full ES system requires you to rearchitect most of your system and introduces many other complexities and requirements.</span></span> <span data-ttu-id="49efa-142">Por ejemplo, ¿desea usar una base de datos que realizó específicamente para originar el evento, como [almacén de eventos](https://geteventstore.com/), o una base de datos orientada a servicios de documento como base de datos de Azure Cosmos, MongoDB, Casandra, CouchDB o RavenDB.</span><span class="sxs-lookup"><span data-stu-id="49efa-142">For example, you would want to use a database specifically made for event sourcing, such as [Event Store](https://geteventstore.com/), or a document-oriented database such as Azure Cosmos DB, MongoDB, Cassandra, CouchDB, or RavenDB.</span></span> <span data-ttu-id="49efa-143">ES es un buen método para este problema, pero no la solución más fácil a menos que ya está familiarizado con el origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-143">ES is a great approach for this problem, but not the easiest solution unless you are already familiar with event sourcing.</span></span>

<span data-ttu-id="49efa-144">La opción para usar el registro de transacciones inicialmente de minería de datos tiene un aspecto muy transparente.</span><span class="sxs-lookup"><span data-stu-id="49efa-144">The option to use transaction log mining initially looks very transparent.</span></span> <span data-ttu-id="49efa-145">Sin embargo, para utilizar este enfoque, el microservicio debe acoplarse en el registro de transacciones de RDBMS, como el registro de transacciones de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49efa-145">However, to use this approach, the microservice has to be coupled to your RDBMS transaction log, such as the SQL Server transaction log.</span></span> <span data-ttu-id="49efa-146">Esto probablemente no es deseable.</span><span class="sxs-lookup"><span data-stu-id="49efa-146">This is probably not desirable.</span></span> <span data-ttu-id="49efa-147">Otra desventaja es que las actualizaciones de bajo nivel en el registro de transacciones pueden no ser el mismo nivel que los eventos de integración de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="49efa-147">Another drawback is that the low-level updates recorded in the transaction log might not be at the same level as your high-level integration events.</span></span> <span data-ttu-id="49efa-148">Si es así, el proceso de ingeniería inversa esas operaciones de registro de transacciones pueden ser difíciles.</span><span class="sxs-lookup"><span data-stu-id="49efa-148">If so, the process of reverse-engineering those transaction log operations can be difficult.</span></span>

<span data-ttu-id="49efa-149">Un enfoque equilibrado es una combinación de una tabla de base de datos transaccional y un patrón ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="49efa-149">A balanced approach is a mix of a transactional database table and a simplified ES pattern.</span></span> <span data-ttu-id="49efa-150">Puede usar un estado como "listo para publicar el evento" que se establece en el evento original cuando se confirma en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="49efa-150">You can use a state such as “ready to publish the event,” which you set in the original event when you commit it to the integration events table.</span></span> <span data-ttu-id="49efa-151">A continuación, intente publicar el evento en el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-151">You then try to publish the event to the event bus.</span></span> <span data-ttu-id="49efa-152">Si la acción de evento de publicación se realiza correctamente, inicie otra transacción en el servicio de origen y mover el estado de "listo para publicar el evento" a "evento ya se han publicado".</span><span class="sxs-lookup"><span data-stu-id="49efa-152">If the publish-event action succeeds, you start another transaction in the origin service and move the state from “ready to publish the event” to “event already published.”</span></span>

<span data-ttu-id="49efa-153">Si la acción de evento de la publicación de bus en el evento se produce un error, los datos aún no serán incoherentes en la microservicio de origen, se marca como "listo para publicar el evento", y con respecto al resto de los servicios, eventualmente será coherente.</span><span class="sxs-lookup"><span data-stu-id="49efa-153">If the publish-event action in the event bus fails, the data still will not be inconsistent within the origin microservice—it is still marked as “ready to publish the event,” and with respect to the rest of the services, it will eventually be consistent.</span></span> <span data-ttu-id="49efa-154">Siempre puede tener la comprobación del estado de las transacciones o eventos de integración de trabajos en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="49efa-154">You can always have background jobs checking the state of the transactions or integration events.</span></span> <span data-ttu-id="49efa-155">Si el trabajo encuentra un evento en el estado "listo para publicar el evento", puede intentar volver a publicar ese evento para el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-155">If the job finds an event in the “ready to publish the event” state, it can try to republish that event to the event bus.</span></span>

<span data-ttu-id="49efa-156">Tenga en cuenta que con este enfoque, vaya a conservar sólo los eventos de integración para cada microservicio de origen y solo los eventos que desea comunicarse con otros microservicios o sistemas externos.</span><span class="sxs-lookup"><span data-stu-id="49efa-156">Notice that with this approach, you are persisting only the integration events for each origin microservice, and only the events that you want to communicate to other microservices or external systems.</span></span> <span data-ttu-id="49efa-157">En cambio, en un sistema ES completo, almacenar todos los eventos de dominio.</span><span class="sxs-lookup"><span data-stu-id="49efa-157">In contrast, in a full ES system, you store all domain events as well.</span></span>

<span data-ttu-id="49efa-158">Por lo tanto, este enfoque equilibrado es un sistema ES simplificado.</span><span class="sxs-lookup"><span data-stu-id="49efa-158">Therefore, this balanced approach is a simplified ES system.</span></span> <span data-ttu-id="49efa-159">Se necesita una lista de eventos de integración con su estado actual ("listo para publicar" frente a "publicar").</span><span class="sxs-lookup"><span data-stu-id="49efa-159">You need a list of integration events with their current state (“ready to publish” versus “published”).</span></span> <span data-ttu-id="49efa-160">Pero sólo necesita implementar estos Estados para los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="49efa-160">But you only need to implement these states for the integration events.</span></span> <span data-ttu-id="49efa-161">Y en este enfoque, no deberá almacenar todos los datos de dominio como los eventos de la base de datos transaccional, tal y como lo haría en un sistema ES completo.</span><span class="sxs-lookup"><span data-stu-id="49efa-161">And in this approach, you do not need to store all your domain data as events in the transactional database, as you would in a full ES system.</span></span>

<span data-ttu-id="49efa-162">Si ya se usa una base de datos relacional, puede usar una tabla transaccional para almacenar eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="49efa-162">If you are already using a relational database, you can use a transactional table to store integration events.</span></span> <span data-ttu-id="49efa-163">Para lograr la atomicidad en la aplicación, utilice un proceso de dos pasos basado en transacciones locales.</span><span class="sxs-lookup"><span data-stu-id="49efa-163">To achieve atomicity in your application, you use a two-step process based on local transactions.</span></span> <span data-ttu-id="49efa-164">Básicamente, dispone de una tabla IntegrationEvent en la misma base de datos donde haya las entidades de dominio.</span><span class="sxs-lookup"><span data-stu-id="49efa-164">Basically, you have an IntegrationEvent table in the same database where you have your domain entities.</span></span> <span data-ttu-id="49efa-165">Esa tabla funciona como un seguro para lograr la atomicidad para que incluyan guardar eventos de integración en las mismas transacciones que se están confirmando los datos de dominio.</span><span class="sxs-lookup"><span data-stu-id="49efa-165">That table works as an insurance for achieving atomicity so that you include persisted integration events into the same transactions that are committing your domain data.</span></span>

<span data-ttu-id="49efa-166">Paso a paso, el proceso se pasa como el siguiente: la aplicación inicia una transacción de base de datos local.</span><span class="sxs-lookup"><span data-stu-id="49efa-166">Step by step, the process goes like this: the application begins a local database transaction.</span></span> <span data-ttu-id="49efa-167">A continuación, se actualiza el estado de las entidades de dominio y se inserta un evento en la tabla de eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="49efa-167">It then updates the state of your domain entities and inserts an event into the integration event table.</span></span> <span data-ttu-id="49efa-168">Por último, confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="49efa-168">Finally, it commits the transaction.</span></span> <span data-ttu-id="49efa-169">Obtener la atomicidad deseada.</span><span class="sxs-lookup"><span data-stu-id="49efa-169">You get the desired atomicity.</span></span>

<span data-ttu-id="49efa-170">Al implementar los pasos necesarios para publicar los eventos, tienes estas opciones:</span><span class="sxs-lookup"><span data-stu-id="49efa-170">When implementing the steps of publishing the events, you have these choices:</span></span>

-   <span data-ttu-id="49efa-171">Publicar el evento integración justo después de confirmar la transacción y usar otra transacción local para marcar los eventos en la tabla que está publicando.</span><span class="sxs-lookup"><span data-stu-id="49efa-171">Publish the integration event right after committing the transaction and use another local transaction to mark the events in the table as being published.</span></span> <span data-ttu-id="49efa-172">A continuación, utilice la tabla al igual que un artefacto para realizar un seguimiento de los eventos de integración en el caso de problemas en el remoto microservicios y realizar acciones de compensación en función de los eventos de integración almacenado.</span><span class="sxs-lookup"><span data-stu-id="49efa-172">Then, use the table just as an artifact to track the integration events in case of issues in the remote microservices, and perform compensatory actions based on the stored integration events.</span></span>

-   <span data-ttu-id="49efa-173">Use la tabla como un tipo de cola.</span><span class="sxs-lookup"><span data-stu-id="49efa-173">Use the table as a kind of queue.</span></span> <span data-ttu-id="49efa-174">Un proceso o subproceso de aplicación independiente consulta la tabla de eventos de integración, publica los eventos en el bus de eventos y, a continuación, usa una transacción local para marcar los eventos como publicada.</span><span class="sxs-lookup"><span data-stu-id="49efa-174">A separate application thread or process queries the integration event table, publishes the events to the event bus, and then uses a local transaction to mark the events as published.</span></span>

<span data-ttu-id="49efa-175">Figura 8-22 muestra la arquitectura para el primero de estos enfoques.</span><span class="sxs-lookup"><span data-stu-id="49efa-175">Figure 8-22 shows the architecture for the first of these approaches.</span></span>

![](./media/image23.png)

<span data-ttu-id="49efa-176">**Figura 8-22**.</span><span class="sxs-lookup"><span data-stu-id="49efa-176">**Figure 8-22**.</span></span> <span data-ttu-id="49efa-177">Atomicidad al publicar eventos en el bus de eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-177">Atomicity when publishing events to the event bus</span></span>

<span data-ttu-id="49efa-178">El enfoque se muestra en la figura 8-22 falta un microservicio trabajo adicional que está a cargo de comprobación y confirmar el éxito de los eventos de integración publicado.</span><span class="sxs-lookup"><span data-stu-id="49efa-178">The approach illustrated in Figure 8-22 is missing an additional worker microservice that is in charge of checking and confirming the success of the published integration events.</span></span> <span data-ttu-id="49efa-179">En caso de error, ese microservicio de trabajo adicional Comprobador puede leer los eventos de la tabla y volver a publicarlos.</span><span class="sxs-lookup"><span data-stu-id="49efa-179">In case of failure, that additional checker worker microservice can read events from the table and republish them.</span></span>

<span data-ttu-id="49efa-180">Acerca del segundo enfoque: use la tabla de registro de eventos como una cola y siempre utilizan un microservicio de trabajo para publicar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="49efa-180">About the second approach: you use the EventLog table as a queue and always use a worker microservice to publish the messages.</span></span> <span data-ttu-id="49efa-181">En ese caso, el proceso que se muestra en la figura 8-23.</span><span class="sxs-lookup"><span data-stu-id="49efa-181">In that case, the process is like that shown in Figure 8-23.</span></span> <span data-ttu-id="49efa-182">Esto muestra un microservicio adicional y la tabla es el único origen cuando se publica los eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-182">This shows an additional microservice, and the table is the single source when publishing events.</span></span>

![](./media/image24.png)

<span data-ttu-id="49efa-183">**Figura 8-23**.</span><span class="sxs-lookup"><span data-stu-id="49efa-183">**Figure 8-23**.</span></span> <span data-ttu-id="49efa-184">Atomicidad al publicar eventos en el bus de eventos con un microservicio de trabajo</span><span class="sxs-lookup"><span data-stu-id="49efa-184">Atomicity when publishing events to the event bus with a worker microservice</span></span>

<span data-ttu-id="49efa-185">Para simplificar, el ejemplo eShopOnContainers usa el primer enfoque (con no hay procesos adicionales o Comprobador microservicios) junto con el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-185">For simplicity, the eShopOnContainers sample uses the first approach (with no additional processes or checker microservices) plus the event bus.</span></span> <span data-ttu-id="49efa-186">Sin embargo, la eShopOnContainers no controla todos los casos de error posibles.</span><span class="sxs-lookup"><span data-stu-id="49efa-186">However, the eShopOnContainers is not handling all possible failure cases.</span></span> <span data-ttu-id="49efa-187">En una aplicación real que se implementan en la nube, debe adoptar el hecho de que se van a surgir problemas al final, y debe implementar que comprobar y volver a enviar lógica.</span><span class="sxs-lookup"><span data-stu-id="49efa-187">In a real application deployed to the cloud, you must embrace the fact that issues will arise eventually, and you must implement that check and resend logic.</span></span> <span data-ttu-id="49efa-188">Con la tabla como una cola puede ser más eficaz que el primer enfoque si tiene esa tabla como un único origen de eventos al publicarlos a través del bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-188">Using the table as a queue can be more effective than the first approach if you have that table as a single source of events when publishing them through the event bus.</span></span>

### <a name="implementing-atomicity-when-publishing-integration-events-through-the-event-bus"></a><span data-ttu-id="49efa-189">Implementar atomicidad al publicar eventos de integración a través del bus de eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-189">Implementing atomicity when publishing integration events through the event bus</span></span>

<span data-ttu-id="49efa-190">El código siguiente muestra cómo puede crear una única transacción que implican varios objetos de DbContext, un contexto relacionado con los datos originales que se está actualizados y el segundo contexto relacionadas con la tabla IntegrationEventLog.</span><span class="sxs-lookup"><span data-stu-id="49efa-190">The following code shows how you can create a single transaction involving multiple DbContext objects—one context related to the original data being updated, and the second context related to the IntegrationEventLog table.</span></span>

<span data-ttu-id="49efa-191">Tenga en cuenta que la transacción en el código de ejemplo siguiente no será resistente a errores si las conexiones a la base de datos tienen algún problema en el momento cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="49efa-191">Note that the transaction in the example code below will not be resilient if connections to the database have any issue at the time when the code is running.</span></span> <span data-ttu-id="49efa-192">Esto puede ocurrir en sistemas de servidor basada en la nube como Azure SQL DB, que puede mover bases de datos entre servidores.</span><span class="sxs-lookup"><span data-stu-id="49efa-192">This can happen in cloud-based systems like Azure SQL DB, which might move databases across servers.</span></span> <span data-ttu-id="49efa-193">Para implementar las transacciones resistentes en varios contextos, consulte el [implementar conexiones de Entity Framework Core SQL resistentes](#implementing_resilient_EFCore_SQL_conns) sección más adelante en esta guía.</span><span class="sxs-lookup"><span data-stu-id="49efa-193">For implementing resilient transactions across multiple contexts, see the [Implementing resilient Entity Framework Core SQL connections](#implementing_resilient_EFCore_SQL_conns) section later in this guide.</span></span>

<span data-ttu-id="49efa-194">Para evitar confusiones, en el ejemplo siguiente se muestra todo el proceso en un único fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="49efa-194">For clarity, the following example shows the whole process in a single piece of code.</span></span> <span data-ttu-id="49efa-195">Sin embargo, la implementación de eShopOnContainers realmente se refactoriza y divide esta lógica en varias clases, por lo que es más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="49efa-195">However, the eShopOnContainers implementation is actually refactored and split this logic into multiple classes so it is easier to maintain.</span></span>

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

<span data-ttu-id="49efa-196">Después de crea el evento de integración de ProductPriceChangedIntegrationEvent, la transacción que almacena la operación de dominio original (actualizar el elemento de catálogo) también incluye la persistencia del evento en la tabla de registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-196">After the ProductPriceChangedIntegrationEvent integration event is created, the transaction that stores the original domain operation (update the catalog item) also includes the persistence of the event in the EventLog table.</span></span> <span data-ttu-id="49efa-197">Esto facilita una única transacción, y siempre podrá comprobar si se envían mensajes de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-197">This makes it a single transaction, and you will always be able to check whether event messages were sent.</span></span>

<span data-ttu-id="49efa-198">La tabla de registro de eventos se actualiza de forma atómica con la operación de base de datos original, usa una transacción local en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="49efa-198">The event log table is updated atomically with the original database operation, using a local transaction against the same database.</span></span> <span data-ttu-id="49efa-199">Si se produce un error en cualquiera de las operaciones, se produce una excepción y la transacción revierte cualquier operación completada, lo que mantiene la coherencia entre las operaciones de dominio y los mensajes de eventos enviados.</span><span class="sxs-lookup"><span data-stu-id="49efa-199">If any of the operations fail, an exception is thrown and the transaction rolls back any completed operation, thus maintaining consistency between the domain operations and the event messages sent.</span></span>

### <a name="receiving-messages-from-subscriptions-event-handlers-in-receiver-microservices"></a><span data-ttu-id="49efa-200">Recibir mensajes de las suscripciones: controladores de eventos de receptor microservicios</span><span class="sxs-lookup"><span data-stu-id="49efa-200">Receiving messages from subscriptions: event handlers in receiver microservices</span></span>

<span data-ttu-id="49efa-201">Además de la lógica de suscripción de eventos, debe implementar el código interno para los controladores de eventos de integración (por ejemplo, un método de devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="49efa-201">In addition to the event subscription logic, you need to implement the internal code for the integration event handlers (like a callback method).</span></span> <span data-ttu-id="49efa-202">El controlador de eventos es donde se especifican donde se se recibe y procesa los mensajes de eventos de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="49efa-202">The event handler is where you specify where the event messages of a certain type will be received and processed.</span></span>

<span data-ttu-id="49efa-203">Un controlador de eventos recibe por primera vez una instancia de evento desde el bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-203">An event handler first receives an event instance from the event bus.</span></span> <span data-ttu-id="49efa-204">A continuación, busca el componente para procesarse relacionados con ese evento de integración, propagación y conservar el evento como un cambio de estado en el receptor de microservicio.</span><span class="sxs-lookup"><span data-stu-id="49efa-204">Then it locates the component to be processed related to that integration event, propagating and persisting the event as a change in state in the receiver microservice.</span></span> <span data-ttu-id="49efa-205">Por ejemplo, si un evento ProductPriceChanged se origina en el catálogo de microservicio, se controla en el microservicio de la cesta de compras y cambia el estado en este microservicio de la cesta de compras de receptor, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="49efa-205">For example, if a ProductPriceChanged event originates in the catalog microservice, it is handled in the basket microservice and changes the state in this receiver basket microservice as well, as shown in the following code.</span></span>

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

<span data-ttu-id="49efa-206">El controlador de eventos debe comprobar si existe el producto en cualquiera de las instancias de la cesta de compra.</span><span class="sxs-lookup"><span data-stu-id="49efa-206">The event handler needs to verify whether the product exists in any of the basket instances.</span></span> <span data-ttu-id="49efa-207">También actualiza el precio del artículo para cada artículo de línea de la cesta de compra relacionados.</span><span class="sxs-lookup"><span data-stu-id="49efa-207">It also updates the item price for each related basket line item.</span></span> <span data-ttu-id="49efa-208">Por último, crea una alerta que se mostrará al usuario sobre el cambio de precio, tal como se muestra en la figura 8-24.</span><span class="sxs-lookup"><span data-stu-id="49efa-208">Finally, it creates an alert to be displayed to the user about the price change, as shown in Figure 8-24.</span></span>

![](./media/image25.png)

<span data-ttu-id="49efa-209">**Figura 8-24**.</span><span class="sxs-lookup"><span data-stu-id="49efa-209">**Figure 8-24**.</span></span> <span data-ttu-id="49efa-210">Mostrar un cambio de precio de artículo en una cesta comunicado por eventos de integración</span><span class="sxs-lookup"><span data-stu-id="49efa-210">Displaying an item price change in a basket, as communicated by integration events</span></span>

## <a name="idempotency-in-update-message-events"></a><span data-ttu-id="49efa-211">Idempotencia en eventos de mensaje de actualización</span><span class="sxs-lookup"><span data-stu-id="49efa-211">Idempotency in update message events</span></span>

<span data-ttu-id="49efa-212">Un aspecto importante de eventos de mensaje de actualización es que un error en cualquier punto de la comunicación debe hacer que el mensaje que volver a intentarse.</span><span class="sxs-lookup"><span data-stu-id="49efa-212">An important aspect of update message events is that a failure at any point in the communication should cause the message to be retried.</span></span> <span data-ttu-id="49efa-213">En caso contrario, una tarea en segundo plano que pueden intentar publicar un evento que ya se ha publicado, crear una condición de carrera.</span><span class="sxs-lookup"><span data-stu-id="49efa-213">Otherwise a background task might try to publish an event that has already been published, creating a race condition.</span></span> <span data-ttu-id="49efa-214">Es necesario para asegurarse de que las actualizaciones son idempotentes o que proporcionan información suficiente para garantizar que puede detectar un duplicado, descartar los cambios y Enviar atrás solo una respuesta.</span><span class="sxs-lookup"><span data-stu-id="49efa-214">You need to make sure that the updates are either idempotent or that they provide enough information to ensure that you can detect a duplicate, discard it, and send back only one response.</span></span>

<span data-ttu-id="49efa-215">Como se indicó anteriormente, Idempotencia significa que una operación se puede realizar varias veces sin cambiar el resultado.</span><span class="sxs-lookup"><span data-stu-id="49efa-215">As noted earlier, idempotency means that an operation can be performed multiple times without changing the result.</span></span> <span data-ttu-id="49efa-216">En un entorno de mensajería, como cuando se comunica eventos, un evento es idempotente si puede entregarse varias veces sin cambiar el resultado para el receptor de microservicio.</span><span class="sxs-lookup"><span data-stu-id="49efa-216">In a messaging environment, as when communicating events, an event is idempotent if it can be delivered multiple times without changing the result for the receiver microservice.</span></span> <span data-ttu-id="49efa-217">Esto puede ser necesario debido a la naturaleza del propio evento, o debido al modo en el sistema controla el evento.</span><span class="sxs-lookup"><span data-stu-id="49efa-217">This may be necessary because of the nature of the event itself, or because of the way the system handles the event.</span></span> <span data-ttu-id="49efa-218">Mensaje idempotencia es importante en cualquier aplicación que utilice la mensajería, no solo en las aplicaciones que implementan el patrón de bus de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-218">Message idempotency is important in any application that uses messaging, not just in applications that implement the event bus pattern.</span></span>

<span data-ttu-id="49efa-219">Un ejemplo de una operación idempotente es una instrucción SQL que inserta datos en una tabla solo si esos datos no están ya en la tabla.</span><span class="sxs-lookup"><span data-stu-id="49efa-219">An example of an idempotent operation is a SQL statement that inserts data into a table only if that data is not already in the table.</span></span> <span data-ttu-id="49efa-220">No importa cuántas veces se ejecuta que inserción la instrucción SQL; el resultado será el mismo, la tabla contendrá esos datos.</span><span class="sxs-lookup"><span data-stu-id="49efa-220">It does not matter how many times you run that insert SQL statement; the result will be the same—the table will contain that data.</span></span> <span data-ttu-id="49efa-221">También puede ser idempotencia parecido a esto es necesario cuando se trabaja con mensajes si los mensajes podrían ser potencialmente enviados y, por tanto, procesado más de una vez.</span><span class="sxs-lookup"><span data-stu-id="49efa-221">Idempotency like this can also be necessary when dealing with messages if the messages could potentially be sent and therefore processed more than once.</span></span> <span data-ttu-id="49efa-222">Por ejemplo, si la lógica de reintento hace que un remitente enviar exactamente el mismo mensaje más de una vez, tiene que asegurarse de que es idempotente.</span><span class="sxs-lookup"><span data-stu-id="49efa-222">For instance, if retry logic causes a sender to send exactly the same message more than once, you need to make sure that it is idempotent.</span></span>

<span data-ttu-id="49efa-223">Es posible diseño idempotente mensajes.</span><span class="sxs-lookup"><span data-stu-id="49efa-223">It is possible to design idempotent messages.</span></span> <span data-ttu-id="49efa-224">Por ejemplo, puede crear un evento que indica que "establecer el precio del producto \$25" en lugar de "agregar \$5 para el precio del producto."</span><span class="sxs-lookup"><span data-stu-id="49efa-224">For example, you can create an event that says "set the product price to \$25" instead of "add \$5 to the product price."</span></span> <span data-ttu-id="49efa-225">Sin ningún riesgo pudo procesar el primer mensaje de cualquier número de veces y el resultado será el mismo.</span><span class="sxs-lookup"><span data-stu-id="49efa-225">You could safely process the first message any number of times and the result will be the same.</span></span> <span data-ttu-id="49efa-226">Esto no es cierto para el segundo mensaje.</span><span class="sxs-lookup"><span data-stu-id="49efa-226">That is not true for the second message.</span></span> <span data-ttu-id="49efa-227">Pero incluso en el primer caso, no puede procesar el primer evento, porque el sistema también han podido enviar un evento de cambio de precio más recientes y se puede sobrescribir el precio de nuevo.</span><span class="sxs-lookup"><span data-stu-id="49efa-227">But even in the first case, you might not want to process the first event, because the system could also have sent a newer price-change event and you would be overwriting the new price.</span></span>

<span data-ttu-id="49efa-228">Otro ejemplo podría ser un evento completado por el orden que se ha propagado a varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="49efa-228">Another example might be an order-completed event being propagated to multiple subscribers.</span></span> <span data-ttu-id="49efa-229">Es importante que orden se actualiza la información en otros sistemas de una sola vez, incluso si hay eventos de mensaje duplicado para el mismo evento completado por orden.</span><span class="sxs-lookup"><span data-stu-id="49efa-229">It is important that order information be updated in other systems just once, even if there are duplicated message events for the same order-completed event.</span></span>

<span data-ttu-id="49efa-230">Es conveniente tener algún tipo de identidad por evento para que pueda crear lógica que exige que cada evento se procesa solo una vez por cada receptor.</span><span class="sxs-lookup"><span data-stu-id="49efa-230">It is convenient to have some kind of identity per event so that you can create logic that enforces that each event is processed only once per receiver.</span></span>

<span data-ttu-id="49efa-231">Algún procesamiento de mensajes es idempotente en Sí.</span><span class="sxs-lookup"><span data-stu-id="49efa-231">Some message processing is inherently idempotent.</span></span> <span data-ttu-id="49efa-232">Por ejemplo, si un sistema genera imágenes en miniatura, podría ser importante no cuántas veces se procesa el mensaje sobre la miniatura generada; el resultado es que se generan las miniaturas y son iguales cada vez.</span><span class="sxs-lookup"><span data-stu-id="49efa-232">For example, if a system generates image thumbnails, it might not matter how many times the message about the generated thumbnail is processed; the outcome is that the thumbnails are generated and they are the same every time.</span></span> <span data-ttu-id="49efa-233">Por otro lado, las operaciones como llamar a una puerta de enlace de pago que se le cobrará una tarjeta de crédito no pueden ser idempotente en absoluto.</span><span class="sxs-lookup"><span data-stu-id="49efa-233">On the other hand, operations such as calling a payment gateway to charge a credit card may not be idempotent at all.</span></span> <span data-ttu-id="49efa-234">En estos casos, debe asegurarse de que procesar un mensaje varias veces tiene el efecto que se espera.</span><span class="sxs-lookup"><span data-stu-id="49efa-234">In these cases, you need to ensure that processing a message multiple times has the effect that you expect.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="49efa-235">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="49efa-235">Additional resources</span></span>

-   <span data-ttu-id="49efa-236">**Respetando mensaje idempotencia** (subtítulo en esta página) [ *https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span><span class="sxs-lookup"><span data-stu-id="49efa-236">**Honoring message idempotency** (subhead on this page) [*https://msdn.microsoft.com/en-us/library/jj591565.aspx*](https://msdn.microsoft.com/en-us/library/jj591565.aspx)</span></span>

## <a name="deduplicating-integration-event-messages"></a><span data-ttu-id="49efa-237">Desduplicar los mensajes de eventos de integración</span><span class="sxs-lookup"><span data-stu-id="49efa-237">Deduplicating integration event messages</span></span>

<span data-ttu-id="49efa-238">Puede asegurarse de que los eventos de mensajes se envían y se procesase sólo una vez por cada suscriptor en niveles diferentes.</span><span class="sxs-lookup"><span data-stu-id="49efa-238">You can make sure that message events are sent and processed just once per subscriber at different levels.</span></span> <span data-ttu-id="49efa-239">Una manera es utilizar una característica de desduplicación que ofrece la infraestructura de mensajería que usa.</span><span class="sxs-lookup"><span data-stu-id="49efa-239">One way is to use a deduplication feature offered by the messaging infrastructure you are using.</span></span> <span data-ttu-id="49efa-240">Otro consiste en implementar lógica personalizada en su microservicio de destino.</span><span class="sxs-lookup"><span data-stu-id="49efa-240">Another is to implement custom logic in your destination microservice.</span></span> <span data-ttu-id="49efa-241">Lo mejor es tener validaciones en el nivel de transporte y el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="49efa-241">Having validations at both the transport level and the application level is your best bet.</span></span>

### <a name="deduplicating-message-events-at-the-eventhandler-level"></a><span data-ttu-id="49efa-242">Desduplicar eventos de mensaje en el nivel de controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="49efa-242">Deduplicating message events at the EventHandler level</span></span>

<span data-ttu-id="49efa-243">Una manera de asegurarse de que un evento se procesa solo una vez por cualquier receptor es implementando cierta lógica al procesar los eventos de mensaje en controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="49efa-243">One way to make sure that an event is processed just once by any receiver is by implementing certain logic when processing the message events in event handlers.</span></span> <span data-ttu-id="49efa-244">Por ejemplo, que es el enfoque usado en la aplicación eShopOnContainers, como puede ver en la [código fuente](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) de la clase OrdersController cuando recibe un comando CreateOrderCommand.</span><span class="sxs-lookup"><span data-stu-id="49efa-244">For example, that is the approach used in the eShopOnContainers application, as you can see in the [source code](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Controllers/OrdersController.cs) of the OrdersController class when it receives a CreateOrderCommand command.</span></span> <span data-ttu-id="49efa-245">(En este caso se utiliza un comando de solicitud HTTP, no un comando basada en mensajes, pero la lógica que necesita para realizar un comando basada en mensaje idempotente es similar).</span><span class="sxs-lookup"><span data-stu-id="49efa-245">(In this case we use an HTTP request command, not a message-based command, but the logic you need to make a message-based command idempotent is similar.)</span></span>

### <a name="deduplicating-messages-when-using-rabbitmq"></a><span data-ttu-id="49efa-246">Desduplicar mensajes cuando se usa RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="49efa-246">Deduplicating messages when using RabbitMQ</span></span>

<span data-ttu-id="49efa-247">Cuando se producen errores de red intermitentes, se pueden duplicar los mensajes y el receptor del mensaje debe estar listo para controlar estos mensajes duplicados.</span><span class="sxs-lookup"><span data-stu-id="49efa-247">When intermittent network failures happen, messages can be duplicated, and the message receiver must be ready to handle these duplicated messages.</span></span> <span data-ttu-id="49efa-248">Si es posible, receptores deben controlar los mensajes de una manera idempotente, lo que es mejor que tratándolos explícitamente con la desduplicación.</span><span class="sxs-lookup"><span data-stu-id="49efa-248">If possible, receivers should handle messages in an idempotent way, which is better than explicitly handling them with deduplication.</span></span>

<span data-ttu-id="49efa-249">Según la [RabbitMQ documentación](https://www.rabbitmq.com/reliability.html#consumer), "si un mensaje se entrega a un consumidor y, a continuación, poner en cola (porque no se ha confirmado antes de quita la conexión del consumidor, por ejemplo), a continuación, RabbitMQ establecerá la marca entregados de nuevo en que se entrega de nuevo (si en el mismo consumidor o uno diferente).</span><span class="sxs-lookup"><span data-stu-id="49efa-249">According to the [RabbitMQ documentation](https://www.rabbitmq.com/reliability.html#consumer), “If a message is delivered to a consumer and then requeued (because it was not acknowledged before the consumer connection dropped, for example) then RabbitMQ will set the redelivered flag on it when it is delivered again (whether to the same consumer or a different one).</span></span>

<span data-ttu-id="49efa-250">Si se establece la marca "entregados de nuevo", el receptor debe tener en cuenta, ya que es posible ya que se ha procesado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49efa-250">If the “redelivered” flag is set, the receiver must take that into account, because the message might already have been processed.</span></span> <span data-ttu-id="49efa-251">Pero que no se garantiza; el mensaje nunca haya alcanzado el receptor después deja al agente de mensajes, quizás debido a problemas de red.</span><span class="sxs-lookup"><span data-stu-id="49efa-251">But that is not guaranteed; the message might never have reached the receiver after it left the message broker, perhaps because of network issues.</span></span> <span data-ttu-id="49efa-252">Por otro lado, si no se estableció el marcador "entregados de nuevo", se garantiza que el mensaje no se ha enviado más de una vez.</span><span class="sxs-lookup"><span data-stu-id="49efa-252">On the other hand, if the “redelivered” flag is not set, it is guaranteed that the message has not been sent more than once.</span></span> <span data-ttu-id="49efa-253">Por lo tanto, el receptor debe desduplicar mensajes o procesan los mensajes de una manera idempotente únicamente si se establece la marca "entregados de nuevo" en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="49efa-253">Therefore, the receiver needs to deduplicate messages or process messages in an idempotent way only if the “redelivered” flag is set in the message.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="49efa-254">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="49efa-254">Additional resources</span></span>

-   <span data-ttu-id="49efa-255">**Evento controlado por mensajería**
    [*http://soapatterns.org/design\_patrones/evento\_controlada por\_de mensajería*](http://soapatterns.org/design_patterns/event_driven_messaging)</span><span class="sxs-lookup"><span data-stu-id="49efa-255">**Event Driven Messaging**
[*http://soapatterns.org/design\_patterns/event\_driven\_messaging*](http://soapatterns.org/design_patterns/event_driven_messaging)</span></span>

-   <span data-ttu-id="49efa-256">**Jimmy Bogard. Refactorización hacia resistencia: Evaluación de acoplamiento**
    [*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span><span class="sxs-lookup"><span data-stu-id="49efa-256">**Jimmy Bogard. Refactoring Towards Resilience: Evaluating Coupling**
[*https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/*](https://jimmybogard.com/refactoring-towards-resilience-evaluating-coupling/)</span></span>

-   <span data-ttu-id="49efa-257">**Canal de la publicación y suscripción**
    [*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span><span class="sxs-lookup"><span data-stu-id="49efa-257">**Publish-Subscribe channel**
[*http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html*](http://www.enterpriseintegrationpatterns.com/patterns/messaging/PublishSubscribeChannel.html)</span></span>

-   <span data-ttu-id="49efa-258">**Comunicación entre limitado contextos**
    [*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span><span class="sxs-lookup"><span data-stu-id="49efa-258">**Communicating Between Bounded Contexts**
[*https://msdn.microsoft.com/en-us/library/jj591572.aspx*](https://msdn.microsoft.com/en-us/library/jj591572.aspx)</span></span>

-   <span data-ttu-id="49efa-259">**Coherencia definitiva**
    [*https://en.wikipedia.org/wiki/Eventual\_coherencia*](https://en.wikipedia.org/wiki/Eventual_consistency)</span><span class="sxs-lookup"><span data-stu-id="49efa-259">**Eventual Consistency**
[*https://en.wikipedia.org/wiki/Eventual\_consistency*](https://en.wikipedia.org/wiki/Eventual_consistency)</span></span>

-   <span data-ttu-id="49efa-260">**Philip Brown. Estrategias para integrar limitado contextos**
    [*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span><span class="sxs-lookup"><span data-stu-id="49efa-260">**Philip Brown. Strategies for Integrating Bounded Contexts**
[*http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/*](http://culttt.com/2014/11/26/strategies-integrating-bounded-contexts/)</span></span>

-   <span data-ttu-id="49efa-261">**Chris Richardson. Desarrollar Microservicios transaccional con agregados, orígenes de eventos y CQRS - parte 2**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span><span class="sxs-lookup"><span data-stu-id="49efa-261">**Chris Richardson. Developing Transactional Microservices Using Aggregates, Event Sourcing and CQRS - Part 2**
[*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-2-richardson)</span></span>

-   <span data-ttu-id="49efa-262">**Chris Richardson. Modelo de origen de evento**
    [*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span><span class="sxs-lookup"><span data-stu-id="49efa-262">**Chris Richardson. Event Sourcing pattern**
[*http://microservices.io/patterns/data/event-sourcing.html*](http://microservices.io/patterns/data/event-sourcing.html)</span></span>

-   <span data-ttu-id="49efa-263">**Introducción a eventos de origen**
    [*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span><span class="sxs-lookup"><span data-stu-id="49efa-263">**Introducing Event Sourcing**
[*https://msdn.microsoft.com/en-us/library/jj591559.aspx*](https://msdn.microsoft.com/en-us/library/jj591559.aspx)</span></span>

-   <span data-ttu-id="49efa-264">**Base de datos de almacén de eventos**.</span><span class="sxs-lookup"><span data-stu-id="49efa-264">**Event Store database**.</span></span> <span data-ttu-id="49efa-265">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="49efa-265">Official site.</span></span>
    [<span data-ttu-id="49efa-266">*https://geteventstore.com/*</span><span class="sxs-lookup"><span data-stu-id="49efa-266">*https://geteventstore.com/*</span></span>](https://geteventstore.com/)

-   <span data-ttu-id="49efa-267">**Patrick Nommensen. Orientadas a eventos administración de datos para Microservicios**
    *<https://dzone.com/articles/event-driven-data-management-for-microservices-1>*</span><span class="sxs-lookup"><span data-stu-id="49efa-267">**Patrick Nommensen. Event-Driven Data Management for Microservices**
*<https://dzone.com/articles/event-driven-data-management-for-microservices-1> *</span></span>

-   <span data-ttu-id="49efa-268">**El teorema CAP**
    [*https://en.wikipedia.org/wiki/CAP\_teorema*](https://en.wikipedia.org/wiki/CAP_theorem)</span><span class="sxs-lookup"><span data-stu-id="49efa-268">**The CAP Theorem**
[*https://en.wikipedia.org/wiki/CAP\_theorem*](https://en.wikipedia.org/wiki/CAP_theorem)</span></span>

-   <span data-ttu-id="49efa-269">**¿Qué es teorema de extremo? ** 
     [ *https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span><span class="sxs-lookup"><span data-stu-id="49efa-269">**What is CAP Theorem?**
[*https://www.quora.com/What-Is-CAP-Theorem-1*](https://www.quora.com/What-Is-CAP-Theorem-1)</span></span>

-   <span data-ttu-id="49efa-270">**Manual de coherencia de datos**
    [*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span><span class="sxs-lookup"><span data-stu-id="49efa-270">**Data Consistency Primer**
[*https://msdn.microsoft.com/en-us/library/dn589800.aspx*](https://msdn.microsoft.com/en-us/library/dn589800.aspx)</span></span>

-   <span data-ttu-id="49efa-271">**Rick Saling. El teorema CAP: Razón "Todo lo que se diferencian" con la nube e Internet**
    [*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span><span class="sxs-lookup"><span data-stu-id="49efa-271">**Rick Saling. The CAP Theorem: Why “Everything is Different” with the Cloud and Internet**
[*https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/*](https://blogs.msdn.microsoft.com/rickatmicrosoft/2013/01/03/the-cap-theorem-why-everything-is-different-with-the-cloud-and-internet/)</span></span>

-   <span data-ttu-id="49efa-272">**Eric Brewer. CAP de doce años más tarde: cómo han cambiado las "reglas"**
    [*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span><span class="sxs-lookup"><span data-stu-id="49efa-272">**Eric Brewer. CAP Twelve Years Later: How the "Rules" Have Changed**
[*https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed*](https://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)</span></span>

-   <span data-ttu-id="49efa-273">**Participar en transacciones externas (DTC)** (MSMQ) [ *https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span><span class="sxs-lookup"><span data-stu-id="49efa-273">**Participating in External (DTC) Transactions** (MSMQ) [*https://msdn.microsoft.com/en-us/library/ms978430.aspx\#bdadotnetasync2\_topic3c*](https://msdn.microsoft.com/en-us/library/ms978430.aspx%23bdadotnetasync2_topic3c)</span></span>

-   <span data-ttu-id="49efa-274">**Bus de servicio de Azure. Mensajería asíncrona: Detección de duplicados**
    [*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span><span class="sxs-lookup"><span data-stu-id="49efa-274">**Azure Service Bus. Brokered Messaging: Duplicate Detection**
[*https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25*](https://code.msdn.microsoft.com/Brokered-Messaging-c0acea25)</span></span>

-   <span data-ttu-id="49efa-275">**Guía de confiabilidad** (documentación de RabbitMQ) [ *https://www.rabbitmq.com/reliability.html\#consumidor*](https://www.rabbitmq.com/reliability.html%23consumer)</span><span class="sxs-lookup"><span data-stu-id="49efa-275">**Reliability Guide** (RabbitMQ documentation) [*https://www.rabbitmq.com/reliability.html\#consumer*](https://www.rabbitmq.com/reliability.html%23consumer)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="49efa-276">[Anterior] (rabbitmq-event-bus-development-test-environment.md) [siguiente] (test-aspnet-core-services-web-apps.md)</span><span class="sxs-lookup"><span data-stu-id="49efa-276">[Previous] (rabbitmq-event-bus-development-test-environment.md) [Next] (test-aspnet-core-services-web-apps.md)</span></span>
