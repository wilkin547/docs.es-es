---
title: Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre las nuevas opciones para usar IHostedService y BackgroundService para implementar tareas en segundo plano en microservicios de .NET Core.
ms.date: 01/30/2020
ms.openlocfilehash: fab67c816e90c69a4d593422b4974cb9b8819807
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77502308"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="f62ca-103">Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService</span><span class="sxs-lookup"><span data-stu-id="f62ca-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="f62ca-104">Las tareas en segundo plano y los trabajos programados son algo que quizá tenga que implementar a la larga en una aplicación basada en microservicio o en cualquier tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f62ca-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="f62ca-105">La diferencia al utilizar una arquitectura de microservicios es que permite implementar un proceso/contenedor único de microservicio para hospedar estas tareas en segundo plano, por lo que se puede escalar o reducir verticalmente según sea necesario, e incluso es posible asegurarse de que se ejecuta una sola instancia de ese proceso o contenedor de microservicio.</span><span class="sxs-lookup"><span data-stu-id="f62ca-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="f62ca-106">Desde un punto de vista genérico, en .NET Core este tipo de tareas se llaman *Servicios hospedados*, puesto que son servicios o lógica que se hospedan en el host, la aplicación o el microservicio.</span><span class="sxs-lookup"><span data-stu-id="f62ca-106">From a generic point of view, in .NET Core we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="f62ca-107">Observe que, en este caso, el servicio hospedado simplemente significa una clase con la lógica de la tarea de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f62ca-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="f62ca-108">Desde la versión 2.0 de .NET Core, el marco proporciona una nueva interfaz denominada <xref:Microsoft.Extensions.Hosting.IHostedService> que le ayuda a implementar fácilmente servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="f62ca-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="f62ca-109">La idea básica es que pueda registrar varias tareas en segundo plano (servicios hospedados), que se ejecutan en segundo plano mientras se ejecuta el host o host web, tal como se muestra en la imagen 6-26.</span><span class="sxs-lookup"><span data-stu-id="f62ca-109">The basic idea is that you can register multiple background tasks (hosted services) that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![Diagrama que compara IWebHost de ASP.NET Core e IHost de .NET Core.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

<span data-ttu-id="f62ca-111">**Figura 6-26**.</span><span class="sxs-lookup"><span data-stu-id="f62ca-111">**Figure 6-26**.</span></span> <span data-ttu-id="f62ca-112">Uso de IHostedService en un WebHost frente a un Host</span><span class="sxs-lookup"><span data-stu-id="f62ca-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="f62ca-113">ASP.NET Core 1.x y 2.x admiten `IWebHost` para los procesos en segundo plano en aplicaciones web.</span><span class="sxs-lookup"><span data-stu-id="f62ca-113">ASP.NET Core 1.x and 2.x support `IWebHost` for background processes in web apps.</span></span> <span data-ttu-id="f62ca-114">.NET Core 2.1 y las versiones posteriores admiten `IHost` para los procesos en segundo plano con aplicaciones de consola planas.</span><span class="sxs-lookup"><span data-stu-id="f62ca-114">.NET Core 2.1 and later versions support `IHost` for background processes with plain console apps.</span></span> <span data-ttu-id="f62ca-115">Observe la diferencia entre `WebHost` y `Host`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-115">Note the difference made between `WebHost` and `Host`.</span></span>

<span data-ttu-id="f62ca-116">`WebHost` (clase base que implementa `IWebHost`) en ASP.NET Core 2.0 es el artefacto de infraestructura que se utiliza para proporcionar características de servidor HTTP al proceso, por ejemplo, si se va a implementar una aplicación web MVC o un servicio de API web.</span><span class="sxs-lookup"><span data-stu-id="f62ca-116">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as when you're implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="f62ca-117">Proporciona todas las ventajas de la nueva infraestructura de ASP.NET Core, lo que le permite usar la inserción de dependencias e insertar middleware en la canalización de solicitudes, así como actividades similares.</span><span class="sxs-lookup"><span data-stu-id="f62ca-117">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, and similar.</span></span> <span data-ttu-id="f62ca-118">`WebHost` usa estos `IHostedServices` para las tareas en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f62ca-118">The `WebHost` uses these very same `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="f62ca-119">Un `Host` (clase base que implementa `IHost`) se presentó en .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="f62ca-119">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="f62ca-120">Básicamente, `Host` permite disponer de una infraestructura similar a la que se tiene con `WebHost` (inserción de dependencias, servicios hospedados, etc.), pero en este caso tan solo quiere tener un proceso sencillo y más ligero como host, sin ninguna relación con las características de servidor HTTP, MVC o API Web.</span><span class="sxs-lookup"><span data-stu-id="f62ca-120">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="f62ca-121">Por lo tanto, puede elegir y crear un proceso de host especializado con `IHost` para controlar los servicios hospedados y nada más, como por ejemplo un microservicio hecho solo para hospedar `IHostedServices`, o bien ampliar un elemento `WebHost` de ASP.NET Core existente, como una aplicación MVC o API web de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f62ca-121">Therefore, you can choose and either create a specialized host-process with `IHost` to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span>

<span data-ttu-id="f62ca-122">Cada enfoque tiene ventajas e inconvenientes dependiendo de sus necesidades empresariales y de escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="f62ca-122">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="f62ca-123">La conclusión es básicamente que, si las tareas en segundo plano no tienen nada que ver con HTTP (`IWebHost`), debe usar `IHost`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-123">The bottom line is basically that if your background tasks have nothing to do with HTTP (`IWebHost`) you should use `IHost`.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="f62ca-124">Registro de servicios hospedados en Host o WebHost</span><span class="sxs-lookup"><span data-stu-id="f62ca-124">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="f62ca-125">Vamos a profundizar más en la interfaz `IHostedService` puesto que su uso es muy similar en un `WebHost` o en un `Host`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-125">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span>

<span data-ttu-id="f62ca-126">SignalR es un ejemplo de un artefacto con servicios hospedados, pero también puede utilizarlo para cosas mucho más sencillas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f62ca-126">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

- <span data-ttu-id="f62ca-127">Una tarea en segundo plano que sondea una base de datos en busca de cambios.</span><span class="sxs-lookup"><span data-stu-id="f62ca-127">A background task polling a database looking for changes.</span></span>
- <span data-ttu-id="f62ca-128">Una tarea programada que actualiza una caché periódicamente.</span><span class="sxs-lookup"><span data-stu-id="f62ca-128">A scheduled task updating some cache periodically.</span></span>
- <span data-ttu-id="f62ca-129">Una implementación de QueueBackgroundWorkItem que permite que una tarea se ejecute en un subproceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f62ca-129">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
- <span data-ttu-id="f62ca-130">Procesar los mensajes de una cola de mensajes en el segundo plano de una aplicación web mientras se comparten servicios comunes como `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-130">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
- <span data-ttu-id="f62ca-131">Una tarea en segundo plano iniciada con `Task.Run()`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-131">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="f62ca-132">Básicamente, puede descargar cualquiera de esas acciones a una tarea en segundo plano que implementa `IHostedService`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-132">You can basically offload any of those actions to a background task that implements `IHostedService`.</span></span>

<span data-ttu-id="f62ca-133">La forma de agregar uno o varios elementos `IHostedServices` en `WebHost` o `Host` es registrarlos a través del método de extensión <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> en un elemento `WebHost` de ASP.NET Core (o en un elemento `Host` en .NET Core 2.1 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="f62ca-133">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> extension method in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="f62ca-134">Básicamente, tiene que registrar los servicios hospedados dentro del conocido método `ConfigureServices()` de la clase `Startup`, como se muestra en el código siguiente de un WebHost de ASP.NET típico.</span><span class="sxs-lookup"><span data-stu-id="f62ca-134">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddHostedService<GracePeriodManagerService>();
    services.AddHostedService<MyHostedServiceB>();
    services.AddHostedService<MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="f62ca-135">En el código, el servicio hospedado `GracePeriodManagerService` es código real del microservicio de negocios de pedido en eShopOnContainers, mientras que los otros dos son solo dos ejemplos adicionales.</span><span class="sxs-lookup"><span data-stu-id="f62ca-135">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="f62ca-136">La ejecución de la tarea en segundo plano `IHostedService` se coordina con la duración de la aplicación (host o microservicio para este propósito).</span><span class="sxs-lookup"><span data-stu-id="f62ca-136">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="f62ca-137">Las tareas se registran cuando se inicia la aplicación y, cuando se esté cerrando la aplicación, tendrá la oportunidad de limpiar o realizar alguna acción correcta.</span><span class="sxs-lookup"><span data-stu-id="f62ca-137">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="f62ca-138">Sin usar `IHostedService`, siempre se puede iniciar un subproceso en segundo plano para ejecutar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="f62ca-138">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="f62ca-139">La diferencia está precisamente en el tiempo de cierre de la aplicación, cuando ese subproceso simplemente terminaría sin tener la oportunidad de ejecutar las acciones de limpieza correcta.</span><span class="sxs-lookup"><span data-stu-id="f62ca-139">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="f62ca-140">Interfaz de IHostedService</span><span class="sxs-lookup"><span data-stu-id="f62ca-140">The IHostedService interface</span></span>

<span data-ttu-id="f62ca-141">Al registrar un `IHostedService`, .NET Core llamará a los métodos `StartAsync()` y `StopAsync()` de su tipo `IHostedService` durante el inicio y la detención de la aplicación respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f62ca-141">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="f62ca-142">En concreto, se llama a start después de que el servidor se inicie y se desencadene `IApplicationLifetime.ApplicationStarted`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-142">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="f62ca-143">`IHostedService`, tal como se define en .NET Core, se parece a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f62ca-143">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```

<span data-ttu-id="f62ca-144">Como puede imaginarse, es posible crear varias implementaciones de IHostedService y registrarlas en el método `ConfigureService()` en el contenedor de DI, tal y como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f62ca-144">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="f62ca-145">Todos los servicios hospedados se iniciarán y detendrán junto con la aplicación o microservicio.</span><span class="sxs-lookup"><span data-stu-id="f62ca-145">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="f62ca-146">Los desarrolladores son responsables de controlar la acción de detención o los servicios cuando el host activa el método `StopAsync()`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-146">As a developer, you are responsible for handling the stopping action of your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="f62ca-147">Implementación de IHostedService con una clase de servicio hospedado personalizado que se deriva de la clase base BackgroundService</span><span class="sxs-lookup"><span data-stu-id="f62ca-147">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="f62ca-148">Puede seguir adelante y crear una clase de servicio hospedado personalizado desde cero e implementar `IHostedService`, tal y como se debe hacer cuando se usa .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="f62ca-148">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span>

<span data-ttu-id="f62ca-149">Pero como la mayoría de las tareas en segundo plano tienen necesidades similares en relación con la administración de tokens de cancelación y otras operaciones habituales, hay una clase base abstracta práctica denominada `BackgroundService` de la que puede derivar (disponible desde .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="f62ca-149">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="f62ca-150">Esta clase proporciona el trabajo principal necesario para configurar la tarea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f62ca-150">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="f62ca-151">El código siguiente es la clase base abstracta de BackgroundService tal y como se implementa en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f62ca-151">The next code is the abstract BackgroundService base class as implemented in .NET Core.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="f62ca-152">Al derivar de la clase base abstracta anterior, y gracias a la implementación heredada, solo tiene que implementar el método `ExecuteAsync()` en su clase de servicio hospedado personalizado propio, como en el siguiente ejemplo simplificado de código de eShopOnContainers, en el que se sondea una base de datos y se publican eventos de integración en el bus de eventos cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="f62ca-152">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

<span data-ttu-id="f62ca-153">En este caso concreto de eShopOnContainers, se ejecuta un método de aplicación que consulta una tabla de base de datos en la que busca pedidos con un estado específico y al aplicar los cambios, está publicando eventos de integración a través del bus de eventos (de forma subyacente puede estar utilizando RabbitMQ o Azure Service Bus).</span><span class="sxs-lookup"><span data-stu-id="f62ca-153">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="f62ca-154">Por supuesto, en su lugar puede ejecutar cualquier otra tarea en segundo plano empresarial.</span><span class="sxs-lookup"><span data-stu-id="f62ca-154">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="f62ca-155">De forma predeterminada, el token de cancelación se establece con un tiempo de espera de 5 segundos, aunque se puede cambiar ese valor al compilar su `WebHost` mediante la extensión `UseShutdownTimeout` de `IWebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="f62ca-155">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="f62ca-156">Esto significa que se espera que nuestro servicio se cancele en 5 segundos o, en caso contrario, se terminará de manera repentina.</span><span class="sxs-lookup"><span data-stu-id="f62ca-156">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="f62ca-157">El código siguiente cambiaría ese tiempo a 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="f62ca-157">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="f62ca-158">Diagrama de clases de resumen</span><span class="sxs-lookup"><span data-stu-id="f62ca-158">Summary class diagram</span></span>

<span data-ttu-id="f62ca-159">En la siguiente ilustración se muestra un resumen visual de las clases y las interfaces implicadas al implementar IHostedServices.</span><span class="sxs-lookup"><span data-stu-id="f62ca-159">The following image shows a visual summary of the classes and interfaces involved when implementing IHostedServices.</span></span>

![Diagrama que muestra que IWebHost y IHost pueden hospedar muchos servicios.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

<span data-ttu-id="f62ca-161">**Figura 6-27**.</span><span class="sxs-lookup"><span data-stu-id="f62ca-161">**Figure 6-27**.</span></span> <span data-ttu-id="f62ca-162">Diagrama de clases que muestra las distintas clases e interfaces relacionadas con IHostedService</span><span class="sxs-lookup"><span data-stu-id="f62ca-162">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

<span data-ttu-id="f62ca-163">Diagrama de clases: IWebHost y IHost pueden hospedar muchos servicios, que heredan de BackgroundService, que implementa IHostedService.</span><span class="sxs-lookup"><span data-stu-id="f62ca-163">Class diagram: IWebHost and IHost can host many services, which inherit from BackgroundService, which implements IHostedService.</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="f62ca-164">Impresiones y consideraciones sobre implementación</span><span class="sxs-lookup"><span data-stu-id="f62ca-164">Deployment considerations and takeaways</span></span>

<span data-ttu-id="f62ca-165">Es importante tener en cuenta que la forma de implementar su ASP.NET Core `WebHost` o .NET Core `Host` puede afectar a la solución final.</span><span class="sxs-lookup"><span data-stu-id="f62ca-165">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="f62ca-166">Por ejemplo, si implementa su `WebHost` en IIS o en un servicio de Azure App Service normal, el host se puede cerrar debido a reciclajes del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f62ca-166">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="f62ca-167">Pero si va a implementar el host como contenedor en un orquestador como Kubernetes, puede controlar el número garantizado de instancias activas del host.</span><span class="sxs-lookup"><span data-stu-id="f62ca-167">But if you are deploying your host as a container into an orchestrator like Kubernetes, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="f62ca-168">Además, podría considerar otros métodos en la nube pensados especialmente para estos escenarios, como Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="f62ca-168">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="f62ca-169">Por último, si necesita que el servicio se ejecute todo el tiempo y se implemente en Windows Server, podría usar un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="f62ca-169">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="f62ca-170">Pero incluso para un elemento `WebHost` implementado en un grupo de aplicaciones, hay escenarios, como el relleno o el vaciado de la memoria caché de la aplicación, en los que sería también aplicable.</span><span class="sxs-lookup"><span data-stu-id="f62ca-170">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache that would be still applicable.</span></span>

<span data-ttu-id="f62ca-171">La interfaz `IHostedService` proporciona una manera cómoda de iniciar tareas en segundo plano en una aplicación web de ASP.NET (en .NET Core 2.0 y versiones posteriores) o en cualquier proceso o host (a partir de .NET Core 2.1 con `IHost`).</span><span class="sxs-lookup"><span data-stu-id="f62ca-171">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0 and later versions) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="f62ca-172">La principal ventaja es la oportunidad de obtener con la cancelación correcta un código de limpieza de sus tareas en segundo plano cuando se está cerrando el propio host.</span><span class="sxs-lookup"><span data-stu-id="f62ca-172">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f62ca-173">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f62ca-173">Additional resources</span></span>

- <span data-ttu-id="f62ca-174">**Creación de una tarea programada en ASP.NET Core/Standard 2.0** </span><span class="sxs-lookup"><span data-stu-id="f62ca-174">**Building a scheduled task in ASP.NET Core/Standard 2.0** </span></span>\
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- <span data-ttu-id="f62ca-175">**Implementación de IHostedService en ASP.NET Core 2.0** </span><span class="sxs-lookup"><span data-stu-id="f62ca-175">**Implementing IHostedService in ASP.NET Core 2.0** </span></span>\
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- <span data-ttu-id="f62ca-176">**Ejemplo de GenericHost mediante ASP.NET Core 2.1** </span><span class="sxs-lookup"><span data-stu-id="f62ca-176">**GenericHost Sample using ASP.NET Core 2.1** </span></span>\
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

>[!div class="step-by-step"]
><span data-ttu-id="f62ca-177">[Anterior](test-aspnet-core-services-web-apps.md)
>[Siguiente](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="f62ca-177">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>
