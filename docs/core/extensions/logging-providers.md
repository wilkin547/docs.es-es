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
# <a name="logging-providers-in-net"></a>Proveedores de registro en .NET

Los proveedores de registro conservan los registros, excepto el proveedor `Console`, que solo muestra los registros como salida estándar. Por ejemplo, el proveedor de Azure Application Insights almacena los registros en Azure Application Insights. Se pueden habilitar varios proveedores.

Las plantillas de aplicación predeterminadas de .NET Worker:

- usan el [host genérico](generic-host.md);
- llaman a <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder%2A>, que agrega los siguientes proveedores de registro:
  - [Consola](#console)
  - [Depurar](#debug)
  - [EventSource](#event-source)
  - [EventLog](#windows-eventlog): Solo Windows

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

En el código anterior se muestra la clase `Program` creada con las plantillas de aplicación de .NET Worker. En las siguientes secciones se proporcionan ejemplos basados en las plantillas de aplicación de .NET Worker, que usan el host genérico.

Para invalidar el conjunto predeterminado de proveedores de registro agregados por `Host.CreateDefaultBuilder`, llame a `ClearProviders` y agregue los proveedores de registro que quiera. Por ejemplo, el código siguiente:

- Llama a <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.ClearProviders%2A> para quitar todas las instancias de <xref:Microsoft.Extensions.Logging.ILoggerProvider> del generador.
- Agrega el proveedor de registro [Console](#console).

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureLogging(logging =>
        {
            logging.ClearProviders();
            logging.AddConsole();
        });
```

Para otros proveedores, vea:

- [Proveedores de registro integrados](#built-in-logging-providers)
- [Proveedores de registro de terceros](#third-party-logging-providers)

## <a name="configure-a-service-that-depends-on-ilogger"></a>Configuración de un servicio que dependa de ILogger

Para configurar un servicio que dependa de `ILogger<T>`, use la inserción de constructores o proporcione un método Factory. Usar un Factory Method es la opción recomendada si no tiene otra alternativa. Por ejemplo, tomemos un servicio que necesita una instancia de `ILogger<T>` proporcionada por DI:

```csharp
.ConfigureServices(services =>
    services.AddSingleton<IExampleService>(container =>
        new DefaultExampleService
        {
            Logger = container.GetRequiredService<ILogger<IExampleService>>()
        }));
```

El código anterior es un elemento [Func<IServiceProvider, IExampleService>](/dotnet/api/system.func-2) que se ejecuta la primera vez que el contenedor de DI necesita crear una instancia de `IExampleService`. Puede acceder a cualquiera de los servicios registrados de esta forma.

## <a name="built-in-logging-providers"></a>Proveedores de registro integrados

Las extensiones de Microsoft incluyen los siguientes proveedores de registro como parte de las bibliotecas en tiempo de ejecución:

- [Consola](#console)
- [Depurar](#debug)
- [EventSource](#event-source)
- [EventLog](#windows-eventlog)

Microsoft envía los siguientes proveedores de registro, pero no como parte de las bibliotecas en tiempo de ejecución. Deben instalarse como paquetes NuGet adicionales.

- [AzureAppServicesFile y AzureAppServicesBlob](#azure-app-service)
- [ApplicationInsights](#azure-application-insights)

### <a name="console"></a>Consola

El proveedor `Console` registra la salida en la consola.

### <a name="debug"></a>Depuración

El proveedor `Debug` escribe la salida del registro mediante la clase [System.Diagnostics.Debug](/dotnet/api/system.diagnostics.debug). Las llamadas a `System.Diagnostics.Debug.WriteLine` escriben en el proveedor `Debug`.

En Linux, la ubicación del registro del proveedor `Debug` depende de la distribución y puede ser una de las siguientes:

- */var/log/message*
- */var/log/syslog*

### <a name="event-source"></a>Origen de eventos

El proveedor `EventSource` escribe en un origen de eventos multiplataforma con el nombre `Microsoft-Extensions-Logging`. En Windows, el proveedor utiliza [ETW](/windows/win32/etw/event-tracing-portal).

#### <a name="dotnet-trace-tooling"></a>herramienta de seguimiento de dotnet

La herramienta de [seguimiento de dotnet](../diagnostics/dotnet-trace.md) es una herramienta global de CLI multiplataforma que permite la recopilación de seguimientos de .NET Core de un proceso en ejecución. La herramienta recopila datos del proveedor <xref:Microsoft.Extensions.Logging.EventSource> mediante un <xref:Microsoft.Extensions.Logging.EventSource.LoggingEventSource>.

Vea [dotnet-trace](../diagnostics/dotnet-trace.md) para obtener instrucciones de instalación. Para ver un tutorial de diagnóstico con `dotnet-trace`, consulte [Depuración del uso intensivo de la CPU en .NET Core](../diagnostics/debug-highcpu.md).

### <a name="windows-eventlog"></a>Registro de eventos de Windows

El proveedor `EventLog` envía la salida del registro al Registro de eventos de Windows. A diferencia de otros proveedores, el proveedor `EventLog` ***no*** hereda la configuración de no proveedor predeterminada. Si no se especifican valores de registro de `EventLog`, el valor predeterminado será `LogLevel.Warning`.

Para registrar eventos inferiores a <xref:Microsoft.Extensions.Logging.LogLevel.Warning?displayProperty=nameWithType>, establezca el nivel de registro de forma explícita. En el ejemplo siguiente se establece el nivel de registro predeterminado del registro de eventos en <xref:Microsoft.Extensions.Logging.LogLevel.Information?displayProperty=nameWithType>:

```json
"Logging": {
  "EventLog": {
    "LogLevel": {
      "Default": "Information"
    }
  }
}
```

Las [sobrecargas de AddEventLog](xref:Microsoft.Extensions.Logging.EventLoggerFactoryExtensions) pueden pasar <xref:Microsoft.Extensions.Logging.EventLog.EventLogSettings>. Si es `null` o no se especifica, se usa la siguiente configuración predeterminada:

- `LogName`: "Application"
- `SourceName`: ".NET Runtime"
- `MachineName`: se usa el nombre del equipo local.

En el código siguiente se cambia el valor predeterminado de `SourceName` (`".NET Runtime"`) por `CustomLogs`:

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

### <a name="azure-app-service"></a>Azure App Service

El paquete de proveedor [Microsoft.Extensions.Logging.AzureAppServices](https://www.nuget.org/packages/Microsoft.Extensions.Logging.AzureAppServices) escribe los registros en archivos de texto en el sistema de archivos de una aplicación de Azure App Service y en [Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet#what-is-blob-storage) en una cuenta de Azure Storage.

El paquete de proveedor no se incluye en las bibliotecas en tiempo de ejecución. Para usar el proveedor, agregue el paquete del proveedor al proyecto.

Para configurar las opciones de proveedor, use <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureFileLoggerOptions> y <xref:Microsoft.Extensions.Logging.AzureAppServices.AzureBlobLoggerOptions>, tal y como se muestra en el ejemplo siguiente:

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

Cuando se implementa en Azure App Service, la aplicación usa la configuración de la sección [Registros de App Service](/azure/app-service/web-sites-enable-diagnostic-log/#enable-application-logging-windows) de la página **App Service** de Azure Portal. Cuando se actualiza la configuración siguiente, los cambios se aplican de inmediato sin necesidad de reiniciar ni de volver a implementar la aplicación.

- **Registro de la aplicación (sistema de archivos)**
- **Registro de la aplicación (blob)**

La ubicación predeterminada de los archivos de registro es la carpeta *D:\\home\\LogFiles\\Application* y el nombre de archivo predeterminado es *diagnostics-aaaammdd.txt*. El límite de tamaño de archivo predeterminado es 10 MB, y el número máximo predeterminado de archivos que se conservan es 2. El nombre de blob predeterminado es *{nombre-de-la-aplicación}{marca de tiempo}/aaaa/mm/dd/hh/{guid}-applicationLog.txt*.

El proveedor solo realiza registros cuando el proyecto se ejecuta en el entorno de Azure.

#### <a name="azure-log-streaming"></a>Secuencias de registro de Azure

El streaming de registro de Azure permiten ver la actividad de registro en tiempo real desde:

- El servidor de aplicaciones
- El servidor web
- Error del seguimiento de solicitudes

Para configurar las secuencias de registro de Azure:

- Desplácese a la página **Registros de App Service** desde la página del portal de la aplicación.
- Establezca **Registro de la aplicación (sistema de archivos)** en **Activado**.
- Elija el **Nivel** de registro. Esta configuración solo se aplica al streaming de registro de Azure.

Desplácese a la página **Secuencia de registro** para ver los registros. Los mensajes que se registran lo hacen con la interfaz `ILogger`.

### <a name="azure-application-insights"></a>Azure Application Insights

El paquete de proveedor [Microsoft.Extensions.Logging.ApplicationInsights](https://www.nuget.org/packages/Microsoft.Extensions.Logging.ApplicationInsights) escribe los registros en [Azure Application Insights](/azure/azure-monitor/app/cloudservices). Application Insights es un servicio que supervisa una aplicación web y proporciona herramientas para consultar y analizar los datos de telemetría. Si usa este proveedor, puede consultar y analizar los registros mediante las herramientas de Application Insights.

Para obtener más información, vea los siguientes recursos:

- [Información general de Application Insights](/azure/application-insights/app-insights-overview)
- [ApplicationInsightsLoggerProvider para los registros de .NET Core ILogger](/azure/azure-monitor/app/ilogger): comience aquí si quiere implementar el proveedor de registro sin el resto de la telemetría de Application Insights.
- [Adaptadores de registro de Application Insights](/azure/azure-monitor/app/asp-net-trace-logs)
- [Instalación, configuración e inicialización del SDK de Application Insights](/learn/modules/instrument-web-app-code-with-application-insights): tutorial interactivo en el sitio de Microsoft Learn.

## <a name="third-party-logging-providers"></a>Proveedores de registro de terceros

Estas son algunas plataformas de registro de terceros que funcionan con las distintas cargas de trabajo de .NET:

- [elmah.io](https://elmah.io) ([repositorio de GitHub](https://github.com/elmahio/Elmah.Io.Extensions.Logging))
- [Gelf](https://docs.graylog.org/en/2.3/pages/gelf.html) ([repositorio de GitHub](https://github.com/mattwcole/gelf-extensions-logging))
- [JSNLog](http://jsnlog.com) ([repositorio de GitHub](https://github.com/mperdeck/jsnlog))
- [KissLog.net](https://kisslog.net) ([repositorio de GitHub](https://github.com/catalingavan/KissLog-net))
- [Log4Net](https://logging.apache.org/log4net) ([repositorio de GitHub](https://github.com/apache/logging-log4net))
- [Loggr](https://loggr.net) ([repositorio de GitHub](https://github.com/imobile3/Loggr.Extensions.Logging))
- [NLog](https://nlog-project.org) ([repositorio de GitHub](https://github.com/NLog/NLog.Extensions.Logging))
- [NReco.Logging](https://github.com/nreco/logging/blob/master/README.md) ([repositorio de GitHub](https://github.com/nreco/logging))
- [Sentry](https://sentry.io/welcome) ([repositorio de GitHub](https://github.com/getsentry/sentry-dotnet))
- [Serilog](https://serilog.net) ([repositorio de GitHub](https://github.com/serilog/serilog-sinks-console))
- [Stackdriver](https://cloud.google.com/dotnet/docs/stackdriver#logging) ([repositorio de GitHub](https://github.com/googleapis/google-cloud-dotnet))

Algunas plataformas de terceros pueden realizar [registro semántico, también conocido como registro estructurado](https://softwareengineering.stackexchange.com/questions/312197/benefits-of-structured-logging-vs-basic-logging).

El uso de una plataforma de terceros es similar al uso de uno de los proveedores integrados:

1. Agregue un paquete NuGet al proyecto.
1. Llame a un método de extensión `ILoggerFactory` o `ILoggingBuilder` proporcionado por la plataforma de registro.

Para más información, vea la documentación de cada proveedor. Microsoft no admite los proveedores de registro de terceros.

## <a name="see-also"></a>Vea también

- [Registro en .NET](logging.md).
- [Implementación de un proveedor de registro personalizado en .NET](custom-logging-provider.md).
- [Registro de alto rendimiento en .NET](high-performance-logging.md).
