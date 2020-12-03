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
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas

Kestrel ahora usa las versiones del protocolo TLS predeterminadas del sistema en lugar de restringir las conexiones a los protocolos TLS 1.1 y TLS 1.2 como hacía anteriormente.

Este cambio permite:

* Usar TLS 1.3 de forma predeterminada en entornos que lo admiten.
* Usar TLS 1.0 en algunos entornos (como Windows Server 2016 de forma predeterminada), lo que normalmente [no es deseable](/security/engineering/solving-tls1-problem).

Para obtener información, vea el tema [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 6)

## <a name="old-behavior"></a>Comportamiento anterior

Kestrel exigía que las conexiones usaran TLS 1.1 o TLS 1.2 de forma predeterminada.

## <a name="new-behavior"></a>Comportamiento nuevo

Kestrel permite que el sistema operativo seleccione el mejor protocolo y que bloquee los protocolos inseguros. <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> ahora tiene como valor predeterminado `SslProtocols.None` en lugar de `SslProtocols.Tls12 | SslProtocols.Tls11`.

## <a name="reason-for-change"></a>Motivo del cambio

El cambio se ha realizado para admitir TLS 1.3 y versiones futuras de TLS de forma predeterminada a medida que están disponibles.

## <a name="recommended-action"></a>Acción recomendada

A menos que la aplicación tenga un motivo concreto para no hacerlo, debe usar los nuevos valores predeterminados. Compruebe que el sistema está configurado para permitir únicamente protocolos seguros.

Para deshabilitar protocolos más antiguos, realice una de las siguientes acciones:

* Deshabilite los protocolos anteriores, como TLS 1.0, en todo el sistema con las [instrucciones de Windows](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry). Actualmente está habilitado de forma predeterminada en todas las versiones de Windows.
* Seleccione manualmente los protocolos que quiere admitir en el código como se indica a continuación:

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

Desafortunadamente, no hay ninguna API para excluir protocolos específicos.

## <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
