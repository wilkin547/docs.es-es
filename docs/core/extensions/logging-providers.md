---
title: Proveedores de registro en .NET
description: Obtenga información sobre cómo se usa la API del proveedor de registro en aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 02/16/2021
ms.openlocfilehash: 7265e51a4d92cd99abebef2ebf0bc5db37b306e3
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "102402210"
---
# <a name="logging-providers-in-net"></a><span data-ttu-id="536a7-103">Proveedores de registro en .NET</span><span class="sxs-lookup"><span data-stu-id="536a7-103">Logging providers in .NET</span></span>

<span data-ttu-id="536a7-104">Los proveedores de registro conservan los registros, excepto el proveedor `Console`, que solo muestra los registros como salida estándar.</span><span class="sxs-lookup"><span data-stu-id="536a7-104">Logging providers persist logs, except for the `Console` provider, which only displays logs as standard output.</span></span> <span data-ttu-id="536a7-105">Por ejemplo, el proveedor de Azure Application Insights almacena los registros en Azure Application Insights.</span><span class="sxs-lookup"><span data-stu-id="536a7-105">For example, the Azure Application Insights provider stores logs in Azure Application Insights.</span></span> <span data-ttu-id="536a7-106">Se pueden habilitar varios proveedores.</span><span class="sxs-lookup"><span data-stu-id="536a7-106">Multiple providers can be enabled.</span></span>

<span data-ttu-id="536a7-107">Las plantillas de aplicación predeterminadas de .NET Worker:</span><span class="sxs-lookup"><span data-stu-id="536a7-107">The default .NET Worker app templates:</span></span>

