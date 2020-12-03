---
title: 'Cambio importante: Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 2e879f020dd108baa14fa8ff67dee7b948209faf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760097"
---
# <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a>Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada

Kestrel ahora reacciona a los cambios realizados en la sección `Kestrel` de la instancia `IConfiguration` del proyecto (por ejemplo, *appsettings.json*) en tiempo de ejecución. Para obtener más información sobre cómo configurar Kestrel mediante *appsettings.json*, vea el ejemplo *appsettings.json* en [Configuración de puntos de conexión](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).

Kestrel enlaza, desenlaza y vuelve a enlazar los puntos de conexión según sea necesario para reaccionar a estos cambios de configuración.

Para obtener información, vea el tema [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 7)

## <a name="old-behavior"></a>Comportamiento anterior

Antes de ASP.NET Core 5.0 (versión preliminar 6), Kestrel no admitía los cambios de configuración en tiempo de ejecución.

En ASP.NET Core 5.0 (versión preliminar 6), podía optar por el actual comportamiento predeterminado de reaccionar a los cambios de configuración en tiempo de ejecución. Esto exigía enlazar la configuración de Kestrel manualmente:

```csharp
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.Hosting;

public class Program
{
    public static void Main(string[] args) =>
        CreateHostBuilder(args).Build().Run();

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

## <a name="new-behavior"></a>Comportamiento nuevo

Kestrel reacciona a los cambios de configuración en tiempo de ejecución de forma predeterminada. Para admitir ese cambio, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> llama a `KestrelServerOptions.Configure(IConfiguration, bool)` con `reloadOnChange: true` de forma predeterminada.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio se ha realizado para admitir la reconfiguración de puntos de conexión en tiempo de ejecución sin reiniciar completamente el servidor. A diferencia de un reinicio completo del servidor, los puntos de conexión sin cambios no se desenlazan ni de forma temporal.

## <a name="recommended-action"></a>Acción recomendada

* En la mayoría de los escenarios en los que la sección de configuración predeterminada de Kestrel no cambia en tiempo de ejecución, este cambio no tiene ningún impacto ni se requiere ninguna acción.
* En los escenarios en los que la sección de configuración predeterminada de Kestrel cambia en tiempo de ejecución y Kestrel debe reaccionar, este es ahora el comportamiento predeterminado.
* En los escenarios en los que la sección de configuración predeterminada de Kestrel cambia en tiempo de ejecución y Kestrel no debe reaccionar, puede optar por no participar de este modo:

    ```csharp
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

**Notas:**

Este cambio no modifica el comportamiento de la sobrecarga `KestrelServerOptions.Configure(IConfiguration)`, que sigue teniendo como valor predeterminado el comportamiento `reloadOnChange: false`.

También es importante asegurarse de que el origen de configuración admite la recarga. En los orígenes JSON, la recarga se configura al llamar a `AddJsonFile(path, reloadOnChange: true)`. La recarga ya está configurada de forma predeterminada para *appsettings.json* y *appsettings.{Environment}.json*.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
