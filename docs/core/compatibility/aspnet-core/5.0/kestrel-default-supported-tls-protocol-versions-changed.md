---
title: 'Cambio importante: Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: d7018be7cc778560b7b9c65472d42d7e0fbf623d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760094"
---
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="d2e4a-103">Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas</span><span class="sxs-lookup"><span data-stu-id="d2e4a-103">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="d2e4a-104">Kestrel ahora usa las versiones del protocolo TLS predeterminadas del sistema en lugar de restringir las conexiones a los protocolos TLS 1.1 y TLS 1.2 como hacía anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-104">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="d2e4a-105">Este cambio permite:</span><span class="sxs-lookup"><span data-stu-id="d2e4a-105">This change allows:</span></span>

* <span data-ttu-id="d2e4a-106">Usar TLS 1.3 de forma predeterminada en entornos que lo admiten.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-106">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="d2e4a-107">Usar TLS 1.0 en algunos entornos (como Windows Server 2016 de forma predeterminada), lo que normalmente [no es deseable](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="d2e4a-107">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="d2e4a-108">Para obtener información, vea el tema [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span><span class="sxs-lookup"><span data-stu-id="d2e4a-108">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d2e4a-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d2e4a-109">Version introduced</span></span>

<span data-ttu-id="d2e4a-110">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="d2e4a-110">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="d2e4a-111">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="d2e4a-111">Old behavior</span></span>

<span data-ttu-id="d2e4a-112">Kestrel exigía que las conexiones usaran TLS 1.1 o TLS 1.2 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-112">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="d2e4a-113">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="d2e4a-113">New behavior</span></span>

<span data-ttu-id="d2e4a-114">Kestrel permite que el sistema operativo seleccione el mejor protocolo y que bloquee los protocolos inseguros.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-114">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="d2e4a-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> ahora tiene como valor predeterminado `SslProtocols.None` en lugar de `SslProtocols.Tls12 | SslProtocols.Tls11`.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d2e4a-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d2e4a-116">Reason for change</span></span>

<span data-ttu-id="d2e4a-117">El cambio se ha realizado para admitir TLS 1.3 y versiones futuras de TLS de forma predeterminada a medida que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-117">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d2e4a-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d2e4a-118">Recommended action</span></span>

<span data-ttu-id="d2e4a-119">A menos que la aplicación tenga un motivo concreto para no hacerlo, debe usar los nuevos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-119">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="d2e4a-120">Compruebe que el sistema está configurado para permitir únicamente protocolos seguros.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-120">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="d2e4a-121">Para deshabilitar protocolos más antiguos, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d2e4a-121">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="d2e4a-122">Deshabilite los protocolos anteriores, como TLS 1.0, en todo el sistema con las [instrucciones de Windows](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span><span class="sxs-lookup"><span data-stu-id="d2e4a-122">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="d2e4a-123">Actualmente está habilitado de forma predeterminada en todas las versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-123">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="d2e4a-124">Seleccione manualmente los protocolos que quiere admitir en el código como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d2e4a-124">Manually select which protocols you want to support in code as follows:</span></span>

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

<span data-ttu-id="d2e4a-125">Desafortunadamente, no hay ninguna API para excluir protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="d2e4a-125">Unfortunately, there's no API to exclude specific protocols.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d2e4a-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d2e4a-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