- <span data-ttu-id="536a7-108">usan el [host genérico](generic-host.md);</span><span class="sxs-lookup"><span data-stu-id="536a7-108">Use the [Generic Host](generic-host.md).</span></span>
- <span data-ttu-id="536a7-109">llaman a <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>, que agrega los siguientes proveedores de registro:</span><span class="sxs-lookup"><span data-stu-id="536a7-109">Call <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>, which adds the following logging providers:</span></span>
  - [<span data-ttu-id="536a7-110">Consola</span><span class="sxs-lookup"><span data-stu-id="536a7-110">Console</span></span>](#console)
  - [<span data-ttu-id="536a7-111">Depurar</span><span class="sxs-lookup"><span data-stu-id="536a7-111">Debug</span></span>](#debug)
  - [<span data-ttu-id="536a7-112">EventSource</span><span class="sxs-lookup"><span data-stu-id="536a7-112">EventSource</span></span>](#event-source)
  - <span data-ttu-id="536a7-113">[EventLog](#windows-eventlog): Solo Windows</span><span class="sxs-lookup"><span data-stu-id="536a7-113">[EventLog](#windows-eventlog): Windows only</span></span>

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

<span data-ttu-id="536a7-114">En el código anterior se muestra la clase `Program` creada con las plantillas de aplicación de .NET Worker.</span><span class="sxs-lookup"><span data-stu-id="536a7-114">The preceding code shows the `Program` class created with the .NET Worker app templates.</span></span> <span data-ttu-id="536a7-115">En las siguientes secciones se proporcionan ejemplos basados en las plantillas de aplicación de .NET Worker, que usan el host genérico.</span><span class="sxs-lookup"><span data-stu-id="536a7-115">The next several sections provide samples based on the .NET Worker app templates, which use the Generic Host.</span></span>

<span data-ttu-id="536a7-116">Para invalidar el conjunto predeterminado de proveedores de registro agregados por `Host.CreateDefaultBuilder`, llame a `ClearProviders` y agregue los proveedores de registro que quiera.</span><span class="sxs-lookup"><span data-stu-id="536a7-116">To override the default set of logging providers added by `Host.CreateDefaultBuilder`, call `ClearProviders` and add the logging providers you want.</span></span> <span data-ttu-id="536a7-117">Por ejemplo, el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="536a7-117">For example, the following code:</span></span>

- <span data-ttu-id="536a7-118">Llama a <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> para quitar todas las instancias de <xref:Microsoft.Extensions.Logging.ILoggerProvider> del generador.</span><span class="sxs-lookup"><span data-stu-id="536a7-118">Calls <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> to remove all the <xref:Microsoft.Extensions.Logging.ILoggerProvider> instances from the builder.</span></span>
- <span data-ttu-id="536a7-119">Agrega el proveedor de registro [Console](#console).</span><span class="sxs-lookup"><span data-stu-id="536a7-119">Adds the [Console](#console) logging provider.</span></span>

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
```

<span data-ttu-id="536a7-120">Para otros proveedores, vea:</span><span class="sxs-lookup"><span data-stu-id="536a7-120">For additional providers, see:</span></span>

- <span data-ttu-id="536a7-121">[Proveedores de registro integrados](#built-in-logging-providers)</span><span class="sxs-lookup"><span data-stu-id="536a7-121">[Built-in logging providers](#built-in-logging-providers).</span></span>
- <span data-ttu-id="536a7-122">[Proveedores de registro de terceros](#third-party-logging-providers)</span><span class="sxs-lookup"><span data-stu-id="536a7-122">[Third-party logging providers](#third-party-logging-providers).</span></span>

## <a name="configure-a-service-that-depends-on-ilogger"></a><span data-ttu-id="536a7-123">Configuración de un servicio que dependa de ILogger</span><span class="sxs-lookup"><span data-stu-id="536a7-123">Configure a service that depends on ILogger</span></span>

<span data-ttu-id="536a7-124">Para configurar un servicio que dependa de `ILogger<T>`, use la inserción de constructores o proporcione un método Factory.</span><span class="sxs-lookup"><span data-stu-id="536a7-124">To configure a service that depends on `ILogger<T>`, use constructor injection or provide a factory method.</span></span> <span data-ttu-id="536a7-125">Usar un Factory Method es la opción recomendada si no tiene otra alternativa.</span><span class="sxs-lookup"><span data-stu-id="536a7-125">The factory method approach is recommended only if there is no other option.</span></span> <span data-ttu-id="536a7-126">Por ejemplo, tomemos un servicio que necesita una instancia de `ILogger<T>` proporcionada por DI:</span><span class="sxs-lookup"><span data-stu-id="536a7-126">For example, consider a service that needs an `ILogger<T>` instance provided by DI:</span></span>

```csharp
.ConfigureServices(services =>
    services.AddSingleton<IExampleService>(container =>
        new DefaultExampleService
        {
            Logger = container.GetRequiredService<ILogger<IExampleService>>()
        }));
```

<span data-ttu-id="536a7-127">El código anterior es un elemento [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) que se ejecuta la primera vez que el contenedor de DI necesita crear una instancia de `IExampleService`.</span><span class="sxs-lookup"><span data-stu-id="536a7-127">The preceding code is a [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) that runs the first time the DI container needs to construct an instance of `IExampleService`.</span></span> <span data-ttu-id="536a7-128">Puede acceder a cualquiera de los servicios registrados de esta forma.</span><span class="sxs-lookup"><span data-stu-id="536a7-128">You can access any of the registered services in this way.</span></span>

## <a name="built-in-logging-providers"></a><span data-ttu-id="536a7-129">Proveedores de registro integrados</span><span class="sxs-lookup"><span data-stu-id="536a7-129">Built-in logging providers</span></span>

<span data-ttu-id="536a7-130">Las extensiones de Microsoft incluyen los siguientes proveedores de registro como parte de las bibliotecas en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="536a7-130">Microsoft Extensions include the following logging providers as part of the runtime libraries:</span></span>

- [<span data-ttu-id="536a7-131">Consola</span><span class="sxs-lookup"><span data-stu-id="536a7-131">Console</span></span>](#console)
- [<span data-ttu-id="536a7-132">Depurar</span><span class="sxs-lookup"><span data-stu-id="536a7-132">Debug</span></span>](#debug)
- [<span data-ttu-id="536a7-133">EventSource</span><span class="sxs-lookup"><span data-stu-id="536a7-133">EventSource</span></span>](#event-source)
- [<span data-ttu-id="536a7-134">EventLog</span><span class="sxs-lookup"><span data-stu-id="536a7-134">EventLog</span></span>](#windows-eventlog)

<span data-ttu-id="536a7-135">Microsoft envía los siguientes proveedores de registro, pero no como parte de las bibliotecas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="536a7-135">The following logging providers are shipped by Microsoft, but not as part of the runtime libraries.</span></span> <span data-ttu-id="536a7-136">Deben instalarse como paquetes NuGet adicionales.</span><span class="sxs-lookup"><span data-stu-id="536a7-136">They must be installed as additional NuGet packages.</span></span>

- [<span data-ttu-id="536a7-137">AzureAppServicesFile y AzureAppServicesBlob</span><span class="sxs-lookup"><span data-stu-id="536a7-137">AzureAppServicesFile and AzureAppServicesBlob</span></span>](#azure-app-service)
- [<span data-ttu-id="536a7-138">ApplicationInsights</span><span class="sxs-lookup"><span data-stu-id="536a7-138">ApplicationInsights</span></span>](#azure-application-insights)

### <a name="console"></a><span data-ttu-id="536a7-139">Consola</span><span class="sxs-lookup"><span data-stu-id="536a7-139">Console</span></span>

<span data-ttu-id="536a7-140">El proveedor `Console` registra la salida en la consola.</span><span class="sxs-lookup"><span data-stu-id="536a7-140">The `Console` provider logs output to the console.</span></span>

### <a name="debug"></a><span data-ttu-id="536a7-141">Depuración</span><span class="sxs-lookup"><span data-stu-id="536a7-141">Debug</span></span>

<span data-ttu-id="536a7-142">El proveedor `Debug` escribe la salida del registro mediante la clase [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug).</span><span class="sxs-lookup"><span data-stu-id="536a7-142">The `Debug` provider writes log output by using the [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug) class.</span></span> <span data-ttu-id="536a7-143">Las llamadas a `System.Diagnostics.Debug.WriteLine` escriben en el proveedor `Debug`.</span><span class="sxs-lookup"><span data-stu-id="536a7-143">Calls to `System.Diagnostics.Debug.WriteLine` write to the `Debug` provider.</span></span>

<span data-ttu-id="536a7-144">En Linux, la ubicación del registro del proveedor `Debug` depende de la distribución y puede ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="536a7-144">On Linux, the `Debug` provider log location is distribution-dependent and may be one of the following:</span></span>

- <span data-ttu-id="536a7-145">*/var/log/message*</span><span class="sxs-lookup"><span data-stu-id="536a7-145">*/var/log/message*</span></span>
- <span data-ttu-id="536a7-146">*/var/log/syslog*</span><span class="sxs-lookup"><span data-stu-id="536a7-146">*/var/log/syslog*</span></span>

### <a name="event-source"></a><span data-ttu-id="536a7-147">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="536a7-147">Event Source</span></span>

<span data-ttu-id="536a7-148">El proveedor `EventSource` escribe en un origen de eventos multiplataforma con el nombre `Microsoft-Extensions-Logging`.</span><span class="sxs-lookup"><span data-stu-id="536a7-148">The `EventSource` provider writes to a cross-platform event source with the name `Microsoft-Extensions-Logging`.</span></span> <span data-ttu-id="536a7-149">En Windows, el proveedor utiliza [ETW](/windows/win32/etw/event-tracing-portal).</span><span class="sxs-lookup"><span data-stu-id="536a7-149">On Windows, the provider uses [ETW](/windows/win32/etw/event-tracing-portal).</span></span>

#### <a name="dotnet-trace-tooling"></a><span data-ttu-id="536a7-150">herramienta de seguimiento de dotnet</span><span class="sxs-lookup"><span data-stu-id="536a7-150">dotnet trace tooling</span></span>

<span data-ttu-id="536a7-151">La herramienta de [seguimiento de dotnet](../diagnostics/dotnet-trace.md) es una herramienta global de CLI multiplataforma que permite la recopilación de seguimientos de .NET Core de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="536a7-151">The [dotnet-trace](../diagnostics/dotnet-trace.md) tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process.</span></span> <span data-ttu-id="536a7-152">La herramienta recopila datos del proveedor <xref:Microsoft.Extensions.Logging.EventSource> mediante un <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>.</span><span class="sxs-lookup"><span data-stu-id="536a7-152">The tool collects <xref:Microsoft.Extensions.Logging.EventSource> provider data using a <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>.</span></span>

<span data-ttu-id="536a7-153">Vea [dotnet-trace](../diagnostics/dotnet-trace.md) para obtener instrucciones de instalación.</span><span class="sxs-lookup"><span data-stu-id="536a7-153">See [dotnet-trace](../diagnostics/dotnet-trace.md) for installation instructions.</span></span> <span data-ttu-id="536a7-154">Para ver un tutorial de diagnóstico con `dotnet-trace`, consulte [Depuración del uso intensivo de la CPU en .NET Core](../diagnostics/debug-highcpu.md).</span><span class="sxs-lookup"><span data-stu-id="536a7-154">For a diagnostic tutorial using `dotnet-trace`, see [Debug high CPU usage in .NET Core](../diagnostics/debug-highcpu.md).</span></span>

### <a name="windows-eventlog"></a><span data-ttu-id="536a7-155">Registro de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="536a7-155">Windows EventLog</span></span>

<span data-ttu-id="536a7-156">El proveedor `EventLog` envía la salida del registro al Registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="536a7-156">The `EventLog` provider sends log output to the Windows Event Log.</span></span> <span data-ttu-id="536a7-157">A diferencia de otros proveedores, el proveedor `EventLog` ***no*** hereda la configuración de no proveedor predeterminada.</span><span class="sxs-lookup"><span data-stu-id="536a7-157">Unlike the other providers, the `EventLog` provider does ***not*** inherit the default non-provider settings.</span></span> <span data-ttu-id="536a7-158">Si no se especifican valores de registro de `EventLog`, el valor predeterminado será `LogLevel.Warning`.</span><span class="sxs-lookup"><span data-stu-id="536a7-158">If `EventLog` log settings aren't specified, they default to `LogLevel.Warning`.</span></span>

<span data-ttu-id="536a7-159">Para registrar eventos inferiores a <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType>, establezca el nivel de registro de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="536a7-159">To log events lower than <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType>, explicitly set the log level.</span></span> <span data-ttu-id="536a7-160">En el ejemplo siguiente se establece el nivel de registro predeterminado del registro de eventos en <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="536a7-160">The following example sets the Event Log default log level to <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>:</span></span>

```json
"Logging": {
  "EventLog": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

<span data-ttu-id="536a7-161">Las [sobrecargas de AddEventLog](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) pueden pasar <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>.</span><span class="sxs-lookup"><span data-stu-id="536a7-161">[AddEventLog overloads](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) can pass in <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>.</span></span> <span data-ttu-id="536a7-162">Si es `null` o no se especifica, se usa la siguiente configuración predeterminada:</span><span class="sxs-lookup"><span data-stu-id="536a7-162">If `null` or not specified, the following default settings are used:</span></span>

- <span data-ttu-id="536a7-163">`LogName`: "Application"</span><span class="sxs-lookup"><span data-stu-id="536a7-163">`LogName`: "Application"</span></span>
- <span data-ttu-id="536a7-164">`SourceName`: ".NET Runtime"</span><span class="sxs-lookup"><span data-stu-id="536a7-164">`SourceName`: ".NET Runtime"</span></span>
- <span data-ttu-id="536a7-165">`MachineName`: se usa el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="536a7-165">`MachineName`: The local machine name is used.</span></span>

<span data-ttu-id="536a7-166">En el código siguiente se cambia el valor predeterminado de `SourceName` (`".NET Runtime"`) por `CustomLogs`:</span><span class="sxs-lookup"><span data-stu-id="536a7-166">The following code changes the `SourceName` from the default value of `".NET Runtime"` to `CustomLogs`:</span></span>

```csharp
public class Program
{
    static async Task Main(string[] args)
    {
        using IHost host = CreateHostBuilder(args).Build();

        // Application code should start here.

        await host.RunAsync();
    }

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddEventLog(configuration =>
                    configuration.SourceName = "CustomLogs"));
}
```

### <a name="azure-app-service"></a><span data-ttu-id="536a7-167">Azure App Service</span><span class="sxs-lookup"><span data-stu-id="536a7-167">Azure App Service</span></span>

<span data-ttu-id="536a7-168">El paquete de proveedor [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) escribe los registros en archivos de texto en el sistema de archivos de una aplicación de Azure App Service y en [Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) en una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="536a7-168">The [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) provider package writes logs to text files in an Azure App Service app's file system and to [blob storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) in an Azure Storage account.</span></span>

<span data-ttu-id="536a7-169">El paquete de proveedor no se incluye en las bibliotecas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="536a7-169">The provider package isn't included in the runtime libraries.</span></span> <span data-ttu-id="536a7-170">Para usar el proveedor, agregue el paquete del proveedor al proyecto.</span><span class="sxs-lookup"><span data-stu-id="536a7-170">To use the provider, add the provider package to the project.</span></span>

<span data-ttu-id="536a7-171">Para configurar las opciones de proveedor, use <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> y <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="536a7-171">To configure provider settings, use <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> and <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>, as shown in the following example:</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using IHost host = CreateHostBuilder(args).Build();

        // Application code should start here.

        await host.RunAsync();
    }

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddAzureWebAppDiagnostics())
            .ConfigureServices(services =>
                services.Configure<AzureFileLoggerOptions>(options =>
                {
                    options.FileName = "azure-diagnostics-";
                    options.FileSizeLimit = 50 * 1024;
                    options.RetainedFileCountLimit = 5;
                })
                .Configure<AzureBlobLoggerOptions>(options =>
                {
                    options.BlobName = "log.txt";
                }));
}
```

<span data-ttu-id="536a7-172">Cuando se implementa en Azure App Service, la aplicación usa la configuración de la sección [Registros de App Service](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) de la página **App Service** de Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="536a7-172">When deployed to Azure App Service, the app uses the settings in the [App Service logs](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) section of the **App Service** page of the Azure portal.</span></span> <span data-ttu-id="536a7-173">Cuando se actualiza la configuración siguiente, los cambios se aplican de inmediato sin necesidad de reiniciar ni de volver a implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="536a7-173">When the following settings are updated, the changes take effect immediately without requiring a restart or redeployment of the app.</span></span>

- <span data-ttu-id="536a7-174">**Registro de la aplicación (sistema de archivos)**</span><span class="sxs-lookup"><span data-stu-id="536a7-174">**Application Logging (Filesystem)**</span></span>
- <span data-ttu-id="536a7-175">**Registro de la aplicación (blob)**</span><span class="sxs-lookup"><span data-stu-id="536a7-175">**Application Logging (Blob)**</span></span>

<span data-ttu-id="536a7-176">La ubicación predeterminada de los archivos de registro es la carpeta *D:\\home\\LogFiles\\Application* y el nombre de archivo predeterminado es *diagnostics-aaaammdd.txt*.</span><span class="sxs-lookup"><span data-stu-id="536a7-176">The default location for log files is in the *D:\\home\\LogFiles\\Application* folder, and the default file name is *diagnostics-yyyymmdd.txt*.</span></span> <span data-ttu-id="536a7-177">El límite de tamaño de archivo predeterminado es 10 MB, y el número máximo predeterminado de archivos que se conservan es 2.</span><span class="sxs-lookup"><span data-stu-id="536a7-177">The default file size limit is 10 MB, and the default maximum number of files retained is 2.</span></span> <span data-ttu-id="536a7-178">El nombre de blob predeterminado es *{nombre-de-la-aplicación}{marca de tiempo}/aaaa/mm/dd/hh/{guid}-applicationLog.txt*.</span><span class="sxs-lookup"><span data-stu-id="536a7-178">The default blob name is *{app-name}{timestamp}/yyyy/mm/dd/hh/{guid}-applicationLog.txt*.</span></span>

<span data-ttu-id="536a7-179">El proveedor solo realiza registros cuando el proyecto se ejecuta en el entorno de Azure.</span><span class="sxs-lookup"><span data-stu-id="536a7-179">This provider only logs when the project runs in the Azure environment.</span></span>

#### <a name="azure-log-streaming"></a><span data-ttu-id="536a7-180">Secuencias de registro de Azure</span><span class="sxs-lookup"><span data-stu-id="536a7-180">Azure log streaming</span></span>

<span data-ttu-id="536a7-181">El streaming de registro de Azure permiten ver la actividad de registro en tiempo real desde:</span><span class="sxs-lookup"><span data-stu-id="536a7-181">Azure log streaming supports viewing log activity in real time from:</span></span>

- <span data-ttu-id="536a7-182">El servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="536a7-182">The app server</span></span>
- <span data-ttu-id="536a7-183">El servidor web</span><span class="sxs-lookup"><span data-stu-id="536a7-183">The web server</span></span>
- <span data-ttu-id="536a7-184">Error del seguimiento de solicitudes</span><span class="sxs-lookup"><span data-stu-id="536a7-184">Failed request tracing</span></span>

<span data-ttu-id="536a7-185">Para configurar las secuencias de registro de Azure:</span><span class="sxs-lookup"><span data-stu-id="536a7-185">To configure Azure log streaming:</span></span>

- <span data-ttu-id="536a7-186">Desplácese a la página **Registros de App Service** desde la página del portal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="536a7-186">Navigate to the **App Service logs** page from the app's portal page.</span></span>
- <span data-ttu-id="536a7-187">Establezca **Registro de la aplicación (sistema de archivos)** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="536a7-187">Set **Application Logging (Filesystem)** to **On**.</span></span>
- <span data-ttu-id="536a7-188">Elija el **Nivel** de registro.</span><span class="sxs-lookup"><span data-stu-id="536a7-188">Choose the log **Level**.</span></span> <span data-ttu-id="536a7-189">Esta configuración solo se aplica al streaming de registro de Azure.</span><span class="sxs-lookup"><span data-stu-id="536a7-189">This setting only applies to Azure log streaming.</span></span>

<span data-ttu-id="536a7-190">Desplácese a la página **Secuencia de registro** para ver los registros.</span><span class="sxs-lookup"><span data-stu-id="536a7-190">Navigate to the **Log Stream** page to view logs.</span></span> <span data-ttu-id="536a7-191">Los mensajes que se registran lo hacen con la interfaz `ILogger`.</span><span class="sxs-lookup"><span data-stu-id="536a7-191">The logged messages are logged with the `ILogger` interface.</span></span>

### <a name="azure-application-insights"></a><span data-ttu-id="536a7-192">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="536a7-192">Azure Application Insights</span></span>

<span data-ttu-id="536a7-193">El paquete de proveedor [Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) escribe los registros en [Azure Application Insights](/azure/azure-monitor/app/cloudservices).</span><span class="sxs-lookup"><span data-stu-id="536a7-193">The [Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) provider package writes logs to [Azure Application Insights](/azure/azure-monitor/app/cloudservices).</span></span> <span data-ttu-id="536a7-194">Application Insights es un servicio que supervisa una aplicación web y proporciona herramientas para consultar y analizar los datos de telemetría.</span><span class="sxs-lookup"><span data-stu-id="536a7-194">Application Insights is a service that monitors a web app and provides tools for querying and analyzing the telemetry data.</span></span> <span data-ttu-id="536a7-195">Si usa este proveedor, puede consultar y analizar los registros mediante las herramientas de Application Insights.</span><span class="sxs-lookup"><span data-stu-id="536a7-195">If you use this provider, you can query and analyze your logs by using the Application Insights tools.</span></span>

<span data-ttu-id="536a7-196">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="536a7-196">For more information, see the following resources:</span></span>

- [<span data-ttu-id="536a7-197">Información general de Application Insights</span><span class="sxs-lookup"><span data-stu-id="536a7-197">Application Insights overview</span></span>](/azure/application-insights/app-insights-overview)
- <span data-ttu-id="536a7-198">[ApplicationInsightsLoggerProvider para los registros de .NET Core ILogger](/azure/azure-monitor/app/ilogger): comience aquí si quiere implementar el proveedor de registro sin el resto de la telemetría de Application Insights.</span><span class="sxs-lookup"><span data-stu-id="536a7-198">[ApplicationInsightsLoggerProvider for .NET Core ILogger logs](/azure/azure-monitor/app/ilogger) - Start here if you want to implement the logging provider without the rest of Application Insights telemetry.</span></span>
- <span data-ttu-id="536a7-199">[Adaptadores de registro de Application Insights](/azure/azure-monitor/app/asp-net-trace-logs)</span><span class="sxs-lookup"><span data-stu-id="536a7-199">[Application Insights logging adapters](/azure/azure-monitor/app/asp-net-trace-logs).</span></span>
- <span data-ttu-id="536a7-200">[Instalación, configuración e inicialización del SDK de Application Insights](/learn/modules/instrument-web-app-code-with-application-insights): tutorial interactivo en el sitio de Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="536a7-200">[Install, configure, and initialize the Application Insights SDK](/learn/modules/instrument-web-app-code-with-application-insights) - Interactive tutorial on the Microsoft Learn site.</span></span>

## <a name="third-party-logging-providers"></a><span data-ttu-id="536a7-201">Proveedores de registro de terceros</span><span class="sxs-lookup"><span data-stu-id="536a7-201">Third-party logging providers</span></span>

<span data-ttu-id="536a7-202">Estas son algunas plataformas de registro de terceros que funcionan con las distintas cargas de trabajo de .NET:</span><span class="sxs-lookup"><span data-stu-id="536a7-202">Here are some third-party logging frameworks that work with various .NET workloads:</span></span>

- <span data-ttu-id="536a7-203">[elmah.io](https://elmah.io) ([repositorio de GitHub](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="536a7-203">[elmah.io](https://elmah.io) ([GitHub repo](https://github.com/elmahio/Elmah.Io.Extensions.Logging))</span></span>
- <span data-ttu-id="536a7-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([repositorio de GitHub](https://github.com/mattwcole/gelf-extensions-logging))</span><span class="sxs-lookup"><span data-stu-id="536a7-204">[Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([GitHub repo](https://github.com/mattwcole/gelf-extensions-logging))</span></span>
- <span data-ttu-id="536a7-205">[JSNLog](http://jsnlog.com) ([repositorio de GitHub](https://github.com/mperdeck/jsnlog))</span><span class="sxs-lookup"><span data-stu-id="536a7-205">[JSNLog](http://jsnlog.com) ([GitHub repo](https://github.com/mperdeck/jsnlog))</span></span>
- <span data-ttu-id="536a7-206">[KissLog.net](https://kisslog.net) ([repositorio de GitHub](https://github.com/catalingavan/KissLog-net))</span><span class="sxs-lookup"><span data-stu-id="536a7-206">[KissLog.net](https://kisslog.net) ([GitHub repo](https://github.com/catalingavan/KissLog-net))</span></span>
- <span data-ttu-id="536a7-207">[Log4Net](https://logging.apache.org/log4net) ([repositorio de GitHub](https://github.com/apache/logging-log4net))</span><span class="sxs-lookup"><span data-stu-id="536a7-207">[Log4Net](https://logging.apache.org/log4net) ([GitHub repo](https://github.com/apache/logging-log4net))</span></span>
- <span data-ttu-id="536a7-208">[Loggr](https://loggr.net) ([repositorio de GitHub](https://github.com/imobile3/Loggr.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="536a7-208">[Loggr](https://loggr.net) ([GitHub repo](https://github.com/imobile3/Loggr.Extensions.Logging))</span></span>
- <span data-ttu-id="536a7-209">[NLog](https://nlog-project.org) ([repositorio de GitHub](https://github.com/NLog/NLog.Extensions.Logging))</span><span class="sxs-lookup"><span data-stu-id="536a7-209">[NLog](https://nlog-project.org) ([GitHub repo](https://github.com/NLog/NLog.Extensions.Logging))</span></span>
- <span data-ttu-id="536a7-210">[NReco.Logging](https://github.com/nreco/logging/blob/master/README.md) ([repositorio de GitHub](https://github.com/nreco/logging))</span><span class="sxs-lookup"><span data-stu-id="536a7-210">[NReco.Logging](https://github.com/nreco/logging/blob/master/README.md) ([GitHub repo](https://github.com/nreco/logging))</span></span>
- <span data-ttu-id="536a7-211">[Sentry](https://sentry.io/welcome) ([repositorio de GitHub](https://github.com/getsentry/sentry-dotnet))</span><span class="sxs-lookup"><span data-stu-id="536a7-211">[Sentry](https://sentry.io/welcome) ([GitHub repo](https://github.com/getsentry/sentry-dotnet))</span></span>
- <span data-ttu-id="536a7-212">[Serilog](https://serilog.net) ([repositorio de GitHub](https://github.com/serilog/serilog-sinks-console))</span><span class="sxs-lookup"><span data-stu-id="536a7-212">[Serilog](https://serilog.net) ([GitHub repo](https://github.com/serilog/serilog-sinks-console))</span></span>
- <span data-ttu-id="536a7-213">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([repositorio de GitHub](https://github.com/googleapis/google-cloud-dotnet))</span><span class="sxs-lookup"><span data-stu-id="536a7-213">[Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([GitHub repo](https://github.com/googleapis/google-cloud-dotnet))</span></span>

<span data-ttu-id="536a7-214">Algunas plataformas de terceros pueden realizar [registro semántico, también conocido como registro estructurado](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).</span><span class="sxs-lookup"><span data-stu-id="536a7-214">Some third-party frameworks can perform [semantic logging, also known as structured logging](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).</span></span>

<span data-ttu-id="536a7-215">El uso de una plataforma de terceros es similar al uso de uno de los proveedores integrados:</span><span class="sxs-lookup"><span data-stu-id="536a7-215">Using a third-party framework is similar to using one of the built-in providers:</span></span>

1. <span data-ttu-id="536a7-216">Agregue un paquete NuGet al proyecto.</span><span class="sxs-lookup"><span data-stu-id="536a7-216">Add a NuGet package to your project.</span></span>
1. <span data-ttu-id="536a7-217">Llame a un método de extensión `ILoggerFactory` o `ILoggingBuilder` proporcionado por la plataforma de registro.</span><span class="sxs-lookup"><span data-stu-id="536a7-217">Call an `ILoggerFactory` or `ILoggingBuilder` extension method provided by the logging framework.</span></span>

<span data-ttu-id="536a7-218">Para más información, vea la documentación de cada proveedor.</span><span class="sxs-lookup"><span data-stu-id="536a7-218">For more information, see each provider's documentation.</span></span> <span data-ttu-id="536a7-219">Microsoft no admite los proveedores de registro de terceros.</span><span class="sxs-lookup"><span data-stu-id="536a7-219">Third-party logging providers aren't supported by Microsoft.</span></span>

## <a name="see-also"></a><span data-ttu-id="536a7-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="536a7-220">See also</span></span>

- <span data-ttu-id="536a7-221">[Registro en .NET](logging.md).</span><span class="sxs-lookup"><span data-stu-id="536a7-221">[Logging in .NET](logging.md).</span></span>
- <span data-ttu-id="536a7-222">[Implementación de un proveedor de registro personalizado en .NET](custom-logging-provider.md).</span><span class="sxs-lookup"><span data-stu-id="536a7-222">[Implement a custom logging provider in .NET](custom-logging-provider.md).</span></span>
- <span data-ttu-id="536a7-223">[Registro de alto rendimiento en .NET](high-performance-logging.md).</span><span class="sxs-lookup"><span data-stu-id="536a7-223">[High-performance logging in .NET](high-performance-logging.md).</span></span>
