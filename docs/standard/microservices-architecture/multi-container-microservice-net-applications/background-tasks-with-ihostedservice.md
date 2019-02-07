---
title: Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre las nuevas opciones para usar IHostedService y BackgroundService para implementar tareas en segundo plano en microservicios de .NET Core.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: 721a3129a00867279846bc44155b307f5e97ae39
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479792"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="56ec0-103">Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService</span><span class="sxs-lookup"><span data-stu-id="56ec0-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="56ec0-104">Las tareas en segundo plano y los trabajos programados son algo que quizá tenga que implementar a la larga en una aplicación basada en microservicio o en cualquier tipo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="56ec0-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="56ec0-105">La diferencia al utilizar una arquitectura de microservicios es que permite implementar un proceso/contenedor único de microservicio para hospedar estas tareas en segundo plano, por lo que se puede escalar o reducir verticalmente según sea necesario, e incluso es posible asegurarse de que se ejecuta una sola instancia de ese proceso o contenedor de microservicio.</span><span class="sxs-lookup"><span data-stu-id="56ec0-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="56ec0-106">Desde un punto de vista genérico, en .NET Core este tipo de tareas se llaman *Servicios hospedados*, puesto que son servicios o lógica que se hospedan en el host, la aplicación o el microservicio.</span><span class="sxs-lookup"><span data-stu-id="56ec0-106">From a generic point of view, in .NET Core we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="56ec0-107">Observe que, en este caso, el servicio hospedado simplemente significa una clase con la lógica de la tarea de segundo plano.</span><span class="sxs-lookup"><span data-stu-id="56ec0-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="56ec0-108">Desde la versión 2.0 de .NET Core, el marco proporciona una nueva interfaz denominada <xref:Microsoft.Extensions.Hosting.IHostedService> que le ayuda a implementar fácilmente servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="56ec0-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="56ec0-109">La idea básica es que pueda registrar varias tareas en segundo plano (servicios hospedados), que se ejecutan en segundo plano mientras se ejecuta el host o host web, como se muestra en la imagen 6-26.</span><span class="sxs-lookup"><span data-stu-id="56ec0-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![ASP.NET Core 1.x y 2.x son compatibles con IWebHost para procesos en segundo plano en las aplicaciones web, .NET Core 2.1 es compatible con IHost para procesos en segundo plano con aplicaciones de consola normales.](./media/image26.png)

<span data-ttu-id="56ec0-111">**Figura 6-26**.</span><span class="sxs-lookup"><span data-stu-id="56ec0-111">**Figure 6-26**.</span></span> <span data-ttu-id="56ec0-112">Uso de IHostedService en un WebHost frente a un Host</span><span class="sxs-lookup"><span data-stu-id="56ec0-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="56ec0-113">Observe la diferencia entre `WebHost` y `Host`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-113">Note the difference made between `WebHost` and `Host`.</span></span> 

<span data-ttu-id="56ec0-114">`WebHost` (clase base que implementa `IWebHost`) en ASP.NET Core 2.0 es el artefacto de infraestructura que se utiliza para proporcionar características de servidor HTTP al proceso, por ejemplo, si se va a implementar una aplicación web MVC o un servicio de API Web.</span><span class="sxs-lookup"><span data-stu-id="56ec0-114">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="56ec0-115">Proporciona todas las ventajas de la nueva infraestructura de ASP.NET Core, lo que le permite usar la inserción de dependencias, insertar middleware en la canalización de solicitudes, etc., además de utilizar de manera precisa `IHostedServices` para tareas en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="56ec0-115">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="56ec0-116">Un `Host` (clase base que implementa `IHost`) se presentó en .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="56ec0-116">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="56ec0-117">Básicamente, `Host` permite disponer de una infraestructura similar a la que se tiene con `WebHost` (inserción de dependencias, servicios hospedados, etc.), pero en este caso tan solo quiere tener un proceso sencillo y más ligero como host, sin ninguna relación con las características de servidor HTTP, MVC o API Web.</span><span class="sxs-lookup"><span data-stu-id="56ec0-117">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="56ec0-118">Por lo tanto, puede elegir y crear un proceso de host especializado con IHost para controlar los servicios hospedados y nada más, como por ejemplo un microservicio hecho solo para hospedar `IHostedServices`, o bien puede ampliar un `WebHost` de ASP.NET Core existente, como por ejemplo una aplicación MVC o API Web de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="56ec0-118">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span> 

