---
title: Host genérico de .NET
author: IEvangelist
description: Obtenga información sobre el host genérico de .NET, que es responsable de la administración de inicio y duración de la aplicación.
ms.author: dapine
ms.date: 12/18/2020
ms.openlocfilehash: bf6d5ad624bbed46994633abace0af64712757f3
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "102402199"
---
# <a name="net-generic-host"></a><span data-ttu-id="3a4be-103">Host genérico de .NET</span><span class="sxs-lookup"><span data-stu-id="3a4be-103">.NET Generic Host</span></span>

<span data-ttu-id="3a4be-104">Las plantillas de servicio de trabajo crean un host genérico de .NET, <xref:Microsoft.Extensions.Hosting.HostBuilder>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-104">The Worker Service templates create a .NET Generic Host, <xref:Microsoft.Extensions.Hosting.HostBuilder>.</span></span> <span data-ttu-id="3a4be-105">El host genérico se puede usar con otros tipos de aplicaciones .NET, como aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="3a4be-105">The Generic Host can be used with other types of .NET applications, such as Console apps.</span></span>

<span data-ttu-id="3a4be-106">El *host* es un objeto que encapsula todos los recursos de la aplicación, como:</span><span class="sxs-lookup"><span data-stu-id="3a4be-106">A *host* is an object that encapsulates an app's resources, such as:</span></span>

- <span data-ttu-id="3a4be-107">Inserción de dependencias (ID)</span><span class="sxs-lookup"><span data-stu-id="3a4be-107">Dependency injection (DI)</span></span>
- <span data-ttu-id="3a4be-108">Registro</span><span class="sxs-lookup"><span data-stu-id="3a4be-108">Logging</span></span>
- <span data-ttu-id="3a4be-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="3a4be-109">Configuration</span></span>
- <span data-ttu-id="3a4be-110">Implementaciones de `IHostedService`</span><span class="sxs-lookup"><span data-stu-id="3a4be-110">`IHostedService` implementations</span></span>

<span data-ttu-id="3a4be-111">Cuando se inicia un host, llama a <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType> en cada implementación de <xref:Microsoft.Extensions.Hosting.IHostedService> registrada en la colección de servicios hospedados del contenedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="3a4be-111">When a host starts, it calls <xref:Microsoft.Extensions.Hosting.IHostedService.StartAsync%2A?displayProperty=nameWithType> on each implementation of <xref:Microsoft.Extensions.Hosting.IHostedService> registered in the service container's collection of hosted services.</span></span> <span data-ttu-id="3a4be-112">En una aplicación de servicio de trabajo, todas las implementaciones de `IHostedService` que contienen instancias de <xref:Microsoft.Extensions.Hosting.BackgroundService> tienen los métodos <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> a los que se llama.</span><span class="sxs-lookup"><span data-stu-id="3a4be-112">In a worker service app, all `IHostedService` implementations that contain <xref:Microsoft.Extensions.Hosting.BackgroundService> instances have their <xref:Microsoft.Extensions.Hosting.BackgroundService.ExecuteAsync%2A?displayProperty=nameWithType> methods called.</span></span>

<span data-ttu-id="3a4be-113">La razón principal para incluir todos los recursos interdependientes de la aplicación en un objeto es la administración de la duración: el control sobre el inicio de la aplicación y el apagado estable.</span><span class="sxs-lookup"><span data-stu-id="3a4be-113">The main reason for including all of the app's interdependent resources in one object is lifetime management: control over app startup and graceful shutdown.</span></span> <span data-ttu-id="3a4be-114">Esto se logra con el paquete NuGet [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting).</span><span class="sxs-lookup"><span data-stu-id="3a4be-114">This is achieved with the [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet package.</span></span>

## <a name="set-up-a-host"></a><span data-ttu-id="3a4be-115">Configuración de un host</span><span class="sxs-lookup"><span data-stu-id="3a4be-115">Set up a host</span></span>

