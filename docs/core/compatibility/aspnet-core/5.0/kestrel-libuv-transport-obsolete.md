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
# <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="a08ab-103">Kestrel: transporte de libuv marcado como obsoleto</span><span class="sxs-lookup"><span data-stu-id="a08ab-103">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="a08ab-104">Las versiones anteriores de ASP.NET Core usaban Libuv como un detalle de implementación de cómo se realizaba la entrada y salida asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="a08ab-104">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="a08ab-105">En ASP.NET Core 2.0 se desarrolló un transporte alternativo basado en <xref:System.Net.Sockets.Socket>.</span><span class="sxs-lookup"><span data-stu-id="a08ab-105">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="a08ab-106">En ASP.NET Core 2.1, Kestrel pasó a usar el transporte basado en `Socket`de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a08ab-106">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="a08ab-107">La compatibilidad de Libuv se mantuvo por motivos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a08ab-107">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="a08ab-108">En este momento, el uso del transporte basado en `Socket` es mucho más común que el transporte de Libuv.</span><span class="sxs-lookup"><span data-stu-id="a08ab-108">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="a08ab-109">Por lo tanto, la compatibilidad de Libuv se ha marcado como obsoleta en .NET 5.0 y se va a quitar por completo en .NET 6.0.</span><span class="sxs-lookup"><span data-stu-id="a08ab-109">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="a08ab-110">Como parte de este cambio, la compatibilidad de Libuv con las nuevas plataformas de sistema operativo (como Windows ARM64) no se va a agregar en el período de tiempo de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="a08ab-110">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="a08ab-111">Para obtener información sobre los problemas de bloqueo que requieren el uso del transporte de Libuv, vea el problema de GitHub en [dotnet/aspnetcore # 23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="a08ab-111">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a08ab-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a08ab-112">Version introduced</span></span>

<span data-ttu-id="a08ab-113">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="a08ab-113">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a08ab-114">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a08ab-114">Old behavior</span></span>

<span data-ttu-id="a08ab-115">Las API de Libuv no están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="a08ab-115">The Libuv APIs aren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="a08ab-116">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a08ab-116">New behavior</span></span>

<span data-ttu-id="a08ab-117">Las API de Libuv están marcadas como obsoletas.</span><span class="sxs-lookup"><span data-stu-id="a08ab-117">The Libuv APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a08ab-118">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a08ab-118">Reason for change</span></span>

<span data-ttu-id="a08ab-119">El transporte basado en `Socket` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a08ab-119">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="a08ab-120">No hay ningún motivo acuciante para seguir usando el transporte de Libuv.</span><span class="sxs-lookup"><span data-stu-id="a08ab-120">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a08ab-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a08ab-121">Recommended action</span></span>

<span data-ttu-id="a08ab-122">Dejar de usar el [paquete Libuv](https://www.nuget.org/packages/Libuv) y los métodos de extensión.</span><span class="sxs-lookup"><span data-stu-id="a08ab-122">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a08ab-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a08ab-123">Affected APIs</span></span>

- [<span data-ttu-id="a08ab-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="a08ab-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="a08ab-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="a08ab-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="a08ab-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="a08ab-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="a08ab-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="a08ab-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="a08ab-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
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