<span data-ttu-id="56ec0-119">Cada enfoque tiene ventajas e inconvenientes dependiendo de sus necesidades empresariales y de escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="56ec0-119">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="56ec0-120">La conclusión es básicamente que, si las tareas en segundo plano no tienen nada que ver con HTTP (IWebHost), debe usar IHost.</span><span class="sxs-lookup"><span data-stu-id="56ec0-120">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use IHost.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="56ec0-121">Registro de servicios hospedados en Host o WebHost</span><span class="sxs-lookup"><span data-stu-id="56ec0-121">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="56ec0-122">Vamos a profundizar más en la interfaz `IHostedService` puesto que su uso es muy similar en un `WebHost` o en un `Host`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-122">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span> 

<span data-ttu-id="56ec0-123">SignalR es un ejemplo de un artefacto con servicios hospedados, pero también puede utilizarlo para cosas mucho más sencillas como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="56ec0-123">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

-   <span data-ttu-id="56ec0-124">Una tarea en segundo plano que sondea una base de datos en busca de cambios.</span><span class="sxs-lookup"><span data-stu-id="56ec0-124">A background task polling a database looking for changes.</span></span>
-   <span data-ttu-id="56ec0-125">Una tarea programada que actualiza una caché periódicamente.</span><span class="sxs-lookup"><span data-stu-id="56ec0-125">A scheduled task updating some cache periodically.</span></span>
-   <span data-ttu-id="56ec0-126">Una implementación de QueueBackgroundWorkItem que permite que una tarea se ejecute en un subproceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="56ec0-126">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
-   <span data-ttu-id="56ec0-127">Procesar los mensajes de una cola de mensajes en el segundo plano de una aplicación web mientras se comparten servicios comunes como `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-127">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
-   <span data-ttu-id="56ec0-128">Una tarea en segundo plano iniciada con `Task.Run()`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-128">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="56ec0-129">Básicamente, puede descargar cualquiera de esas acciones a una tarea en segundo plano basada en IHostedService.</span><span class="sxs-lookup"><span data-stu-id="56ec0-129">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="56ec0-130">La manera de agregar uno o varios `IHostedServices` en su `WebHost` o `Host` es registrándolos mediante DI estándar (inserción de dependencias) en `WebHost` de ASP.NET Core (o en `Host` en .NET Core 2.1 y superior).</span><span class="sxs-lookup"><span data-stu-id="56ec0-130">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="56ec0-131">Básicamente, tiene que registrar los servicios hospedados dentro del conocido método `ConfigureServices()` de la clase `Startup`, como se muestra en el código siguiente de un WebHost de ASP.NET típico.</span><span class="sxs-lookup"><span data-stu-id="56ec0-131">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span> 

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{            
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="56ec0-132">En el código, el servicio hospedado `GracePeriodManagerService` es código real del microservicio de negocios de pedido en eShopOnContainers, mientras que los otros dos son solo dos ejemplos adicionales.</span><span class="sxs-lookup"><span data-stu-id="56ec0-132">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="56ec0-133">La ejecución de la tarea en segundo plano `IHostedService` se coordina con la duración de la aplicación (host o microservicio para este propósito).</span><span class="sxs-lookup"><span data-stu-id="56ec0-133">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="56ec0-134">Las tareas se registran cuando se inicia la aplicación y, cuando se esté cerrando la aplicación, tendrá la oportunidad de limpiar o realizar alguna acción correcta.</span><span class="sxs-lookup"><span data-stu-id="56ec0-134">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="56ec0-135">Sin usar `IHostedService`, siempre se puede iniciar un subproceso en segundo plano para ejecutar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="56ec0-135">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="56ec0-136">La diferencia está precisamente en el tiempo de cierre de la aplicación, cuando ese subproceso simplemente terminaría sin tener la oportunidad de ejecutar las acciones de limpieza correcta.</span><span class="sxs-lookup"><span data-stu-id="56ec0-136">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="56ec0-137">Interfaz de IHostedService</span><span class="sxs-lookup"><span data-stu-id="56ec0-137">The IHostedService interface</span></span>

<span data-ttu-id="56ec0-138">Al registrar un `IHostedService`, .NET Core llamará a los métodos `StartAsync()` y `StopAsync()` de su tipo `IHostedService` durante el inicio y la detención de la aplicación respectivamente.</span><span class="sxs-lookup"><span data-stu-id="56ec0-138">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="56ec0-139">En concreto, se llama a start después de que el servidor se inicie y se desencadene `IApplicationLifetime.ApplicationStarted`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-139">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="56ec0-140">`IHostedService`, tal como se define en .NET Core, se parece a lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="56ec0-140">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

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
<span data-ttu-id="56ec0-141">Como puede imaginarse, es posible crear varias implementaciones de IHostedService y registrarlas en el método `ConfigureService()` en el contenedor de DI, tal y como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="56ec0-141">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="56ec0-142">Todos los servicios hospedados se iniciarán y detendrán junto con la aplicación o microservicio.</span><span class="sxs-lookup"><span data-stu-id="56ec0-142">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="56ec0-143">Los desarrolladores son responsables de controlar la acción de detención o los servicios cuando el host activa el método `StopAsync()`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-143">As a developer, you are responsible for handling the stopping action or your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="56ec0-144">Implementación de IHostedService con una clase de servicio hospedado personalizado que se deriva de la clase base BackgroundService</span><span class="sxs-lookup"><span data-stu-id="56ec0-144">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="56ec0-145">Puede seguir adelante y crear una clase de servicio hospedado personalizado desde cero e implementar `IHostedService`, tal y como se debe hacer cuando se usa .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="56ec0-145">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span> 

<span data-ttu-id="56ec0-146">Pero como la mayoría de las tareas en segundo plano tienen necesidades similares en relación con la administración de tokens de cancelación y otras operaciones habituales, hay una clase base abstracta práctica denominada `BackgroundService` de la que puede derivar (disponible desde .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="56ec0-146">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="56ec0-147">Esta clase proporciona el trabajo principal necesario para configurar la tarea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="56ec0-147">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="56ec0-148">El código siguiente es la clase base abstracta de BackgroundService tal y como se implementa en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="56ec0-148">The next code is the abstract BackgroundService base class as implemented in .NET Core.</span></span>

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

<span data-ttu-id="56ec0-149">Al derivar de la clase base abstracta anterior, y gracias a la implementación heredada, solo tiene que implementar el método `ExecuteAsync()` en su clase de servicio hospedado personalizado propio, como en el siguiente ejemplo simplificado de código de eShopOnContainers, en el que se sondea una base de datos y se publican eventos de integración en el bus de eventos cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="56ec0-149">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

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
                // and publishing events into the Event Bus (RabbitMS / ServiceBus)
                CheckConfirmedGracePeriodOrders();

                await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
            }
            
            _logger.LogDebug($"GracePeriod background task is stopping.");

        }

        protected override async Task StopAsync (CancellationToken stoppingToken)
        {
               // Run your graceful clean-up actions
        }
}
```

