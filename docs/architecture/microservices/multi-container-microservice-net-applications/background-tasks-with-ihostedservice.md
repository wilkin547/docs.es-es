---
title: Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre las nuevas opciones para usar IHostedService y BackgroundService para implementar tareas en segundo plano en microservicios de .NET Core.
ms.date: 01/13/2021
ms.openlocfilehash: 26bc06c4a63cddcd32bf7da705f6258fab8eaafa
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188808"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a>Implementar tareas en segundo plano en microservicios con IHostedService y la clase BackgroundService

Las tareas en segundo plano y los trabajos programados son elementos que podría necesitar para cualquier aplicación, tanto si esta sigue el patrón de arquitectura de microservicios como si no. La diferencia al usar una arquitectura de microservicios es que se puede implementar la tarea en segundo plano en un proceso o contenedor independiente para el hospedaje, de modo que se pueda modificar su escala en función de las necesidades.

Desde un punto de vista genérico, en .NET este tipo de tareas se llaman *Servicios hospedados*, puesto que son servicios o lógica que se hospedan en el host, la aplicación o el microservicio. Observe que, en este caso, el servicio hospedado simplemente significa una clase con la lógica de la tarea de segundo plano.

Desde la versión 2.0 de .NET Core, el marco proporciona una nueva interfaz denominada <xref:Microsoft.Extensions.Hosting.IHostedService> que le ayuda a implementar fácilmente servicios hospedados. La idea básica es que pueda registrar varias tareas en segundo plano (servicios hospedados), que se ejecutan en segundo plano mientras se ejecuta el host o host web, tal como se muestra en la imagen 6-26.

![Diagrama que compara IWebHost de ASP.NET Core e IHost de .NET Core.](./media/background-tasks-with-ihostedservice/ihosted-service-webhost-vs-host.png)

**Figura 6-26**. Uso de IHostedService en un WebHost frente a un Host

ASP.NET Core 1.x y 2.x admiten `IWebHost` para los procesos en segundo plano en aplicaciones web. .NET Core 2.1 y las versiones posteriores admiten `IHost` para los procesos en segundo plano con aplicaciones de consola planas. Observe la diferencia entre `WebHost` y `Host`.

`WebHost` (clase base que implementa `IWebHost`) en ASP.NET Core 2.0 es el artefacto de infraestructura que se utiliza para proporcionar características de servidor HTTP al proceso, por ejemplo, si se va a implementar una aplicación web MVC o un servicio de API web. Proporciona todas las ventajas de la nueva infraestructura de ASP.NET Core, lo que le permite usar la inserción de dependencias e insertar middleware en la canalización de solicitudes, así como actividades similares. `WebHost` usa estos `IHostedServices` para las tareas en segundo plano.

Un `Host` (clase base que implementa `IHost`) se presentó en .NET Core 2.1. Básicamente, `Host` permite disponer de una infraestructura similar a la que se tiene con `WebHost` (inserción de dependencias, servicios hospedados, etc.), pero en este caso tan solo quiere tener un proceso sencillo y más ligero como host, sin ninguna relación con las características de servidor HTTP, MVC o API Web.

Por lo tanto, puede elegir y crear un proceso de host especializado con `IHost` para controlar los servicios hospedados y nada más, como por ejemplo un microservicio hecho solo para hospedar `IHostedServices`, o bien ampliar un elemento `WebHost` de ASP.NET Core existente, como una aplicación MVC o API web de ASP.NET Core.

Cada enfoque tiene ventajas e inconvenientes dependiendo de sus necesidades empresariales y de escalabilidad. La conclusión es básicamente que, si las tareas en segundo plano no tienen nada que ver con HTTP (`IWebHost`), debe usar `IHost`.

## <a name="registering-hosted-services-in-your-webhost-or-host"></a>Registro de servicios hospedados en Host o WebHost

Vamos a profundizar más en la interfaz `IHostedService` puesto que su uso es muy similar en un `WebHost` o en un `Host`.

SignalR es un ejemplo de un artefacto con servicios hospedados, pero también puede utilizarlo para cosas mucho más sencillas como las siguientes:

- Una tarea en segundo plano que sondea una base de datos en busca de cambios.
- Una tarea programada que actualiza una caché periódicamente.
- Una implementación de QueueBackgroundWorkItem que permite que una tarea se ejecute en un subproceso en segundo plano.
- Procesar los mensajes de una cola de mensajes en el segundo plano de una aplicación web mientras se comparten servicios comunes como `ILogger`.
- Una tarea en segundo plano iniciada con `Task.Run()`.

Básicamente, puede descargar cualquiera de esas acciones a una tarea en segundo plano que implementa `IHostedService`.

La forma de agregar uno o varios elementos `IHostedServices` en `WebHost` o `Host` es registrarlos a través del método de extensión <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> en un elemento `WebHost` de ASP.NET Core (o en un elemento `Host` en .NET Core 2.1 y versiones posteriores). Básicamente, tiene que registrar los servicios hospedados dentro del conocido método `ConfigureServices()` de la clase `Startup`, como se muestra en el código siguiente de un WebHost de ASP.NET típico.

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

En el código, el servicio hospedado `GracePeriodManagerService` es código real del microservicio de negocios de pedido en eShopOnContainers, mientras que los otros dos son solo dos ejemplos adicionales.

La ejecución de la tarea en segundo plano `IHostedService` se coordina con la duración de la aplicación (host o microservicio para este propósito). Las tareas se registran cuando se inicia la aplicación y, cuando se esté cerrando la aplicación, tendrá la oportunidad de limpiar o realizar alguna acción correcta.

