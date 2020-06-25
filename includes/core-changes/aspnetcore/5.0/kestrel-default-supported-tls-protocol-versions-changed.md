---
ms.openlocfilehash: 3244a36808fb687663241e704d08775ea5c96720
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803249"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="e58a3-101">Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas</span><span class="sxs-lookup"><span data-stu-id="e58a3-101">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="e58a3-102">Kestrel ahora usa las versiones del protocolo TLS predeterminadas del sistema en lugar de restringir las conexiones a los protocolos TLS 1.1 y TLS 1.2 como hacía anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e58a3-102">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="e58a3-103">Este cambio permite:</span><span class="sxs-lookup"><span data-stu-id="e58a3-103">This change allows:</span></span>

* <span data-ttu-id="e58a3-104">Usar TLS 1.3 de forma predeterminada en entornos que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="e58a3-104">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="e58a3-105">Usar TLS 1.0 en algunos entornos (como Windows Server 2016 de forma predeterminada), lo que normalmente [no es deseable](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="e58a3-105">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="e58a3-106">Para obtener información, vea el tema [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span><span class="sxs-lookup"><span data-stu-id="e58a3-106">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e58a3-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e58a3-107">Version introduced</span></span>

<span data-ttu-id="e58a3-108">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="e58a3-108">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e58a3-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="e58a3-109">Old behavior</span></span>

<span data-ttu-id="e58a3-110">Kestrel exigía que las conexiones usaran TLS 1.1 o TLS 1.2 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e58a3-110">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e58a3-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="e58a3-111">New behavior</span></span>

<span data-ttu-id="e58a3-112">Kestrel permite que el sistema operativo seleccione el mejor protocolo y que bloquee los protocolos inseguros.</span><span class="sxs-lookup"><span data-stu-id="e58a3-112">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="e58a3-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> ahora tiene como valor predeterminado `SslProtocols.None` en lugar de `SslProtocols.Tls12 | SslProtocols.Tls11`.</span><span class="sxs-lookup"><span data-stu-id="e58a3-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e58a3-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e58a3-114">Reason for change</span></span>

<span data-ttu-id="e58a3-115">El cambio se ha realizado para admitir TLS 1.3 y versiones futuras de TLS de forma predeterminada a medida que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e58a3-115">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e58a3-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e58a3-116">Recommended action</span></span>

<span data-ttu-id="e58a3-117">A menos que la aplicación tenga un motivo concreto para no hacerlo, debe usar los nuevos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e58a3-117">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="e58a3-118">Compruebe que el sistema está configurado para permitir únicamente protocolos seguros.</span><span class="sxs-lookup"><span data-stu-id="e58a3-118">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="e58a3-119">Para deshabilitar protocolos más antiguos, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e58a3-119">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="e58a3-120">Deshabilite los protocolos anteriores, como TLS 1.0, en todo el sistema con las [instrucciones de Windows](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span><span class="sxs-lookup"><span data-stu-id="e58a3-120">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](/dotnet/framework/network-programming/tls#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="e58a3-121">Actualmente está habilitado de forma predeterminada en todas las versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="e58a3-121">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="e58a3-122">Seleccione manualmente los protocolos que quiere admitir en el código como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e58a3-122">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
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
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="e58a3-123">Desafortunadamente, no hay ninguna API para excluir protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="e58a3-123">Unfortunately, there's no API to exclude specific protocols.</span></span>

#### <a name="category"></a><span data-ttu-id="e58a3-124">Categoría</span><span class="sxs-lookup"><span data-stu-id="e58a3-124">Category</span></span>

<span data-ttu-id="e58a3-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e58a3-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e58a3-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e58a3-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