<span data-ttu-id="56ec0-150">En este caso concreto de eShopOnContainers, se ejecuta un método de aplicación que consulta una tabla de base de datos en la que busca pedidos con un estado específico y al aplicar los cambios, está publicando eventos de integración a través del bus de eventos (de forma subyacente puede estar utilizando RabbitMQ o Azure Service Bus).</span><span class="sxs-lookup"><span data-stu-id="56ec0-150">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="56ec0-151">Por supuesto, en su lugar puede ejecutar cualquier otra tarea en segundo plano empresarial.</span><span class="sxs-lookup"><span data-stu-id="56ec0-151">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="56ec0-152">De forma predeterminada, el token de cancelación se establece con un tiempo de espera de 5 segundos, aunque se puede cambiar ese valor al compilar su `WebHost` mediante la extensión `UseShutdownTimeout` de `IWebHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="56ec0-152">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="56ec0-153">Esto significa que se espera que nuestro servicio se cancele en 5 segundos o, en caso contrario, se terminará de manera repentina.</span><span class="sxs-lookup"><span data-stu-id="56ec0-153">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="56ec0-154">El código siguiente cambiaría ese tiempo a 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="56ec0-154">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="56ec0-155">Diagrama de clases de resumen</span><span class="sxs-lookup"><span data-stu-id="56ec0-155">Summary class diagram</span></span>

<span data-ttu-id="56ec0-156">En la siguiente ilustración se muestra un resumen visual de las clases y las interfaces implicadas al implementar IHostedServices.</span><span class="sxs-lookup"><span data-stu-id="56ec0-156">The following image shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>
 
![Class diagram: IWebHost y IHost pueden hospedar muchos servicios, que heredan de BackgroundService, que implementa IHostedService.](./media/image27.png)

<span data-ttu-id="56ec0-158">**Figura 6-27**.</span><span class="sxs-lookup"><span data-stu-id="56ec0-158">**Figure 6-27**.</span></span> <span data-ttu-id="56ec0-159">Diagrama de clases que muestra las distintas clases e interfaces relacionadas con IHostedService</span><span class="sxs-lookup"><span data-stu-id="56ec0-159">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="56ec0-160">Impresiones y consideraciones sobre implementación</span><span class="sxs-lookup"><span data-stu-id="56ec0-160">Deployment considerations and takeaways</span></span>

<span data-ttu-id="56ec0-161">Es importante tener en cuenta que la forma de implementar su ASP.NET Core `WebHost` o .NET Core `Host` puede afectar a la solución final.</span><span class="sxs-lookup"><span data-stu-id="56ec0-161">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="56ec0-162">Por ejemplo, si implementa su `WebHost` en IIS o en un servicio de Azure App Service normal, el host se puede cerrar debido a reciclajes del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="56ec0-162">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="56ec0-163">Pero si va a implementar el host como un contenedor en un orquestador como Kubernetes o Service Fabric, puede controlar el número garantizado de instancias activas del host.</span><span class="sxs-lookup"><span data-stu-id="56ec0-163">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="56ec0-164">Además, podría considerar otros métodos en la nube pensados especialmente para estos escenarios, como Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="56ec0-164">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="56ec0-165">Por último, si necesita que el servicio se ejecute todo el tiempo y se implemente en Windows Server, podría usar un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="56ec0-165">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="56ec0-166">Pero incluso para un `WebHost` implementado en un grupo de aplicaciones, hay escenarios, como el relleno o el vaciado de la memoria caché de la aplicación, en los que sería también aplicable.</span><span class="sxs-lookup"><span data-stu-id="56ec0-166">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="56ec0-167">La interfaz `IHostedService` proporciona una manera cómoda de iniciar tareas en segundo plano en una aplicación web de ASP.NET (en .NET Core 2.0) o en cualquier proceso o host (a partir de .NET Core 2.1 con `IHost`).</span><span class="sxs-lookup"><span data-stu-id="56ec0-167">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="56ec0-168">La principal ventaja es la oportunidad de obtener con la cancelación correcta un código de limpieza de sus tareas en segundo plano cuando se está cerrando el propio host.</span><span class="sxs-lookup"><span data-stu-id="56ec0-168">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="56ec0-169">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="56ec0-169">Additional resources</span></span>

-   <span data-ttu-id="56ec0-170">**Building a scheduled task in ASP.NET Core/Standard 2.0** (Creación de una tarea programada en ASP.NET Core/Standard 2.0)</span><span class="sxs-lookup"><span data-stu-id="56ec0-170">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span> <br/>
    [*https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html*](https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html)

-   <span data-ttu-id="56ec0-171">**Implementing IHostedService in ASP.NET Core 2.0** (Implementación de IHostedService en ASP.NET Core 2.0)</span><span class="sxs-lookup"><span data-stu-id="56ec0-171">**Implementing IHostedService in ASP.NET Core 2.0**</span></span> <br/>
    [*https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice*](https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice)

-   <span data-ttu-id="56ec0-172">**Ejemplo de GenericHost mediante ASP.NET Core 2.1**</span><span class="sxs-lookup"><span data-stu-id="56ec0-172">**GenericHost Sample using ASP.NET Core 2.1**</span></span> <br/>
    [*https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample*](https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample)

>[!div class="step-by-step"]
><span data-ttu-id="56ec0-173">[Anterior](test-aspnet-core-services-web-apps.md)
>[Siguiente](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="56ec0-173">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>