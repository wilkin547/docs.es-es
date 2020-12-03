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
# <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="af5c3-103">Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="af5c3-103">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="af5c3-104">Kestrel ahora reacciona a los cambios realizados en la sección `Kestrel` de la instancia `IConfiguration` del proyecto (por ejemplo, *appsettings.json*) en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af5c3-104">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="af5c3-105">Para obtener más información sobre cómo configurar Kestrel mediante *appsettings.json*, vea el ejemplo *appsettings.json* en [Configuración de puntos de conexión](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span><span class="sxs-lookup"><span data-stu-id="af5c3-105">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="af5c3-106">Kestrel enlaza, desenlaza y vuelve a enlazar los puntos de conexión según sea necesario para reaccionar a estos cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="af5c3-106">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="af5c3-107">Para obtener información, vea el tema [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span><span class="sxs-lookup"><span data-stu-id="af5c3-107">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="af5c3-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="af5c3-108">Version introduced</span></span>

<span data-ttu-id="af5c3-109">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="af5c3-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="af5c3-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="af5c3-110">Old behavior</span></span>

<span data-ttu-id="af5c3-111">Antes de ASP.NET Core 5.0 (versión preliminar 6), Kestrel no admitía los cambios de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af5c3-111">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="af5c3-112">En ASP.NET Core 5.0 (versión preliminar 6), podía optar por el actual comportamiento predeterminado de reaccionar a los cambios de configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="af5c3-112">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="af5c3-113">Esto exigía enlazar la configuración de Kestrel manualmente:</span><span class="sxs-lookup"><span data-stu-id="af5c3-113">Opting in required binding Kestrel's configuration manually:</span></span>

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

## <a name="new-behavior"></a><span data-ttu-id="af5c3-114">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="af5c3-114">New behavior</span></span>

<span data-ttu-id="af5c3-115">Kestrel reacciona a los cambios de configuración en tiempo de ejecución de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="af5c3-115">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="af5c3-116">Para admitir ese cambio, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> llama a `KestrelServerOptions.Configure(IConfiguration, bool)` con `reloadOnChange: true` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="af5c3-116">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="af5c3-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="af5c3-117">Reason for change</span></span>

<span data-ttu-id="af5c3-118">El cambio se ha realizado para admitir la reconfiguración de puntos de conexión en tiempo de ejecución sin reiniciar completamente el servidor.</span><span class="sxs-lookup"><span data-stu-id="af5c3-118">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="af5c3-119">A diferencia de un reinicio completo del servidor, los puntos de conexión sin cambios no se desenlazan ni de forma temporal.</span><span class="sxs-lookup"><span data-stu-id="af5c3-119">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="af5c3-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="af5c3-120">Recommended action</span></span>

* <span data-ttu-id="af5c3-121">En la mayoría de los escenarios en los que la sección de configuración predeterminada de Kestrel no cambia en tiempo de ejecución, este cambio no tiene ningún impacto ni se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="af5c3-121">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="af5c3-122">En los escenarios en los que la sección de configuración predeterminada de Kestrel cambia en tiempo de ejecución y Kestrel debe reaccionar, este es ahora el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="af5c3-122">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="af5c3-123">En los escenarios en los que la sección de configuración predeterminada de Kestrel cambia en tiempo de ejecución y Kestrel no debe reaccionar, puede optar por no participar de este modo:</span><span class="sxs-lookup"><span data-stu-id="af5c3-123">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

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

<span data-ttu-id="af5c3-124">**Notas:**</span><span class="sxs-lookup"><span data-stu-id="af5c3-124">**Notes:**</span></span>

<span data-ttu-id="af5c3-125">Este cambio no modifica el comportamiento de la sobrecarga `KestrelServerOptions.Configure(IConfiguration)`, que sigue teniendo como valor predeterminado el comportamiento `reloadOnChange: false`.</span><span class="sxs-lookup"><span data-stu-id="af5c3-125">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="af5c3-126">También es importante asegurarse de que el origen de configuración admite la recarga.</span><span class="sxs-lookup"><span data-stu-id="af5c3-126">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="af5c3-127">En los orígenes JSON, la recarga se configura al llamar a `AddJsonFile(path, reloadOnChange: true)`.</span><span class="sxs-lookup"><span data-stu-id="af5c3-127">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="af5c3-128">La recarga ya está configurada de forma predeterminada para *appsettings.json* y *appsettings.{Environment}.json*.</span><span class="sxs-lookup"><span data-stu-id="af5c3-128">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="af5c3-129">API afectadas</span><span class="sxs-lookup"><span data-stu-id="af5c3-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
