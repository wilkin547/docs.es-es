---
title: Inserción de dependencias en .NET
description: Obtenga información sobre la manera en que .NET implementa la inserción de dependencias y cómo se usa.
author: IEvangelist
ms.author: dapine
ms.date: 10/28/2020
ms.topic: overview
ms.openlocfilehash: cc030e32846690b6544b99030800b50055a3113e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "102402192"
---
# <a name="dependency-injection-in-net"></a><span data-ttu-id="dd2ba-103">Inserción de dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="dd2ba-103">Dependency injection in .NET</span></span>

<span data-ttu-id="dd2ba-104">.NET admite el patrón de diseño de software de inserción de dependencias (DI), que es una técnica para conseguir la [inversión de control (IoC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) entre clases y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-104">.NET supports the dependency injection (DI) software design pattern, which is a technique for achieving [Inversion of Control (IoC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) between classes and their dependencies.</span></span> <span data-ttu-id="dd2ba-105">La inserción de dependencias en .NET es un [ciudadano de primera clase](https://en.wikipedia.org/wiki/First-class_citizen), junto con la configuración, el registro y el patrón de opciones.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-105">Dependency injection in .NET is a [first-class citizen](https://en.wikipedia.org/wiki/First-class_citizen), along with configuration, logging, and the options pattern.</span></span>

<span data-ttu-id="dd2ba-106">Una *dependencia* es un objeto del que depende otro objeto.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-106">A *dependency* is an object that another object depends on.</span></span> <span data-ttu-id="dd2ba-107">Examine la clase `MessageWriter` siguiente con un método `Write` del que dependen otras clases:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-107">Examine the following `MessageWriter` class with a `Write` method that other classes depend on:</span></span>

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

<span data-ttu-id="dd2ba-108">Una clase puede crear una instancia de la clase `MessageWriter` para usar su método `Write`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-108">A class can create an instance of the `MessageWriter` class to make use of its `Write` method.</span></span> <span data-ttu-id="dd2ba-109">En el ejemplo siguiente, la clase `MessageWriter` es una dependencia de la clase `Worker`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-109">In the following example, the `MessageWriter` class is a dependency of the `Worker` class:</span></span>

```csharp
public class Worker : BackgroundService
{
    private readonly MessageWriter _messageWriter = new MessageWriter();

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _messageWriter.Write($"Worker running at: {DateTimeOffset.Now}");
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

<span data-ttu-id="dd2ba-110">La clase crea y depende directamente de la clase `MessageWriter`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-110">The class creates and directly depends on the `MessageWriter` class.</span></span> <span data-ttu-id="dd2ba-111">Las dependencias codificadas de forma rígida, como en el ejemplo anterior, son problemáticas y deben evitarse por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-111">Hard-coded dependencies, such as in the previous example, are problematic and should be avoided for the following reasons:</span></span>

- <span data-ttu-id="dd2ba-112">Para reemplazar `MessageWriter` por una implementación diferente, se debe modificar la clase `Worker`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-112">To replace `MessageWriter` with a different implementation, the `Worker` class must be modified.</span></span>
- <span data-ttu-id="dd2ba-113">Si `MessageWriter` tiene dependencias, deben configurarse según la clase `Worker`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-113">If `MessageWriter` has dependencies, they must also be configured by the `Worker` class.</span></span> <span data-ttu-id="dd2ba-114">En un proyecto grande con varias clases que dependen de `MessageWriter`, el código de configuración se dispersa por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-114">In a large project with multiple classes depending on `MessageWriter`, the configuration code becomes scattered across the app.</span></span>
- <span data-ttu-id="dd2ba-115">Esta implementación es difícil para realizar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-115">This implementation is difficult to unit test.</span></span> <span data-ttu-id="dd2ba-116">La aplicación debe usar una clase `MessageWriter` como boceto o código auxiliar, que no es posible con este enfoque.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-116">The app should use a mock or stub `MessageWriter` class, which isn't possible with this approach.</span></span>

<span data-ttu-id="dd2ba-117">La inserción de dependencias aborda estos problemas mediante:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-117">Dependency injection addresses these problems through:</span></span>

- <span data-ttu-id="dd2ba-118">Uso de una interfaz o clase base para abstraer la implementación de dependencias.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-118">The use of an interface or base class to abstract the dependency implementation.</span></span>
- <span data-ttu-id="dd2ba-119">Registro de la dependencia en un contenedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-119">Registration of the dependency in a service container.</span></span> <span data-ttu-id="dd2ba-120">.NET proporciona un contenedor de servicios integrado, <xref:System.IServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-120">.NET provides a built-in service container, <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="dd2ba-121">Normalmente, los servicios se registran al iniciar la aplicación y se anexan a una interfaz <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-121">Services are typically registered at the app's start-up, and appended to an <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>.</span></span> <span data-ttu-id="dd2ba-122">Una vez que se agregan todos los servicios, se usa <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> para crear el contenedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-122">Once all services are added, you use <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> to create the service container.</span></span>
- <span data-ttu-id="dd2ba-123">*Inserción* del servicio en el constructor de la clase en la que se usa.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-123">*Injection* of the service into the constructor of the class where it's used.</span></span> <span data-ttu-id="dd2ba-124">El marco de trabajo asume la responsabilidad de crear una instancia de la dependencia y de desecharla cuando ya no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-124">The framework takes on the responsibility of creating an instance of the dependency and disposing of it when it's no longer needed.</span></span>

<span data-ttu-id="dd2ba-125">Por ejemplo, la interfaz `IMessageWriter` define el método `Write`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-125">As an example, the `IMessageWriter` interface defines the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

<span data-ttu-id="dd2ba-126">Esta interfaz se implementa mediante un tipo concreto, `MessageWriter`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-126">This interface is implemented by a concrete type, `MessageWriter`:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

<span data-ttu-id="dd2ba-127">El código de ejemplo registra el servicio `IMessageWriter` con el tipo concreto `MessageWriter`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-127">The sample code registers the `IMessageWriter` service with the concrete type `MessageWriter`.</span></span> <span data-ttu-id="dd2ba-128">El método <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> registra el servicio mediante una duración con ámbito, definida como la duración de una única solicitud.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-128">The <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> method registers the service with a scoped lifetime, the lifetime of a single request.</span></span> <span data-ttu-id="dd2ba-129">Las [duraciones del servicio](#service-lifetimes) se describen más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-129">[Service lifetimes](#service-lifetimes) are described later in this article.</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

<span data-ttu-id="dd2ba-130">En la aplicación de ejemplo, el servicio `IMessageWriter` se solicita y usa para llamar al método `Write`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-130">In the sample app, the `IMessageWriter` service is requested and used to call the `Write` method:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

<span data-ttu-id="dd2ba-131">Mediante el uso del patrón de DI, el servicio de trabajo:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-131">By using the DI pattern, the worker service:</span></span>

- <span data-ttu-id="dd2ba-132">No usa el tipo concreto `MessageWriter`, solo la interfaz `IMessageWriter` que lo implementa.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-132">Doesn't use the concrete type `MessageWriter`, only the `IMessageWriter` interface that implements it.</span></span> <span data-ttu-id="dd2ba-133">Esto facilita el cambio de la implementación que el controlador utiliza sin modificar el controlador.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-133">That makes it easy to change the implementation that the controller uses without modifying the controller.</span></span>
- <span data-ttu-id="dd2ba-134">No crea una instancia de `MessageWriter`, la crea el contenedor de DI.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-134">Doesn't create an instance of `MessageWriter`, it's created by the DI container.</span></span>

<span data-ttu-id="dd2ba-135">La implementación de la interfaz de `IMessageWriter` se puede mejorar mediante el uso de la API de registro integrada:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-135">The implementation of the `IMessageWriter` interface can be improved by using the built-in logging API:</span></span>

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

<span data-ttu-id="dd2ba-136">El método `ConfigureServices` actualizado registra la nueva implementación de `IMessageWriter`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-136">The updated `ConfigureServices` method registers the new `IMessageWriter` implementation:</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

<span data-ttu-id="dd2ba-137">`LoggingMessageWriter` depende de <xref:Microsoft.Extensions.Logging.ILogger%601>, el que solicita en el constructor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-137">`LoggingMessageWriter` depends on <xref:Microsoft.Extensions.Logging.ILogger%601>, which it requests in the constructor.</span></span> <span data-ttu-id="dd2ba-138">`ILogger<TCategoryName>` es un [servicio proporcionado por el marco de trabajo](#framework-provided-services).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-138">`ILogger<TCategoryName>` is a [framework-provided service](#framework-provided-services).</span></span>

<span data-ttu-id="dd2ba-139">No es raro usar la inserción de dependencias de forma encadenada.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-139">It's not unusual to use dependency injection in a chained fashion.</span></span> <span data-ttu-id="dd2ba-140">Cada dependencia solicitada a su vez solicita sus propias dependencias.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-140">Each requested dependency in turn requests its own dependencies.</span></span> <span data-ttu-id="dd2ba-141">El contenedor resuelve las dependencias del gráfico y devuelve el servicio totalmente resuelto.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-141">The container resolves the dependencies in the graph and returns the fully resolved service.</span></span> <span data-ttu-id="dd2ba-142">El conjunto colectivo de dependencias que deben resolverse suele denominarse *árbol de dependencias*, *gráfico de dependencias* o *gráfico de objetos*.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-142">The collective set of dependencies that must be resolved is typically referred to as a *dependency tree*, *dependency graph*, or *object graph*.</span></span>

<span data-ttu-id="dd2ba-143">El contenedor resuelve `ILogger<TCategoryName>` aprovechando las ventajas de los [tipos abiertos (genéricos)](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), lo que elimina la necesidad de registrar todos los [tipos construidos (genéricos)](/dotnet/csharp/language-reference/language-specification/types#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-143">The container resolves `ILogger<TCategoryName>` by taking advantage of [(generic) open types](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), eliminating the need to register every [(generic) constructed type](/dotnet/csharp/language-reference/language-specification/types#constructed-types).</span></span>

<span data-ttu-id="dd2ba-144">En la terminología de la inserción de dependencias, un servicio:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-144">In dependency injection terminology, a service:</span></span>

- <span data-ttu-id="dd2ba-145">Por lo general, es un objeto que proporciona un servicio a otros objetos, como el servicio `IMessageWriter`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-145">Is typically an object that provides a service to other objects, such as the `IMessageWriter` service.</span></span>
- <span data-ttu-id="dd2ba-146">No está relacionado con un servicio web, aunque el servicio puede utilizar un servicio web.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-146">Is not related to a web service, although the service may use a web service.</span></span>

<span data-ttu-id="dd2ba-147">El marco de trabajo proporciona un sistema de registro sólido.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-147">The framework provides a robust logging system.</span></span> <span data-ttu-id="dd2ba-148">Las implementaciones de `IMessageWriter` que se muestran en los ejemplos anteriores se escribieron para mostrar la inserción de DI básica, no para implementar el registro.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-148">The `IMessageWriter` implementations shown in the preceding examples were written to demonstrate basic DI, not to implement logging.</span></span> <span data-ttu-id="dd2ba-149">La mayoría de las aplicaciones no deberían tener que escribir registradores.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-149">Most apps shouldn't need to write loggers.</span></span> <span data-ttu-id="dd2ba-150">En el código siguiente se muestra cómo usar el registro predeterminado, que solo requiere que `Worker` se registre en `ConfigureServices` como un servicio hospedado <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-150">The following code demonstrates using the default logging, which only requires the `Worker` to be registered in `ConfigureServices` as a hosted service <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>:</span></span>

```csharp
public class Worker : BackgroundService
{
    private readonly ILogger<Worker> _logger;

    public Worker(ILogger<Worker> logger) =>
        _logger = logger;

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogInformation("Worker running at: {time}", DateTimeOffset.Now);
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

<span data-ttu-id="dd2ba-151">Con el código anterior, no es necesario actualizar `ConfigureServices` porque el registro se proporciona a través del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-151">Using the preceding code, there is no need to update `ConfigureServices`, because logging is provided by the framework.</span></span>

## <a name="register-groups-of-services-with-extension-methods"></a><span data-ttu-id="dd2ba-152">Registro de grupos de servicios con métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="dd2ba-152">Register groups of services with extension methods</span></span>

<span data-ttu-id="dd2ba-153">Las extensiones de Microsoft usan una convención para registrar un grupo de servicios relacionados.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-153">Microsoft Extensions uses a convention for registering a group of related services.</span></span> <span data-ttu-id="dd2ba-154">La convención es usar un único método de extensión de `Add{GROUP_NAME}` para registrar todos los servicios requeridos por una característica de marco.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-154">The convention is to use a single `Add{GROUP_NAME}` extension method to register all of the services required by a framework feature.</span></span> <span data-ttu-id="dd2ba-155">Por ejemplo, el método de extensión <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> registra todos los servicios necesarios para usar las opciones.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-155">For example, the <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> extension method registers all of the services required for using options.</span></span>

## <a name="framework-provided-services"></a><span data-ttu-id="dd2ba-156">Servicios proporcionados por el marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="dd2ba-156">Framework-provided services</span></span>

<span data-ttu-id="dd2ba-157">El método `ConfigureServices` registra los servicios que la aplicación usa, incluidas las características de plataforma.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-157">The `ConfigureServices` method registers services that the app uses, including platform features.</span></span> <span data-ttu-id="dd2ba-158">Inicialmente, el valor `IServiceCollection` proporcionado a `ConfigureServices` tiene los servicios definidos por el marco en función de [cómo se configurara el host](generic-host.md#host-configuration).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-158">Initially, the `IServiceCollection` provided to `ConfigureServices` has services defined by the framework depending on [how the host was configured](generic-host.md#host-configuration).</span></span> <span data-ttu-id="dd2ba-159">En el caso de las aplicaciones basadas en las plantillas de .NET, el marco de trabajo registra cientos de servicios.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-159">For apps based on the .NET templates, the framework registers hundreds of services.</span></span>

<span data-ttu-id="dd2ba-160">En la tabla siguiente se ilustra una pequeña muestra de estos servicios registrados por el marco:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-160">The following table lists a small sample of these framework-registered services:</span></span>

| <span data-ttu-id="dd2ba-161">Tipo de servicio</span><span class="sxs-lookup"><span data-stu-id="dd2ba-161">Service Type</span></span>                                                                       | <span data-ttu-id="dd2ba-162">Período de duración</span><span class="sxs-lookup"><span data-stu-id="dd2ba-162">Lifetime</span></span>  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | <span data-ttu-id="dd2ba-163">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-163">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | <span data-ttu-id="dd2ba-164">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-164">Singleton</span></span> |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | <span data-ttu-id="dd2ba-165">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-165">Singleton</span></span> |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | <span data-ttu-id="dd2ba-166">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-166">Singleton</span></span> |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | <span data-ttu-id="dd2ba-167">Transitorio</span><span class="sxs-lookup"><span data-stu-id="dd2ba-167">Transient</span></span> |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | <span data-ttu-id="dd2ba-168">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-168">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | <span data-ttu-id="dd2ba-169">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-169">Singleton</span></span> |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | <span data-ttu-id="dd2ba-170">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-170">Singleton</span></span> |

## <a name="service-lifetimes"></a><span data-ttu-id="dd2ba-171">Duraciones de servicios</span><span class="sxs-lookup"><span data-stu-id="dd2ba-171">Service lifetimes</span></span>

<span data-ttu-id="dd2ba-172">Los servicios se pueden registrar con una de las duraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-172">Services can be registered with one of the following lifetimes:</span></span>

- <span data-ttu-id="dd2ba-173">Transitorio</span><span class="sxs-lookup"><span data-stu-id="dd2ba-173">Transient</span></span>
- <span data-ttu-id="dd2ba-174">Con ámbito</span><span class="sxs-lookup"><span data-stu-id="dd2ba-174">Scoped</span></span>
- <span data-ttu-id="dd2ba-175">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-175">Singleton</span></span>

<span data-ttu-id="dd2ba-176">En las secciones siguientes se describen cada una de las duraciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-176">The following sections describe each of the preceding lifetimes.</span></span> <span data-ttu-id="dd2ba-177">Elija una duración adecuada para cada servicio registrado.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-177">Choose an appropriate lifetime for each registered service.</span></span>

### <a name="transient"></a><span data-ttu-id="dd2ba-178">Transitorio</span><span class="sxs-lookup"><span data-stu-id="dd2ba-178">Transient</span></span>

<span data-ttu-id="dd2ba-179">Los servicios de duración transitoria se crean cada vez que el contenedor del servicio los solicita.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-179">Transient lifetime services are created each time they're requested from the service container.</span></span> <span data-ttu-id="dd2ba-180">Esta duración funciona mejor para servicios sin estado ligeros.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-180">This lifetime works best for lightweight, stateless services.</span></span> <span data-ttu-id="dd2ba-181">Registre los servicios transitorios con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-181">Register transient services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>.</span></span>

<span data-ttu-id="dd2ba-182">En las aplicaciones que procesan solicitudes, los servicios transitorios se eliminan al final de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-182">In apps that process requests, transient services are disposed at the end of the request.</span></span>

### <a name="scoped"></a><span data-ttu-id="dd2ba-183">Con ámbito</span><span class="sxs-lookup"><span data-stu-id="dd2ba-183">Scoped</span></span>

<span data-ttu-id="dd2ba-184">En el caso de las aplicaciones web, una duración con ámbito indica que los servicios se crean una vez por solicitud de cliente (conexión).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-184">For web applications, a scoped lifetime indicates that services are created once per client request (connection).</span></span> <span data-ttu-id="dd2ba-185">Registre los servicios con ámbito con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-185">Register scoped services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>.</span></span>

<span data-ttu-id="dd2ba-186">En las aplicaciones que procesan solicitudes, los servicios con ámbito se eliminan al final de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-186">In apps that process requests, scoped services are disposed at the end of the request.</span></span>

<span data-ttu-id="dd2ba-187">Cuando se usa Entity Framework Core, el método de extensión <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> registra tipos de `DbContext` con una duración de ámbito de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-187">When using Entity Framework Core, the <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> extension method registers `DbContext` types with a scoped lifetime by default.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2ba-188">**No** resuelva un servicio con ámbito desde un singleton y tenga cuidado de no hacerlo indirectamente, por ejemplo, a través de un servicio transitorio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-188">Do \***not** _ resolve a scoped service from a singleton and be careful not to do so indirectly, for example, through a transient service.</span></span> <span data-ttu-id="dd2ba-189">Puede dar lugar a que el servicio adopte un estado incorrecto al procesar solicitudes posteriores.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-189">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="dd2ba-190">Basta con:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-190">It's fine to:</span></span>
>
> - <span data-ttu-id="dd2ba-191">Resolver un servicio singleton desde un servicio con ámbito o transitorio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-191">Resolve a singleton service from a scoped or transient service.</span></span>
> - <span data-ttu-id="dd2ba-192">Resolver un servicio con ámbito desde otro servicio con ámbito o transitorio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-192">Resolve a scoped service from another scoped or transient service.</span></span>

<span data-ttu-id="dd2ba-193">De manera predeterminada, en el entorno de desarrollo, resolver un servicio desde otro servicio con una duración más larga genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-193">By default, in the development environment, resolving a service from another service with a longer lifetime throws an exception.</span></span> <span data-ttu-id="dd2ba-194">Para más información, vea [Validación del ámbito](#scope-validation).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-194">For more information, see [Scope validation](#scope-validation).</span></span>

### <a name="singleton"></a><span data-ttu-id="dd2ba-195">Singleton</span><span class="sxs-lookup"><span data-stu-id="dd2ba-195">Singleton</span></span>

<span data-ttu-id="dd2ba-196">Los servicios de duración de singleton se crean de alguna de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-196">Singleton lifetime services are created either:</span></span>

- <span data-ttu-id="dd2ba-197">La primera vez que se solicitan.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-197">The first time they're requested.</span></span>
- <span data-ttu-id="dd2ba-198">Mediante el desarrollador, al proporcionar una instancia de implementación directamente al contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-198">By the developer, when providing an implementation instance directly to the container.</span></span> <span data-ttu-id="dd2ba-199">Este enfoque rara vez es necesario.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-199">This approach is rarely needed.</span></span>

<span data-ttu-id="dd2ba-200">Cada solicitud siguiente de la implementación del servicio desde el contenedor de inserción de dependencias utiliza la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-200">Every subsequent request of the service implementation from the dependency injection container uses the same instance.</span></span> <span data-ttu-id="dd2ba-201">Si la aplicación requiere un comportamiento de singleton, permita que el contenedor de servicios administre la duración del servicio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-201">If the app requires singleton behavior, allow the service container to manage the service's lifetime.</span></span> <span data-ttu-id="dd2ba-202">No implemente el modelo de diseño singleton y proporcione el código para desechar el singleton.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-202">Don't implement the singleton design pattern and provide code to dispose of the singleton.</span></span> <span data-ttu-id="dd2ba-203">Los servicios nunca deben desecharse mediante el código que haya resuelto el servicio del contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-203">Services should never be disposed by code that resolved the service from the container.</span></span> <span data-ttu-id="dd2ba-204">Si un tipo o fábrica se registra como singleton, el contenedor elimina el singleton de manera automática.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-204">If a type or factory is registered as a singleton, the container disposes the singleton automatically.</span></span>

<span data-ttu-id="dd2ba-205">Registre los servicios singleton con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-205">Register singleton services with <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>.</span></span> <span data-ttu-id="dd2ba-206">Los servicios singleton deben ser seguros para los subprocesos y se suelen usar en servicios sin estado.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-206">Singleton services must be thread safe and are often used in stateless services.</span></span>

<span data-ttu-id="dd2ba-207">En las aplicaciones que procesan solicitudes, los servicios singleton se eliminan cuando <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> se elimina al cerrarse la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-207">In apps that process requests, singleton services are disposed when the <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> is disposed on application shutdown.</span></span> <span data-ttu-id="dd2ba-208">Como no se libera memoria hasta que se apaga la aplicación, se debe tener en cuenta el uso de memoria con un servicio singleton.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-208">Because memory is not released until the app is shut down, consider memory use with a singleton service.</span></span>

> [!WARNING]
> <span data-ttu-id="dd2ba-209">_*_No_*_ resuelva un servicio con ámbito desde un singleton.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-209">Do _*_not_*_ resolve a scoped service from a singleton.</span></span> <span data-ttu-id="dd2ba-210">Puede dar lugar a que el servicio adopte un estado incorrecto al procesar solicitudes posteriores.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-210">It may cause the service to have incorrect state when processing subsequent requests.</span></span> <span data-ttu-id="dd2ba-211">Basta con resolver un servicio singleton desde un servicio con ámbito o transitorio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-211">It's fine to resolve a singleton service from a scoped or transient service.</span></span>

## <a name="service-registration-methods"></a><span data-ttu-id="dd2ba-212">Métodos de registro del servicio</span><span class="sxs-lookup"><span data-stu-id="dd2ba-212">Service registration methods</span></span>

<span data-ttu-id="dd2ba-213">El marco proporciona métodos de extensión de registro del servicio que resultan útiles en escenarios específicos:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-213">The framework provides service registration extension methods that are useful in specific scenarios:</span></span>

| <span data-ttu-id="dd2ba-214">Método</span><span class="sxs-lookup"><span data-stu-id="dd2ba-214">Method</span></span> | <span data-ttu-id="dd2ba-215">Automático</span><span class="sxs-lookup"><span data-stu-id="dd2ba-215">Automatic</span></span><br><span data-ttu-id="dd2ba-216">objeto</span><span class="sxs-lookup"><span data-stu-id="dd2ba-216">object</span></span><br><span data-ttu-id="dd2ba-217">eliminación</span><span class="sxs-lookup"><span data-stu-id="dd2ba-217">disposal</span></span> | <span data-ttu-id="dd2ba-218">Múltiple</span><span class="sxs-lookup"><span data-stu-id="dd2ba-218">Multiple</span></span><br><span data-ttu-id="dd2ba-219">implementaciones</span><span class="sxs-lookup"><span data-stu-id="dd2ba-219">implementations</span></span> | <span data-ttu-id="dd2ba-220">Transferencia de argumentos</span><span class="sxs-lookup"><span data-stu-id="dd2ba-220">Pass args</span></span> |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br><span data-ttu-id="dd2ba-221">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-221">Example:</span></span><br><br>`services.AddSingleton<IMyDep, MyDep>();` | <span data-ttu-id="dd2ba-222">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-222">Yes</span></span> | <span data-ttu-id="dd2ba-223">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-223">Yes</span></span> | <span data-ttu-id="dd2ba-224">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-224">No</span></span> |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br><span data-ttu-id="dd2ba-225">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-225">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | <span data-ttu-id="dd2ba-226">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-226">Yes</span></span> | <span data-ttu-id="dd2ba-227">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-227">Yes</span></span> | <span data-ttu-id="dd2ba-228">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-228">Yes</span></span> |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br><span data-ttu-id="dd2ba-229">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-229">Example:</span></span><br><br>`services.AddSingleton<MyDep>();` | <span data-ttu-id="dd2ba-230">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-230">Yes</span></span> | <span data-ttu-id="dd2ba-231">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-231">No</span></span> | <span data-ttu-id="dd2ba-232">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-232">No</span></span> |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br><span data-ttu-id="dd2ba-233">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-233">Examples:</span></span><br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | <span data-ttu-id="dd2ba-234">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-234">No</span></span> | <span data-ttu-id="dd2ba-235">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-235">Yes</span></span> | <span data-ttu-id="dd2ba-236">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-236">Yes</span></span> |
| `AddSingleton(new {IMPLEMENTATION})`<br><br><span data-ttu-id="dd2ba-237">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-237">Examples:</span></span><br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | <span data-ttu-id="dd2ba-238">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-238">No</span></span> | <span data-ttu-id="dd2ba-239">No</span><span class="sxs-lookup"><span data-stu-id="dd2ba-239">No</span></span> | <span data-ttu-id="dd2ba-240">Sí</span><span class="sxs-lookup"><span data-stu-id="dd2ba-240">Yes</span></span> |

<span data-ttu-id="dd2ba-241">Para obtener más información sobre el tipo de eliminación, consulte la sección [Eliminación de servicios](dependency-injection-guidelines.md#disposal-of-services).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-241">For more information on type disposal, see the [Disposal of services](dependency-injection-guidelines.md#disposal-of-services) section.</span></span>

<span data-ttu-id="dd2ba-242">El registro de un servicio con un solo tipo de implementación es equivalente al registro de ese servicio con la misma implementación y el mismo tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-242">Registering a service with only an implementation type is equivalent to registering that service with the same implementation and service type.</span></span> <span data-ttu-id="dd2ba-243">Por eso no se pueden registrar varias implementaciones de un servicio mediante los métodos que no toman un tipo de servicio explícito.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-243">This is why multiple implementations of a service cannot be registered using the methods that don't take an explicit service type.</span></span> <span data-ttu-id="dd2ba-244">Estos métodos pueden registrar varias instancias de un servicio, pero todos tienen el mismo tipo de *implementación*.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-244">These methods can register multiple _instances\* of a service, but they will all have the same *implementation* type.</span></span>

<span data-ttu-id="dd2ba-245">Cualquiera de los métodos de registro de servicio anteriores se puede usar para registrar varias instancias de servicio del mismo tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-245">Any of the above service registration methods can be used to register multiple service instances of the same service type.</span></span> <span data-ttu-id="dd2ba-246">En el ejemplo siguiente se llama a `AddSingleton` dos veces con `IMessageWriter` como tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-246">In the following example, `AddSingleton` is called twice with `IMessageWriter` as the service type.</span></span> <span data-ttu-id="dd2ba-247">La segunda llamada a `AddSingleton` invalida la anterior cuando se resuelve como `IMessageWriter`, y se agrega a la anterior cuando varios servicios se resuelven mediante `IEnumerable<IMessageWriter>`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-247">The second call to `AddSingleton` overrides the previous one when resolved as `IMessageWriter` and adds to the previous one when multiple services are resolved via `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="dd2ba-248">Los servicios aparecen en el orden en que se han registrado al resolverse mediante `IEnumerable<{SERVICE}>`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-248">Services appear in the order they were registered when resolved via `IEnumerable<{SERVICE}>`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/Program.cs" highlight="19-24":::

<span data-ttu-id="dd2ba-249">El código fuente de ejemplo anterior registra dos implementaciones de `IMessageWriter`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-249">The preceding sample source code registers two implementations of the `IMessageWriter`.</span></span>

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/ExampleService.cs" highlight="9-18":::

<span data-ttu-id="dd2ba-250">`ExampleService` define dos parámetros de constructor, un único `IMessageWriter` y un `IEnumerable<IMessageWriter>`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-250">The `ExampleService` defines two constructor parameters; a single `IMessageWriter`, and an `IEnumerable<IMessageWriter>`.</span></span> <span data-ttu-id="dd2ba-251">El `IMessageWriter` único es la última implementación registrada, mientras que `IEnumerable<IMessageWriter>` representa todas las implementaciones registradas.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-251">The single `IMessageWriter` is the last implementation to have been registered, whereas the `IEnumerable<IMessageWriter>` represents all registered implementations.</span></span>

<span data-ttu-id="dd2ba-252">El marco también proporciona métodos de extensión `TryAdd{LIFETIME}`, que registran el servicio solo si todavía no hay registrada una implementación.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-252">The framework also provides `TryAdd{LIFETIME}` extension methods, which register the service only if there isn't already an implementation registered.</span></span>

<span data-ttu-id="dd2ba-253">En el ejemplo siguiente, la llamada a `AddSingleton` registra `ConsoleMessageWriter` como una implementación para `IMessageWriter`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-253">In the following example, the call to `AddSingleton` registers `ConsoleMessageWriter` as an implementation for `IMessageWriter`.</span></span> <span data-ttu-id="dd2ba-254">La llamada a `TryAddSingleton` no tiene ningún efecto porque `IMessageWriter` ya tiene una implementación registrada:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-254">The call to `TryAddSingleton` has no effect because `IMessageWriter` already has a registered implementation:</span></span>

```csharp
services.AddSingleton<IMessageWriter, ConsoleMessageWriter>();
services.TryAddSingleton<IMessageWriter, LoggingMessageWriter>();
```

<span data-ttu-id="dd2ba-255">`TryAddSingleton` no tiene ningún efecto, puesto que ya se agregó y "try" generará un error.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-255">The `TryAddSingleton` has no effect, as it was already added and the "try" will fail.</span></span> <span data-ttu-id="dd2ba-256">`ExampleService` impondría lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-256">The `ExampleService` would assert the following:</span></span>

```csharp
public class ExampleService
{
    public ExampleService(
        IMessageWriter messageWriter,
        IEnumerable<IMessageWriter> messageWriters)
    {
        Trace.Assert(messageWriter is ConsoleMessageWriter);
        Trace.Assert(messageWriters.Single() is ConsoleMessageWriter);
    }
}
```

<span data-ttu-id="dd2ba-257">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-257">For more information, see:</span></span>

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

<span data-ttu-id="dd2ba-258">Los métodos [TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) registran el servicio solo si todavía no hay una implementación *del mismo tipo*.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-258">The [TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) methods register the service only if there isn't already an implementation *of the same type*.</span></span> <span data-ttu-id="dd2ba-259">A través de `IEnumerable<{SERVICE}>` se resuelven varios servicios.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-259">Multiple services are resolved via `IEnumerable<{SERVICE}>`.</span></span> <span data-ttu-id="dd2ba-260">Al registrar los servicios, agregue una instancia si no se ha agregado ya una del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-260">When registering services, add an instance if one of the same types hasn't already been added.</span></span> <span data-ttu-id="dd2ba-261">Los autores de bibliotecas usan `TryAddEnumerable` para evitar el registro de varias copias de una implementación en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-261">Library authors use `TryAddEnumerable` to avoid registering multiple copies of an implementation in the container.</span></span>

<span data-ttu-id="dd2ba-262">En el ejemplo siguiente, la primera llamada a `TryAddEnumerable` registra `MessageWriter` como una implementación para `IMessageWriter1`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-262">In the following example, the first call to `TryAddEnumerable` registers `MessageWriter` as an implementation for `IMessageWriter1`.</span></span> <span data-ttu-id="dd2ba-263">La segunda llamada registra `MessageWriter` para `IMessageWriter2`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-263">The second call registers `MessageWriter` for `IMessageWriter2`.</span></span> <span data-ttu-id="dd2ba-264">La tercera llamada no tiene ningún efecto porque `IMessageWriter1` ya tiene una implementación registrada de `MessageWriter`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-264">The third call has no effect because `IMessageWriter1` already has a registered implementation of `MessageWriter`:</span></span>

```csharp
public interface IMessageWriter1 { }
public interface IMessageWriter2 { }

public class MessageWriter : IMessageWriter1, IMessageWriter2
{
}

services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter2, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
```

<span data-ttu-id="dd2ba-265">Normalmente, el registro del servicio es independiente, excepto cuando se registran varias implementaciones del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-265">Service registration is generally order independent except when registering multiple implementations of the same type.</span></span>

<span data-ttu-id="dd2ba-266">`IServiceCollection` es una colección de objetos <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-266">`IServiceCollection` is a collection of <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor> objects.</span></span> <span data-ttu-id="dd2ba-267">En el ejemplo siguiente se muestra cómo registrar un servicio mediante la creación e incorporación de un elemento `ServiceDescriptor`:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-267">The following example shows how to register a service by creating and adding a `ServiceDescriptor`:</span></span>

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

<span data-ttu-id="dd2ba-268">Los métodos `Add{LIFETIME}` integrados usan el mismo enfoque.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-268">The built-in `Add{LIFETIME}` methods use the same approach.</span></span> <span data-ttu-id="dd2ba-269">Por ejemplo, consulte el [código fuente de AddScoped](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-269">For example, see the [AddScoped source code](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).</span></span>

### <a name="constructor-injection-behavior"></a><span data-ttu-id="dd2ba-270">Comportamiento de inserción de constructor</span><span class="sxs-lookup"><span data-stu-id="dd2ba-270">Constructor injection behavior</span></span>

<span data-ttu-id="dd2ba-271">Los servicios se pueden resolver mediante el uso de:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-271">Services can be resolved by using:</span></span>

- <xref:System.IServiceProvider>
- <span data-ttu-id="dd2ba-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-272"><xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:</span></span>
  - <span data-ttu-id="dd2ba-273">Crea objetos que no están registrados en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-273">Creates objects that aren't registered in the container.</span></span>
  - <span data-ttu-id="dd2ba-274">Se utiliza con algunas características de Framework.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-274">Used with some framework features.</span></span>

<span data-ttu-id="dd2ba-275">Los constructores pueden aceptar argumentos que no se proporcionan mediante la inserción de dependencias, pero los argumentos deben asignar valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-275">Constructors can accept arguments that aren't provided by dependency injection, but the arguments must assign default values.</span></span>

<span data-ttu-id="dd2ba-276">Cuando se resuelven los servicios mediante `IServiceProvider` o `ActivatorUtilities`, la inserción del constructor requiere un constructor *público*.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-276">When services are resolved by `IServiceProvider` or `ActivatorUtilities`, constructor injection requires a *public* constructor.</span></span>

<span data-ttu-id="dd2ba-277">Cuando se resuelven los servicios mediante `ActivatorUtilities`, la inserción del constructor requiere que exista solo un constructor aplicable.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-277">When services are resolved by `ActivatorUtilities`, constructor injection requires that only one applicable constructor exists.</span></span> <span data-ttu-id="dd2ba-278">Se admiten las sobrecargas de constructor, pero solo puede existir una sobrecarga cuyos argumentos pueda cumplir la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-278">Constructor overloads are supported, but only one overload can exist whose arguments can all be fulfilled by dependency injection.</span></span>

## <a name="scope-validation"></a><span data-ttu-id="dd2ba-279">Validación del ámbito</span><span class="sxs-lookup"><span data-stu-id="dd2ba-279">Scope validation</span></span>

<span data-ttu-id="dd2ba-280">Cuando la aplicación se ejecuta en el entorno `Development` y llama a [CreateDefaultBuilder](generic-host.md#default-builder-settings) para compilar el host, el proveedor de servicios predeterminado realiza comprobaciones para confirmar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd2ba-280">When the app runs in the `Development` environment and calls [CreateDefaultBuilder](generic-host.md#default-builder-settings) to build the host, the default service provider performs checks to verify that:</span></span>

- <span data-ttu-id="dd2ba-281">Los servicios con ámbito no se resuelven desde el proveedor de servicios raíz.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-281">Scoped services aren't resolved from the root service provider.</span></span>
- <span data-ttu-id="dd2ba-282">Los servicios con ámbito no se insertan en singletons.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-282">Scoped services aren't injected into singletons.</span></span>

<span data-ttu-id="dd2ba-283">El proveedor de servicios raíz se crea cuando se llama a <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-283">The root service provider is created when <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> is called.</span></span> <span data-ttu-id="dd2ba-284">La vigencia del proveedor de servicios raíz es la misma que la de la aplicación cuando el proveedor se inicia con la aplicación, y se elimina cuando la aplicación se cierra.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-284">The root service provider's lifetime corresponds to the app's lifetime when the provider starts with the app and is disposed when the app shuts down.</span></span>

<span data-ttu-id="dd2ba-285">De la eliminación de los servicios con ámbito se encarga el contenedor que los creó.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-285">Scoped services are disposed by the container that created them.</span></span> <span data-ttu-id="dd2ba-286">Si un servicio con ámbito se crea en el contenedor raíz, su duración sube a la del singleton, ya que solo lo puede eliminar el contenedor raíz cuando la aplicación se cierra.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-286">If a scoped service is created in the root container, the service's lifetime is effectively promoted to singleton because it's only disposed by the root container when the app shuts down.</span></span> <span data-ttu-id="dd2ba-287">Al validar los ámbitos de servicio, este tipo de situaciones se detectan cuando se llama a `BuildServiceProvider`.</span><span class="sxs-lookup"><span data-stu-id="dd2ba-287">Validating service scopes catches these situations when `BuildServiceProvider` is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd2ba-288">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd2ba-288">See also</span></span>

- [<span data-ttu-id="dd2ba-289">Uso de la inserción de dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="dd2ba-289">Use dependency injection in .NET</span></span>](dependency-injection-usage.md)
- [<span data-ttu-id="dd2ba-290">Instrucciones para la inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="dd2ba-290">Dependency injection guidelines</span></span>](dependency-injection-guidelines.md)
- [<span data-ttu-id="dd2ba-291">Inserción de dependencias en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dd2ba-291">Dependency injection in ASP.NET Core</span></span>](/aspnet/core/fundamentals/dependency-injection)
- [<span data-ttu-id="dd2ba-292">Patrones de la Conferencia NDC para el desarrollo de aplicaciones de inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="dd2ba-292">NDC Conference Patterns for DI app development</span></span>](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [<span data-ttu-id="dd2ba-293">Principio de dependencias explícitas</span><span class="sxs-lookup"><span data-stu-id="dd2ba-293">Explicit dependencies principle</span></span>](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [<span data-ttu-id="dd2ba-294">Los contenedores de inversión de control y el patrón de inserción de dependencias (Martin Fowler)</span><span class="sxs-lookup"><span data-stu-id="dd2ba-294">Inversion of control containers and the dependency injection pattern (Martin Fowler)</span></span>](https://www.martinfowler.com/articles/injection.html)
- <span data-ttu-id="dd2ba-295">Los errores de DI deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).</span><span class="sxs-lookup"><span data-stu-id="dd2ba-295">DI bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
