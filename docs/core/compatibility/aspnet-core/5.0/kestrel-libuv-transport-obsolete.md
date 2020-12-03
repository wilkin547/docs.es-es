---
title: 'Cambio importante: Kestrel: transporte de libuv marcado como obsoleto'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Kestrel: transporte de libuv marcado como obsoleto'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f66b9b646671e07957e6d30a95333d392eb29617
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760184"
---
# <a name="kestrel-libuv-transport-marked-as-obsolete"></a>Kestrel: transporte de libuv marcado como obsoleto

Las versiones anteriores de ASP.NET Core usaban Libuv como un detalle de implementación de cómo se realizaba la entrada y salida asincrónicas. En ASP.NET Core 2.0 se desarrolló un transporte alternativo basado en <xref:System.Net.Sockets.Socket>. En ASP.NET Core 2.1, Kestrel pasó a usar el transporte basado en `Socket`de forma predeterminada. La compatibilidad de Libuv se mantuvo por motivos de compatibilidad.

En este momento, el uso del transporte basado en `Socket` es mucho más común que el transporte de Libuv. Por lo tanto, la compatibilidad de Libuv se ha marcado como obsoleta en .NET 5.0 y se va a quitar por completo en .NET 6.0.

Como parte de este cambio, la compatibilidad de Libuv con las nuevas plataformas de sistema operativo (como Windows ARM64) no se va a agregar en el período de tiempo de .NET 5.0.

Para obtener información sobre los problemas de bloqueo que requieren el uso del transporte de Libuv, vea el problema de GitHub en [dotnet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

## <a name="old-behavior"></a>Comportamiento anterior

Las API de Libuv no están marcadas como obsoletas.

## <a name="new-behavior"></a>Comportamiento nuevo

Las API de Libuv están marcadas como obsoletas.

## <a name="reason-for-change"></a>Motivo del cambio

El transporte basado en `Socket` es el valor predeterminado. No hay ningún motivo acuciante para seguir usando el transporte de Libuv.

## <a name="recommended-action"></a>Acción recomendada

Dejar de usar el [paquete Libuv](https://www.nuget.org/packages/Libuv) y los métodos de extensión.

## <a name="affected-apis"></a>API afectadas

- [WebHostBuilderLibuvExtensions](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [WebHostBuilderLibuvExtensions.UseLibuv](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
