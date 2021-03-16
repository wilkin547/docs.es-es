---
title: Registro en .NET
author: IEvangelist
description: Obtenga información sobre cómo usar la plataforma de registro proporcionada por el paquete NuGet Microsoft.Extensions.Logging.
ms.author: dapine
ms.date: 02/19/2021
ms.openlocfilehash: 834331b9e103138012bbe91586d0d5a7c08654ce
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102402215"
---
# <a name="logging-in-net"></a>Registro en .NET

.NET es compatible con una API de registro que funciona con una gran variedad de proveedores de registro integrados y de terceros. En este artículo se muestra cómo usar las API de registro con proveedores integrados. La mayoría de los ejemplos de código que se muestran en este artículo se aplican a cualquier aplicación .NET que use el [host genérico](generic-host.md). En el caso de las aplicaciones que no usan el host genérico, vea [Aplicación de consola que no es de host](#non-host-console-app).

## <a name="create-logs"></a>Creación de registros

Para crear registros, use un objeto <xref:Microsoft.Extensions.Logging.ILogger%601> desde la [inserción de dependencias (DI)](dependency-injection.md).

En el ejemplo siguiente:

- Crea un registrador, `ILogger<Worker>`, que utiliza una *categoría* de registro del nombre completo del tipo `Worker`. La categoría de registro es una cadena que está asociada con cada registro.
- Llama a <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> para realizar el registro en el nivel de `Information`. El *nivel* de registro indica la gravedad del evento registrado.

:::code language="csharp" source="snippets/configuration/worker-service/Worker.cs" range="9-24" highlight="12":::

Los [niveles](#log-level) y las [categorías](#log-category) se explican detalladamente más adelante en este artículo.

## <a name="configure-logging"></a>registro

La configuración de registros suele proporcionarla la sección `Logging` de los archivos *appsettings*.`{Environment}` *.json*. El siguiente archivo *appsettings.Development.json* se genera mediante las plantillas de servicio de trabajo de .NET:

:::code language="json" source="snippets/configuration/worker-service/appsettings.Development.json":::

En el código JSON anterior:

- Se especifican las categorías `"Default"`, `"Microsoft"` y `"Microsoft.Hosting.Lifetime"`.
- La categoría `"Microsoft"` se aplica a todas las categorías que comienzan por `"Microsoft"`.
- La categoría `"Microsoft"` registra en el nivel de registro `Warning` y superiores.
- La categoría `"Microsoft.Hosting.Lifetime"` es más específica que la categoría `"Microsoft"`, por lo que la categoría `"Microsoft.Hosting.Lifetime"` registra en el nivel de registro "Information" y superiores.
- No se especifica un proveedor de registro específico, por lo que `LogLevel` se aplica a todos los proveedores de registro habilitados, excepto [Windows EventLog](logging-providers.md#windows-eventlog).

La propiedad `Logging` puede tener <xref:Microsoft.Extensions.Logging.LogLevel> y registrar propiedades del proveedor de registro. `LogLevel` especifica el [nivel](#log-level) mínimo que se va a registrar para las categorías seleccionadas. En el código JSON anterior, se especifican los niveles de registro `Information` y `Warning`. `LogLevel` indica la gravedad del registro y los valores están entre 0 y 6:

`Trace` = 0, `Debug` = 1, `Information` = 2, `Warning` = 3, `Error` = 4, `Critical` = 5 y `None` = 6.

Cuando se especifica `LogLevel`, el registro está habilitado para los mensajes tanto en el nivel especificado como en los superiores. En el código JSON anterior, se registra la categoría `Default` para `Information` y los niveles posteriores. Por ejemplo, se registran los mensajes `Information`, `Warning`, `Error` y `Critical`. Si no se especifica `LogLevel`, el nivel predeterminado del registro es `Information`. Para obtener más información, consulte [Niveles de registro](#log-level).

Una propiedad de proveedor puede especificar una propiedad de `LogLevel`. `LogLevel` en un proveedor especifica los niveles que se van a registrar para ese proveedor, e invalida la configuración de registro que no es de proveedor. Fíjese en el siguiente archivo *appsettings.json*:

:::code language="json" source="snippets/configuration/worker-service/appsettings.Staging.json":::

La configuración de `Logging.{ProviderName}.LogLevel` invalida la configuración de `Logging.LogLevel`. En el código JSON anterior, el nivel de registro predeterminado del proveedor `Debug` se establece en `Information`:

`Logging:Debug:LogLevel:Default:Information`

La configuración anterior especifica el nivel de registro `Information` para cada categoría de `Logging:Debug:`, excepto `Microsoft.Hosting`. Cuando se muestra una categoría específica, esa categoría invalida la categoría predeterminada. En el JSON anterior, las categorías de `Logging:Debug:LogLevel` `"Microsoft.Hosting"` y `"Default"` invalidan la configuración de `Logging:LogLevel`

Se puede especificar el nivel de registro mínimo para:

- Proveedores específicos:  Por ejemplo, `Logging:EventSource:LogLevel:Default:Information`.
- Categorías específicas: Por ejemplo, `Logging:LogLevel:Microsoft:Warning`.
- Todos los proveedores y todas las categorías: `Logging:LogLevel:Default:Warning`

Los registros situados por debajo del nivel mínimo:

- no se pasan proveedor;
- no se registran ni se muestran.

Para suprimir todos los registros, especifique [LogLevel.None](xref:Microsoft.Extensions.Logging.LogLevel). `LogLevel.None` tiene un valor de 6, que es mayor que `LogLevel.Critical` (5).

Si un proveedor admite [ámbitos de registro](#log-scopes), `IncludeScopes` indica si están habilitados. Para obtener más información, consulte [Ámbitos de registro](#log-scopes).

El siguiente archivo *appsettings.json* contiene la configuración de todos los proveedores integrados:

:::code language="json" source="snippets/configuration/worker-service/appsettings.Production.json":::

En el ejemplo anterior:

- Las categorías y los niveles no son valores sugeridos. El objetivo del ejemplo es mostrar todos los proveedores predeterminados.
- La configuración de `Logging.{ProviderName}.LogLevel` invalida la configuración de `Logging.LogLevel`. Por ejemplo, el nivel de `Debug.LogLevel.Default` invalida el nivel de `LogLevel.Default`.
- Se usa cada *alias* de proveedor. Cada proveedor define un *alias* que se puede utilizar en la configuración en lugar del nombre de tipo completo. Los alias de proveedores integrados son los siguientes:
  - Consola
  - Depuración
  - EventSource
  - EventLog
  - AzureAppServicesFile
  - AzureAppServicesBlob
  - ApplicationInsights

### <a name="set-log-level-by-command-line-environment-variables-and-other-configuration"></a>Establecimiento del nivel de registro mediante la línea de comandos, las variables de entorno y otra configuración

El nivel de registro se puede establecer con cualquiera de los [proveedores de configuración](configuration-providers.md). Por ejemplo, puede crear una variable de entorno persistente denominada `Logging:LogLevel:Microsoft` con un valor de `Information`.

## <a name="command-line"></a>[Línea de comandos](#tab/command-line)

Cree y asigne una variable de entorno persistente según el valor de nivel de registro.

```CMD
:: Assigns the env var to the value
setx "Logging__LogLevel__Microsoft" "Information" /M
```

En una *nueva* instancia del **símbolo del sistema**, lea la variable de entorno.

```CMD
:: Prints the env var value
echo %Logging__LogLevel__Microsoft%
```

## <a name="powershell"></a>[PowerShell](#tab/powershell)

Cree y asigne una variable de entorno persistente según el valor de nivel de registro.

```powershell
# Assigns the env var to the value
[System.Environment]::SetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Information", "Machine")
```

En una *nueva* instancia de **PowerShell**, lea la variable de entorno.

```powershell
# Prints the env var value
[System.Environment]::GetEnvironmentVariable(
    "Logging__LogLevel__Microsoft", "Machine")
```

## <a name="bash"></a>[Bash](#tab/bash)

Cree y asigne una variable de entorno persistente según el valor de nivel de registro.

```Bash
# Assigns the env var to the value, persists it across sessions
echo export Logging__LogLevel__Microsoft="Information" >> ~/.bashrc && source ~/.bashrc
```

Para leer la variable de entorno.

```Bash
# Prints the env var value
echo $Logging__LogLevel__Microsoft

# Or use printenv:
# printenv Logging__LogLevel__Microsoft
```

> [!NOTE]
> Al configurar variables de entorno con nombres que contienen `.` (puntos), considere la posibilidad de "Exportar una variable con un punto (.) en ella" en **Stack Exchange** y su [respuesta aceptada](https://unix.stackexchange.com/a/93533) correspondiente.

---

La configuración del entorno anterior se conserva en el entorno. Para probar la configuración cuando se usa una aplicación creada con las plantillas de servicio de trabajo de .NET, use el comando `dotnet run` en el directorio del proyecto después de asignar la variable de entorno.

```dotnetcli
dotnet run
```

> [!TIP]
> Después de establecer una variable de entorno, reinicie su entorno de desarrollo integrado (IDE) para asegurarse de que las variables de entorno recién agregadas están disponibles.

En [Azure App Service](https://azure.microsoft.com/services/app-service/), seleccione **Nueva configuración de la aplicación** en la página **Configuración > Configuración**. Los ajustes de configuración de Azure App Service:

- Se cifran en reposo y se transmiten a través de un canal cifrado.
- Se exponen como variables de entorno.

Para más información sobre cómo establecer los valores de configuración de .NET mediante variables de entorno, vea [Variables de entorno](configuration-providers.md#environment-variable-configuration-provider).

## <a name="how-filtering-rules-are-applied"></a>Cómo se aplican las reglas de filtro

Cuando se crea un objeto <xref:Microsoft.Extensions.Logging.ILogger%601>, el objeto <xref:Microsoft.Extensions.Logging.ILoggerFactory> selecciona una sola regla por proveedor para aplicar a ese registrador. Todos los mensajes escritos por una instancia `ILogger` se filtran según las reglas seleccionadas. De las reglas disponibles, se selecciona la más específica para cada par de categoría y proveedor.

Cuando se crea un `ILogger` para una categoría determinada, se usa el algoritmo siguiente para cada proveedor:

- Se seleccionan todas las reglas que coinciden con el proveedor o su alias. Si no se encuentra ninguna coincidencia, se seleccionan todas las reglas con un proveedor vacío.
- Del resultado del paso anterior, se seleccionan las reglas con el prefijo de categoría coincidente más largo. Si no se encuentra ninguna coincidencia, se seleccionan todas las reglas que no especifican una categoría.
- Si se seleccionan varias reglas, se toma la **última**.
- Si no hay ninguna regla seleccionada, use <xref:Microsoft.Extensions.Logging.LoggingBuilderExtensions.SetMinimumLevel(Microsoft.Extensions.Logging.ILoggingBuilder,Microsoft.Extensions.Logging.LogLevel)?displayProperty=nameWithType> para especificar el nivel de registro mínimo.

## <a name="log-category"></a>Categoría de registro

Cuando se crea un objeto `ILogger`, se especifica una *categoría*. Esa categoría se incluye con cada mensaje de registro creado por esa instancia de `ILogger`. La cadena de categoría es arbitraria, pero la convención es usar el nombre de clase. Por ejemplo, en una aplicación con un servicio definido como el siguiente objeto, la categoría podría ser `"Example.DefaultService"`:

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger<DefaultService> _logger;

        public DefaultService(ILogger<DefaultService> logger) =>
            _logger = logger;

        // ...
    }
}
```

Para especificar explícitamente la categoría, llame a <xref:Microsoft.Extensions.Logging.LoggerFactory.CreateLogger%2A?displayProperty=nameWithType>:

```csharp
namespace Example
{
    public class DefaultService : IService
    {
        private readonly ILogger _logger;

        public DefaultService(ILoggerFactory loggerFactory) =>
            _logger = loggerFactory.CreateLogger("CustomCategory");

        // ...
    }
}
```

La llamada a `CreateLogger` con un nombre fijo puede ser útil cuando se usa en varias clases o tipos, por lo que los eventos se pueden organizar por categoría.

`ILogger<T>` es equivale a llamar a `CreateLogger` con el nombre de tipo completo de `T`.

## <a name="log-level"></a>Nivel de registro

En la tabla siguiente se enumeran los valores de <xref:Microsoft.Extensions.Logging.LogLevel>, el método de extensión `Log{LogLevel}` oportuno y el uso sugerido:

| LogLevel | Valor | Método | Descripción |
|--|--|--|--|
| [Seguimiento](xref:Microsoft.Extensions.Logging.LogLevel) | 0 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogTrace%2A> | Contienen los mensajes más detallados. Estos mensajes pueden contener datos confidenciales de la aplicación. Están deshabilitados de forma predeterminada y ***no*** se deben habilitar en un entorno de producción. |
| [Depurar](xref:Microsoft.Extensions.Logging.LogLevel) | 1 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogDebug%2A> | Para depuración y desarrollo. Debido al elevado volumen, tenga precaución cuando lo use en producción. |
| [Información](xref:Microsoft.Extensions.Logging.LogLevel) | 2 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogInformation%2A> | Realiza el seguimiento del flujo general de la aplicación. Puede tener un valor a largo plazo. |
| [Advertencia](xref:Microsoft.Extensions.Logging.LogLevel) | 3 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogWarning%2A> | Para eventos anómalos o inesperados. Normalmente incluye errores o estados que no provocan un error en la aplicación. |
| [Error](xref:Microsoft.Extensions.Logging.LogLevel) | 4 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogError%2A> | Para los errores y excepciones que no se pueden controlar. Estos mensajes indican un error en la operación o solicitud actual, no un error de toda la aplicación. |
| [Critical)](xref:Microsoft.Extensions.Logging.LogLevel) (Crítico) | 5 | <xref:Microsoft.Extensions.Logging.LoggerExtensions.LogCritical%2A> | Para los errores que requieren atención inmediata. Ejemplos: escenarios de pérdida de datos, espacio en disco insuficiente. |
| [Ninguno](xref:Microsoft.Extensions.Logging.LogLevel) | 6 |  | Especifica que no se debe escribir ningún mensaje. |

En la tabla anterior, `LogLevel` aparece de menor a mayor gravedad.

El primer parámetro del método [Log](xref:Microsoft.Extensions.Logging.LoggerExtensions), <xref:Microsoft.Extensions.Logging.LogLevel>, indica la gravedad del registro. En lugar de llamar a `Log(LogLevel, ...)`, la mayoría de los desarrolladores llaman a los métodos de extensión [Log{LogLevel}](xref:Microsoft.Extensions.Logging.LoggerExtensions). Los métodos de extensión `Log{LogLevel}` [llaman al método Log y especifican el LogLevel](https://github.com/dotnet/extensions/blob/release/3.1/src/Logging/Logging.Abstractions/src/LoggerExtensions.cs). Por ejemplo, las dos llamadas de registro siguientes son funcionalmente equivalentes y generan el mismo registro:

```csharp
public void LogDetails()
{
    var logMessage = "Details for log.";

    _logger.Log(LogLevel.Information, AppLogEvents.Details, logMessage);
    _logger.LogInformation(AppLogEvents.Details, logMessage);
}
```

`AppLogEvents.Details` es el identificador del evento y se representa implícitamente mediante un valor <xref:System.Int32> de constante. `AppLogEvents` es una clase que expone varias constantes de identificador con nombre y se muestra en la sección [Id. de evento del registro](#log-event-id).

El siguiente código crea los registros `Information` y `Warning`:

```csharp
public async Task<T> GetAsync<T>(string id)
{
    _logger.LogInformation(AppLogEvents.Read, "Reading value for {Id}", id);

    var result = await _repository.GetAsync(id);
    if (result is null)
    {
        _logger.LogWarning(AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
    }

    return result;
}
```

En el código anterior, el primer parámetro de `Log{LogLevel}`, `AppLogEvents.Read`, es el [identificador de evento de registro](#log-event-id). El segundo parámetro es una plantilla de mensaje con marcadores de posición para los valores de argumento proporcionados por el resto de parámetros de método. Los parámetros de método se explican detalladamente en la sección de la [plantilla de mensaje](#log-message-template) más adelante en este artículo.

Configure el nivel de registro adecuado y llame a los métodos `Log{LogLevel}` correctos para controlar el volumen de resultados del registro que se escriben en un soporte de almacenamiento determinado. Por ejemplo:

- En producción:
  - El registro en los niveles `Trace` o `Information` genera un gran volumen de mensajes de registro detallados. Para controlar los costos y no superar los límites de almacenamiento de datos, registre los mensajes de nivel `Trace` a `Information` en un almacén de datos de alto volumen y bajo costo. Considere la posibilidad de limitar `Trace` y `Information` a categorías específicas.
  - El registro entre los niveles `Warning` y `Critical` debe generar pocos mensajes de registro.
    - Los costos y los límites de almacenamiento no suelen ser un problema.
    - Cuantos menos registros haya, mayor será la flexibilidad a la hora de elegir el almacén de datos.
- En desarrollo:
  - Establézcalo en `Warning`.
  - Agregue los mensajes `Trace` o`Information` al solucionar problemas. Para limitar la salida, establezca `Trace` o `Information` solo para las categorías que se están investigando.

El siguiente JSON establece `Logging:Console:LogLevel:Microsoft:Information`:

:::code language="json" source="snippets/configuration/worker-service/appsettings.MSFT.json":::

## <a name="log-event-id"></a>Id. de evento del registro

Cada registro puede especificar un *identificador de evento*; <xref:Microsoft.Extensions.Logging.EventId> es una estructura con `Id` y propiedades opcionales `Name` de solo lectura. El código fuente de ejemplo usa la clase `AppLogEvents` para definir los identificadores de evento:

```csharp
internal static class AppLogEvents
{
    internal const int Create = 1000;
    internal const int Read = 1001;
    internal const int Update = 1002;
    internal const int Delete = 1003;

    internal const int Details = 3000;
    internal const int Error = 3001;

    internal const int ReadNotFound = 4000;
    internal const int UpdateNotFound = 4001;

    // ...
}
```

Un id. de evento asocia un conjunto de eventos. Por ejemplo, todos los registros relacionados con la lectura de valores de un repositorio pueden ser `1001`.

El proveedor de registro puede registrar el id. de evento en un campo de identificador, en el mensaje de registro o no almacenarlo. El proveedor de depuración no muestra los identificadores de evento. El proveedor de consola muestra los identificadores de evento entre corchetes después de la categoría:

```console
info: Example.DefaultService.GetAsync[1001]
      Reading value for a1b2c3
warn: Example.DefaultService.GetAsync[4000]
      GetAsync(a1b2c3) not found
```

Algunos proveedores de registro almacenan el identificador de evento en un campo, lo que permite filtrar por el id.

## <a name="log-message-template"></a>Plantilla de mensaje de registro

Cada API de registro usa una plantilla de mensaje. La plantilla de mensaje puede contener marcadores de posición para los que se proporcionan argumentos. Use los nombres de los marcadores de posición, no números. El orden de los marcadores de posición, no sus nombres, determina qué parámetros se usan para proporcionar sus valores. En el código siguiente, los nombres de parámetro están fuera de la secuencia en la plantilla de mensaje:

```csharp
string p1 = "param1";
string p2 = "param2";
_logger.LogInformation("Parameter values: {p2}, {p1}", p1, p2);
```

El código anterior crea un mensaje de registro con los valores de parámetro en secuencia:

```text
Parameter values: param1, param2
```

Este enfoque permite a los proveedores de registro implementar [registro semántico o estructurado](https://github.com/NLog/NLog/wiki/How-to-use-structured-logging). Los propios argumentos se pasan al sistema de registro, no solo a la plantilla de mensaje con formato. Esto permite a los proveedores de registro almacenar los valores de parámetro como campos. Observe el siguiente método de registrador:

```csharp
_logger.LogInformation("Getting item {Id} at {RunTime}", id, DateTime.Now);
```

Por ejemplo, al registrar en Azure Table Storage:

- Cada entidad de Azure Table puede tener propiedades `ID` y `RunTime`.
- Las tablas con propiedades simplifican las consultas en los datos registrados. Por ejemplo, una consulta puede buscar todos los registros dentro de un intervalo `RunTime` determinado sin necesidad de analizar el tiempo de espera del mensaje de texto.

## <a name="log-exceptions"></a>Registro de excepciones

Los métodos de registrador tienen sobrecargas que toman un parámetro de excepción:

```csharp
public void Test(string id)
{
    try
    {
        if (id == "none")
        {
            throw new Exception("Default Id detected.");
        }
    }
    catch (Exception ex)
    {
        _logger.LogWarning(
            AppLogEvents.Error, ex,
            "Failed to process iteration: {Id}", id)
    }
}
```

El registro de excepciones es específico del proveedor.

### <a name="default-log-level"></a>Nivel de registro predeterminado

Si no se establece el nivel de registro predeterminado, su valor será `Information`.

Por ejemplo, observe la siguiente aplicación de servicio de trabajo:

- Creada con las plantillas de trabajo de .NET.
- *appsettings.json* y *appsettings.Development.json* eliminados o con el nombre cambiado.

Con la configuración anterior, al navegar a la página de privacidad o de inicio, se generan muchos mensajes de `Trace`, `Debug` y `Information` con `Microsoft` en el nombre de la categoría.

El código siguiente establece el nivel de registro predeterminado cuando este no se establece en la configuración:

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging => logging.SetMinimumLevel(LogLevel.Warning));
}
```

### <a name="filter-function"></a>Función de filtro

Se invoca una función de filtro para todos los proveedores y las categorías que no tienen reglas asignadas mediante configuración o código:

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
                logging.AddFilter((provider, category, logLevel) =>
                {
                    return provider.Contains("ConsoleLoggerProvider")
                        && (category.Contains("Example") || category.Contains("Microsoft"))
                        && logLevel >= LogLevel.Information;
                }));
}
```

El código anterior muestra los registros de la consola cuando la categoría contiene `Example` o `Microsoft` y el nivel de registro es `Information` o superior.

## <a name="log-scopes"></a>Ámbitos de registro

 Un *ámbito* puede agrupar un conjunto de operaciones lógicas. Esta agrupación se puede utilizar para adjuntar los mismos datos para cada registro que se crea como parte de un conjunto. Por ejemplo, cada registro creado como parte del procesamiento de una transacción puede incluir el identificador de dicha transacción.

Un ámbito:

- es un tipo <xref:System.IDisposable> devuelto por el método <xref:Microsoft.Extensions.Logging.ILogger.BeginScope%2A>;
- se mantiene hasta que se elimina.

Los siguientes proveedores admiten ámbitos:

- `Console`
- [AzureAppServicesFile y AzureAppServicesBlob](xref:Microsoft.Extensions.Logging.AzureAppServices.BatchingLoggerOptions.IncludeScopes)

Use un ámbito encapsulando las llamadas de registrador en un bloque `using`:

```csharp
public async Task<T> GetAsync<T>(string id)
{
    T result;

    using (_logger.BeginScope("using block message"))
    {
        _logger.LogInformation(
            AppLogEvents.Read, "Reading value for {Id}", id);

        var result = await _repository.GetAsync(id);
        if (result is null)
        {
            _logger.LogWarning(
                AppLogEvents.ReadNotFound, "GetAsync({Id}) not found", id);
        }
    }

    return result;
}
```

El JSON siguiente habilita ámbitos para el proveedor de la consola:

:::code language="json" source="snippets/configuration/worker-service/appsettings.IncludeScopes.json" highlight="9":::

El código siguiente permite ámbitos para el proveedor de la consola:

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging((_, logging) =>
                logging.ClearProviders()
                    .AddConsole(options => options.IncludeScopes = true));
}
```

## <a name="non-host-console-app"></a>Aplicación de consola que no es de host

El código de registro para las aplicaciones sin un [host genérico](generic-host.md) es distinto en la forma en que [se agregan los proveedores](logging-providers.md#built-in-logging-providers) y [se crean los registradores](#create-logs). En una aplicación de consola que no sea de host, llame al método de extensión `Add{provider name}` del proveedor al crear un elemento `LoggerFactory`:

```csharp
class Program
{
    static void Main(string[] args)
    {
        using var loggerFactory = LoggerFactory.Create(builder =>
        {
            builder
                .AddFilter("Microsoft", LogLevel.Warning)
                .AddFilter("System", LogLevel.Warning)
                .AddFilter("LoggingConsoleApp.Program", LogLevel.Debug)
                .AddConsole();
        });

        ILogger logger = loggerFactory.CreateLogger<Program>();
        logger.LogInformation("Example log message");
    }
}
```

El objeto `loggerFactory` se usa para crear una instancia de <xref:Microsoft.Extensions.Logging.ILogger>.

## <a name="create-logs-in-main"></a>Creación de registros en Main

El código siguiente registra en `Main` mediante la obtención de una instancia de `ILogger` de inserción de dependencias después de compilar el host:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;
using Microsoft.Extensions.Logging;

class Program
{
    static Task Main(string[] args)
    {
        IHost host = Host.CreateDefaultBuilder(args).Build();

        var logger = host.Services.GetRequiredService<ILogger<Program>>();
        logger.LogInformation("Host created.");

        return host.RunAsync();
    }
}
```

### <a name="no-asynchronous-logger-methods"></a>No hay métodos de registrador asincrónicos

El registro debe ser tan rápido que no merezca la pena el costo de rendimiento del código asincrónico. Si el almacén de datos de registro es lento, no escriba directamente en él. Considere la posibilidad de escribir primero los mensajes de registro en un almacén rápido y, después, moverlos al almacén lento. Por ejemplo, al iniciar sesión en SQL Server, no lo haga directamente en un método `Log`, ya que los métodos `Log` son sincrónicos. En su lugar, agregue sincrónicamente mensajes de registro a una cola en memoria y haga que un trabajo en segundo plano extraiga los mensajes de la cola para realizar el trabajo asincrónico de insertar datos en SQL Server.

## <a name="change-log-levels-in-a-running-app"></a>Cambio de los niveles de registro en una aplicación en ejecución

La API de registro no incluye un escenario que permita cambiar los niveles de registro mientras se ejecuta una aplicación. No obstante, algunos proveedores de configuración pueden volver a cargar la configuración, lo que tiene efecto inmediato en la configuración del registro. Por ejemplo, el [Proveedor de configuración de archivo](configuration-providers.md#file-configuration-provider) vuelve a cargar la configuración de registro de forma predeterminada. Si se cambia la configuración en el código mientras se ejecuta una aplicación, la aplicación puede llamar a [IConfigurationRoot.Reload](xref:Microsoft.Extensions.Configuration.IConfigurationRoot.Reload%2A) para actualizar la configuración de registro de la aplicación.

## <a name="nuget-packages"></a>Paquetes NuGet

Las implementaciones y las interfaces de <xref:Microsoft.Extensions.Logging.ILogger%601> y <xref:Microsoft.Extensions.Logging.ILoggerFactory> se incluyen en el SDK de .NET Core. También están disponibles en los siguientes paquetes NuGet:

- Las interfaces están en [Microsoft.Extensions.Logging.Abstractions](https://www.nuget.org/packages/Microsoft.Extensions.Logging.Abstractions).
- Las implementaciones predeterminadas se encuentran en [Microsoft.Extensions.Logging](https://www.nuget.org/packages/microsoft.extensions.logging).

## <a name="apply-log-filter-rules-in-code"></a>Aplicación de reglas de filtro en el código

El método preferido para establecer las reglas de filtro de registro es mediante la [Configuración](configuration.md).

En el siguiente ejemplo se muestra cómo registrar reglas de filtro en el código:

```csharp
class Program
{
    static Task Main(string[] args) =>
        CreateHostBuilder(args).Build().RunAsync();

    static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureLogging(logging =>
               logging.AddFilter("System", LogLevel.Debug)
                  .AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)
                  .AddFilter<ConsoleLoggerProvider>("Microsoft", LogLevel.Trace));
}
```

`logging.AddFilter("System", LogLevel.Debug)` especifica la categoría `System` y el nivel de registro `Debug`. El filtro se aplica a todos los proveedores porque no se ha configurado un proveedor específico.

`AddFilter<DebugLoggerProvider>("Microsoft", LogLevel.Information)` especifica:

- El proveedor de registro `Debug`.
- Nivel de registro `Information` y superiores.
- Todas las categorías que empiezan con `"Microsoft"`.

## <a name="see-also"></a>Vea también

- [Proveedores de registro en .NET](logging-providers.md)
- [Implementación de un proveedor de registro personalizado en .NET](custom-logging-provider.md)
- [Formato de registro de la consola](console-log-formatter.md)
- [Registro de alto rendimiento en .NET](high-performance-logging.md)
- Los errores de registro deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).