<span data-ttu-id="3a4be-116">Normalmente se configura, compila y ejecuta el host por el código de la clase `Program`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-116">The host is typically configured, built, and run by code in the `Program` class.</span></span> <span data-ttu-id="3a4be-117">El método `Main` realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a4be-117">The `Main` method:</span></span>

- <span data-ttu-id="3a4be-118">Llama a un método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> para crear y configurar un objeto del generador.</span><span class="sxs-lookup"><span data-stu-id="3a4be-118">Calls a <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder> method to create and configure a builder object.</span></span>
- <span data-ttu-id="3a4be-119">Llama a <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> para crear una instancia de <xref:Microsoft.Extensions.Hosting.IHost>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-119">Calls <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build> to create an <xref:Microsoft.Extensions.Hosting.IHost> instance.</span></span>
- <span data-ttu-id="3a4be-120">Llama al método <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> o <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> en el objeto host.</span><span class="sxs-lookup"><span data-stu-id="3a4be-120">Calls <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.Run%2A> or <xref:Microsoft.Extensions.Hosting.HostingAbstractionsHostExtensions.RunAsync%2A> method on the host object.</span></span>

<span data-ttu-id="3a4be-121">Las plantillas de servicio de trabajo de .NET generan el código siguiente para crear un host genérico:</span><span class="sxs-lookup"><span data-stu-id="3a4be-121">The .NET Worker Service templates generate the following code to create a Generic Host:</span></span>

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureServices((hostContext, services) =>
            {
                services.AddHostedService<Worker>();
            });
}
```

## <a name="default-builder-settings"></a><span data-ttu-id="3a4be-122">Configuración predeterminada del generador</span><span class="sxs-lookup"><span data-stu-id="3a4be-122">Default builder settings</span></span>

<span data-ttu-id="3a4be-123">El método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a4be-123">The <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A> method:</span></span>

- <span data-ttu-id="3a4be-124">Establece la raíz de contenido en la ruta de acceso devuelta por <xref:System.IO.Directory.GetCurrentDirectory>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-124">Sets the content root to the path returned by <xref:System.IO.Directory.GetCurrentDirectory>.</span></span>
- <span data-ttu-id="3a4be-125">Carga la [configuración de host](#host-configuration) de:</span><span class="sxs-lookup"><span data-stu-id="3a4be-125">Loads [host configuration](#host-configuration) from:</span></span>
  - <span data-ttu-id="3a4be-126">Variables de entorno con el prefijo `DOTNET_`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-126">Environment variables prefixed with `DOTNET_`.</span></span>
  - <span data-ttu-id="3a4be-127">Argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a4be-127">Command-line arguments.</span></span>
- <span data-ttu-id="3a4be-128">Carga la configuración de aplicación de:</span><span class="sxs-lookup"><span data-stu-id="3a4be-128">Loads app configuration from:</span></span>
  - <span data-ttu-id="3a4be-129">*appsettings.json*.</span><span class="sxs-lookup"><span data-stu-id="3a4be-129">*appsettings.json*.</span></span>
  - <span data-ttu-id="3a4be-130">*appsettings.{Environment}.json*.</span><span class="sxs-lookup"><span data-stu-id="3a4be-130">*appsettings.{Environment}.json*.</span></span>
  - <span data-ttu-id="3a4be-131">Administrador de secretos, cuando la aplicación se ejecuta en el entorno `Development`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-131">Secret Manager when the app runs in the `Development` environment.</span></span>
  - <span data-ttu-id="3a4be-132">Variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="3a4be-132">Environment variables.</span></span>
  - <span data-ttu-id="3a4be-133">Argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3a4be-133">Command-line arguments.</span></span>
- <span data-ttu-id="3a4be-134">Agrega los siguientes proveedores de registro:</span><span class="sxs-lookup"><span data-stu-id="3a4be-134">Adds the following logging providers:</span></span>
  - <span data-ttu-id="3a4be-135">Consola</span><span class="sxs-lookup"><span data-stu-id="3a4be-135">Console</span></span>
  - <span data-ttu-id="3a4be-136">Depuración</span><span class="sxs-lookup"><span data-stu-id="3a4be-136">Debug</span></span>
  - <span data-ttu-id="3a4be-137">EventSource</span><span class="sxs-lookup"><span data-stu-id="3a4be-137">EventSource</span></span>
  - <span data-ttu-id="3a4be-138">EventLog (solo si se ejecuta en Windows)</span><span class="sxs-lookup"><span data-stu-id="3a4be-138">EventLog (only when running on Windows)</span></span>
- <span data-ttu-id="3a4be-139">Permite la validación del ámbito y la [validación de dependencias](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild) si el entorno es `Development`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-139">Enables scope validation and [dependency validation](xref:Microsoft.Extensions.DependencyInjection.ServiceProviderOptions.ValidateOnBuild) when the environment is `Development`.</span></span>

<span data-ttu-id="3a4be-140">El método `ConfigureServices` expone la capacidad de agregar servicios a la instancia de <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-140">The `ConfigureServices` method exposes the ability to add services to the <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="3a4be-141">Más adelante, estos servicios se pueden poner a disposición de la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="3a4be-141">Later, these services can be made available from dependency injection.</span></span>

## <a name="framework-provided-services"></a><span data-ttu-id="3a4be-142">Servicios proporcionados por el marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="3a4be-142">Framework-provided services</span></span>

<span data-ttu-id="3a4be-143">Los servicios siguientes se registran de forma automática:</span><span class="sxs-lookup"><span data-stu-id="3a4be-143">The following services are registered automatically:</span></span>

- [<span data-ttu-id="3a4be-144">IHostApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="3a4be-144">IHostApplicationLifetime</span></span>](#ihostapplicationlifetime)
- [<span data-ttu-id="3a4be-145">IHostLifetime</span><span class="sxs-lookup"><span data-stu-id="3a4be-145">IHostLifetime</span></span>](#ihostlifetime)
- [<span data-ttu-id="3a4be-146">IHostEnvironment</span><span class="sxs-lookup"><span data-stu-id="3a4be-146">IHostEnvironment</span></span>](#ihostenvironment)

## <a name="ihostapplicationlifetime"></a><span data-ttu-id="3a4be-147">IHostApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="3a4be-147">IHostApplicationLifetime</span></span>

<span data-ttu-id="3a4be-148">Permite insertar el servicio <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> en cualquier clase para controlar las tareas posteriores al inicio y el cierre estable.</span><span class="sxs-lookup"><span data-stu-id="3a4be-148">Inject the <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime> service into any class to handle post-startup and graceful shutdown tasks.</span></span> <span data-ttu-id="3a4be-149">Tres de las propiedades de la interfaz son tokens de cancelación que se usan para registrar los métodos del controlador de eventos de inicio y detención de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3a4be-149">Three properties on the interface are cancellation tokens used to register app start and app stop event handler methods.</span></span> <span data-ttu-id="3a4be-150">La interfaz también incluye un método <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-150">The interface also includes a <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication> method.</span></span>

<span data-ttu-id="3a4be-151">El ejemplo siguiente es una implementación de `IHostedService` que registra los eventos `IHostApplicationLifetime`:</span><span class="sxs-lookup"><span data-stu-id="3a4be-151">The following example is an `IHostedService` implementation that registers `IHostApplicationLifetime` events:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/ExampleHostedService.cs" highlight="18-20":::

<span data-ttu-id="3a4be-152">La plantilla de servicio de trabajo se puede modificar para agregar la implementación de `ExampleHostedService`:</span><span class="sxs-lookup"><span data-stu-id="3a4be-152">The Worker Service template could be modified to add the `ExampleHostedService` implementation:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="1-16,36" highlight="15":::

<span data-ttu-id="3a4be-153">La aplicación escribiría la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3a4be-153">The application would write the following sample output:</span></span>

:::code language="csharp" source="snippets/configuration/app-lifetime/Program.cs" range="17-35":::

## <a name="ihostlifetime"></a><span data-ttu-id="3a4be-154">IHostLifetime</span><span class="sxs-lookup"><span data-stu-id="3a4be-154">IHostLifetime</span></span>

<span data-ttu-id="3a4be-155">La implementación de <xref:Microsoft.Extensions.Hosting.IHostLifetime> controla cuándo se inicia el host y cuándo se detiene.</span><span class="sxs-lookup"><span data-stu-id="3a4be-155">The <xref:Microsoft.Extensions.Hosting.IHostLifetime> implementation controls when the host starts and when it stops.</span></span> <span data-ttu-id="3a4be-156">Se usa la última implementación registrada.</span><span class="sxs-lookup"><span data-stu-id="3a4be-156">The last implementation registered is used.</span></span>

<span data-ttu-id="3a4be-157">`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime` es la implementación predeterminada de `IHostLifetime`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-157">`Microsoft.Extensions.Hosting.Internal.ConsoleLifetime` is the default `IHostLifetime` implementation.</span></span> <span data-ttu-id="3a4be-158">`ConsoleLifetime`:</span><span class="sxs-lookup"><span data-stu-id="3a4be-158">`ConsoleLifetime`:</span></span>

- <span data-ttu-id="3a4be-159">Escucha <kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT) o [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM), y llama a <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A> para iniciar el proceso de apagado.</span><span class="sxs-lookup"><span data-stu-id="3a4be-159">Listens for <kbd>Ctrl</kbd>+<kbd>C</kbd>, [SIGINT](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGINT), or [SIGTERM](https://en.wikipedia.org/wiki/Signal_(IPC)#SIGTERM) and calls <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime.StopApplication%2A> to start the shutdown process.</span></span>
- <span data-ttu-id="3a4be-160">Desbloquea extensiones como `RunAsync` y `WaitForShutdownAsync`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-160">Unblocks extensions such as `RunAsync` and `WaitForShutdownAsync`.</span></span>

## <a name="ihostenvironment"></a><span data-ttu-id="3a4be-161">IHostEnvironment</span><span class="sxs-lookup"><span data-stu-id="3a4be-161">IHostEnvironment</span></span>

<span data-ttu-id="3a4be-162">Permite insertar el servicio <xref:Microsoft.Extensions.Hosting.IHostEnvironment> en una clase para obtener información sobre los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a4be-162">Inject the <xref:Microsoft.Extensions.Hosting.IHostEnvironment> service into a class to get information about the following settings:</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ApplicationName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootFileProvider?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.ContentRootPath?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostEnvironment.EnvironmentName?displayProperty=nameWithType>

## <a name="host-configuration"></a><span data-ttu-id="3a4be-163">Configuración de host</span><span class="sxs-lookup"><span data-stu-id="3a4be-163">Host configuration</span></span>

<span data-ttu-id="3a4be-164">La configuración de host se usa para configurar las propiedades de la implementación de [IHostEnvironment](#ihostenvironment).</span><span class="sxs-lookup"><span data-stu-id="3a4be-164">Host configuration is used to configure properties of the [IHostEnvironment](#ihostenvironment) implementation.</span></span>

<span data-ttu-id="3a4be-165">La configuración de host está disponible en [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration) dentro del método <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A>.</span><span class="sxs-lookup"><span data-stu-id="3a4be-165">The host configuration is available in [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration) within the <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> method.</span></span> <span data-ttu-id="3a4be-166">Al llamar al método `ConfigureAppConfiguration`, `HostBuilderContext` y `IConfigurationBuilder` se pasan a `configureDelegate`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-166">When calling the `ConfigureAppConfiguration` method, the `HostBuilderContext` and `IConfigurationBuilder` are passed into the `configureDelegate`.</span></span> <span data-ttu-id="3a4be-167">`configureDelegate` se define como `Action<HostBuilderContext, IConfigurationBuilder>`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-167">The `configureDelegate` is defined as an `Action<HostBuilderContext, IConfigurationBuilder>`.</span></span> <span data-ttu-id="3a4be-168">El contexto del generador de hosts expone la propiedad `.Configuration`, que es una instancia de `IConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-168">The host builder context exposes the `.Configuration` property, which is an instance of `IConfiguration`.</span></span> <span data-ttu-id="3a4be-169">Representa la configuración generada a partir del host, mientras que `IConfigurationBuilder` es el objeto de generador que se usa para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a4be-169">It represents the configuration built from the host, whereas the `IConfigurationBuilder` is the builder object used to configure the app.</span></span>