Sin usar `IHostedService`, siempre se puede iniciar un subproceso en segundo plano para ejecutar cualquier tarea. La diferencia está precisamente en el momento de cierre de la aplicación, cuando ese subproceso simplemente terminaría sin tener ocasión de ejecutar las acciones de limpieza correcta.

## <a name="the-ihostedservice-interface"></a>Interfaz de IHostedService

Al registrar un servicio `IHostedService`, .NET llamará a los métodos `StartAsync()` y `StopAsync()` de su tipo `IHostedService` durante el inicio y la detención de la aplicación, respectivamente. Para obtener más información, vea [Interfaz IHostedService](/aspnet/core/fundamentals/host/hosted-services?tabs=visual-studio&view=aspnetcore-3.1#ihostedservice-interface).

Como puede imaginarse, es posible crear varias implementaciones de IHostedService y registrarlas en el método `ConfigureService()` en el contenedor de DI, tal y como se ha mostrado anteriormente. Todos los servicios hospedados se iniciarán y detendrán junto con la aplicación o microservicio.

Los desarrolladores son responsables de controlar la acción de detención o los servicios cuando el host activa el método `StopAsync()`.

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a>Implementación de IHostedService con una clase de servicio hospedado personalizado que se deriva de la clase base BackgroundService

Puede seguir adelante y crear una clase de servicio hospedado personalizado desde cero e implementar `IHostedService`, tal y como se debe hacer cuando se usa .NET Core 2.0 y versiones posteriores.

Pero como la mayoría de las tareas en segundo plano tienen necesidades similares en relación con la administración de tokens de cancelación y otras operaciones habituales, hay una clase base abstracta práctica denominada `BackgroundService` de la que puede derivar (disponible desde .NET Core 2.1).

Esta clase proporciona el trabajo principal necesario para configurar la tarea en segundo plano.

El código siguiente es la clase base abstracta BackgroundService tal y como se implementa en .NET.

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

Al derivar de la clase base abstracta anterior, y gracias a la implementación heredada, solo tiene que implementar el método `ExecuteAsync()` en su clase de servicio hospedado personalizado propio, como en el siguiente ejemplo simplificado de código de eShopOnContainers, en el que se sondea una base de datos y se publican eventos de integración en el bus de eventos cuando es necesario.

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
        // Constructor's parameters validations...
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

En este caso concreto de eShopOnContainers, se ejecuta un método de aplicación que consulta una tabla de base de datos en la que busca pedidos con un estado específico y al aplicar los cambios, está publicando eventos de integración a través del bus de eventos (de forma subyacente puede estar utilizando RabbitMQ o Azure Service Bus).

Por supuesto, en su lugar puede ejecutar cualquier otra tarea en segundo plano empresarial.

De forma predeterminada, el token de cancelación se establece con un tiempo de espera de 5 segundos, aunque se puede cambiar ese valor al compilar su `WebHost` mediante la extensión `UseShutdownTimeout` de `IWebHostBuilder`. Esto significa que se espera que nuestro servicio se cancele en 5 segundos o, en caso contrario, se terminará de manera repentina.

El código siguiente cambiaría ese tiempo a 10 segundos.

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a>Diagrama de clases de resumen

En la siguiente ilustración se muestra un resumen visual de las clases y las interfaces implicadas al implementar IHostedServices.

![Diagrama que muestra que IWebHost y IHost pueden hospedar muchos servicios.](./media/background-tasks-with-ihostedservice/class-diagram-custom-ihostedservice.png)

**Figura 6-27**. Diagrama de clases que muestra las distintas clases e interfaces relacionadas con IHostedService

Diagrama de clases: IWebHost y IHost pueden hospedar muchos servicios, que heredan de BackgroundService, que implementa IHostedService.

### <a name="deployment-considerations-and-takeaways"></a>Impresiones y consideraciones sobre implementación

Es importante tener en cuenta que la forma de implementar su `WebHost` de ASP.NET Core o `Host` de .NET puede afectar a la solución final. Por ejemplo, si implementa su `WebHost` en IIS o en un servicio de Azure App Service normal, el host se puede cerrar debido a reciclajes del grupo de aplicaciones. Pero si va a implementar el host como contenedor en un orquestador como Kubernetes, puede controlar el número garantizado de instancias activas del host. Además, podría considerar otros métodos en la nube pensados especialmente para estos escenarios, como Azure Functions. Por último, si necesita que el servicio se ejecute todo el tiempo y se implemente en Windows Server, podría usar un servicio de Windows.

Pero incluso para un elemento `WebHost` implementado en un grupo de aplicaciones, hay escenarios, como el relleno o el vaciado de la memoria caché de la aplicación, en los que sería también aplicable.

La interfaz `IHostedService` proporciona una manera cómoda de iniciar tareas en segundo plano en una aplicación web de ASP.NET (en .NET Core 2.0 y versiones posteriores) o en cualquier proceso o host (a partir de .NET Core 2.1 con `IHost`). La principal ventaja es la oportunidad de obtener con la cancelación correcta un código de limpieza de sus tareas en segundo plano cuando se está cerrando el propio host.

## <a name="additional-resources"></a>Recursos adicionales

- **Creación de una tarea programada en ASP.NET Core/Standard 2.0** \
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- **Implementación de IHostedService en ASP.NET Core 2.0** \
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- **Ejemplo de GenericHost mediante ASP.NET Core 2.1** \
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

> [!div class="step-by-step"]
> [Anterior](test-aspnet-core-services-web-apps.md)
> [Siguiente](implement-api-gateways-with-ocelot.md)