> [!TIP]
> <span data-ttu-id="3a4be-170">Después de llamar a `ConfigureAppConfiguration`, `HostBuilderContext.Configuration` se reemplaza por la [configuración de la aplicación](#app-configuration).</span><span class="sxs-lookup"><span data-stu-id="3a4be-170">After `ConfigureAppConfiguration` is called the `HostBuilderContext.Configuration` is replaced with the [app config](#app-configuration).</span></span>

<span data-ttu-id="3a4be-171">Para agregar la configuración de host, llame a <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A> en `IHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-171">To add host configuration, call <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureHostConfiguration%2A> on `IHostBuilder`.</span></span> <span data-ttu-id="3a4be-172">Se puede llamar varias veces a `ConfigureHostConfiguration` con resultados de suma.</span><span class="sxs-lookup"><span data-stu-id="3a4be-172">`ConfigureHostConfiguration` can be called multiple times with additive results.</span></span> <span data-ttu-id="3a4be-173">El host usa cualquier opción que establezca un valor en último lugar en una clave determinada.</span><span class="sxs-lookup"><span data-stu-id="3a4be-173">The host uses whichever option sets a value last on a given key.</span></span>

<span data-ttu-id="3a4be-174">En el ejemplo siguiente se crea la configuración de host:</span><span class="sxs-lookup"><span data-stu-id="3a4be-174">The following example creates host configuration:</span></span>

:::code language="csharp" source="snippets/configuration/console-host/Program.cs" highlight="19-25":::

## <a name="app-configuration"></a><span data-ttu-id="3a4be-175">Configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3a4be-175">App configuration</span></span>

<span data-ttu-id="3a4be-176">La configuración de la aplicación se crea llamando a <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> en `IHostBuilder`.</span><span class="sxs-lookup"><span data-stu-id="3a4be-176">App configuration is created by calling <xref:Microsoft.Extensions.Hosting.HostBuilder.ConfigureAppConfiguration%2A> on `IHostBuilder`.</span></span> <span data-ttu-id="3a4be-177">Se puede llamar varias veces a `ConfigureAppConfiguration` con resultados de suma.</span><span class="sxs-lookup"><span data-stu-id="3a4be-177">`ConfigureAppConfiguration` can be called multiple times with additive results.</span></span> <span data-ttu-id="3a4be-178">La aplicación usa cualquier opción que establezca un valor en último lugar en una clave determinada.</span><span class="sxs-lookup"><span data-stu-id="3a4be-178">The app uses whichever option sets a value last on a given key.</span></span>

<span data-ttu-id="3a4be-179">La configuración creada por `ConfigureAppConfiguration` está disponible en [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A) para las operaciones posteriores y como servicio de ID.</span><span class="sxs-lookup"><span data-stu-id="3a4be-179">The configuration created by `ConfigureAppConfiguration` is available in [HostBuilderContext.Configuration](xref:Microsoft.Extensions.Hosting.HostBuilderContext.Configuration%2A) for subsequent operations and as a service from DI.</span></span> <span data-ttu-id="3a4be-180">La configuración de host también se agrega a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a4be-180">The host configuration is also added to the app configuration.</span></span>

<span data-ttu-id="3a4be-181">Para obtener más información, vea [Configuración en .NET](configuration.md).</span><span class="sxs-lookup"><span data-stu-id="3a4be-181">For more information, see [Configuration in .NET](configuration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a4be-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a4be-182">See also</span></span>

- [<span data-ttu-id="3a4be-183">Configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="3a4be-183">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="3a4be-184">Host web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a4be-184">ASP.NET Core Web Host</span></span>](/aspnet/core/fundamentals/host/web-host)
- <span data-ttu-id="3a4be-185">Los errores del host genérico deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).</span><span class="sxs-lookup"><span data-stu-id="3a4be-185">Generic host bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
