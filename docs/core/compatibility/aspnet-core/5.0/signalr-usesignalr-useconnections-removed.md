---
title: 'Cambio importante: SignalR: los métodos UseSignalR y UseConnections se han quitado'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado SignalR: los métodos UseSignalR y UseConnections se han quitado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 1b1fce04518e69927cdc1650cc1e19107cc81e3b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760126"
---
# <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="4d407-103">SignalR: los métodos UseSignalR y UseConnections se han quitado</span><span class="sxs-lookup"><span data-stu-id="4d407-103">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="4d407-104">En ASP.NET Core 3.0, SignalR adoptó el enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4d407-104">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="4d407-105">Como parte de ese cambio, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> y algunos métodos relacionados se marcaron como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="4d407-105">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="4d407-106">En ASP.NET Core 5.0, se quitaron los métodos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="4d407-106">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="4d407-107">Para ver la lista completa de métodos, consulte [API afectadas](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="4d407-107">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="4d407-108">Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="4d407-108">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4d407-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4d407-109">Version introduced</span></span>

<span data-ttu-id="4d407-110">5.0 (versión preliminar 3)</span><span class="sxs-lookup"><span data-stu-id="4d407-110">5.0 Preview 3</span></span>

## <a name="old-behavior"></a><span data-ttu-id="4d407-111">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="4d407-111">Old behavior</span></span>

<span data-ttu-id="4d407-112">Los controladores de conexión y concentradores de SignalR podrían registrarse en la canalización de software intermedio mediante los métodos `UseSignalR` o `UseConnections`.</span><span class="sxs-lookup"><span data-stu-id="4d407-112">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="4d407-113">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="4d407-113">New behavior</span></span>

<span data-ttu-id="4d407-114">Los controladores de conexión y concentradores de SignalR deben registrarse en <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mediante los métodos de extensión <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> y <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> de <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span><span class="sxs-lookup"><span data-stu-id="4d407-114">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4d407-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4d407-115">Reason for change</span></span>

<span data-ttu-id="4d407-116">Los métodos anteriores tenían una lógica de enrutamiento personalizado que no interactuaba con otros componentes de enrutamiento en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4d407-116">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="4d407-117">En ASP.NET Core 3.0, se presentó un nuevo sistema de enrutamiento de uso general, llamado enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4d407-117">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="4d407-118">El enrutamiento de puntos de conexión habilitó SignalR para interactuar con otros componentes de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="4d407-118">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="4d407-119">Cambiar a este modelo permite a los usuarios comprender todos los beneficios del enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4d407-119">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="4d407-120">Por consiguiente, se han quitado los métodos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4d407-120">Consequently, the old methods have been removed.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4d407-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4d407-121">Recommended action</span></span>

<span data-ttu-id="4d407-122">Quite el código que llama a `UseSignalR` o `UseConnections` desde el método `Startup.Configure` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d407-122">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="4d407-123">Reemplácelo por llamadas a `MapHub` o `MapConnectionHandler`, respectivamente, en el cuerpo de una llamada a `UseEndpoints`.</span><span class="sxs-lookup"><span data-stu-id="4d407-123">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="4d407-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4d407-124">For example:</span></span>

<span data-ttu-id="4d407-125">**Código anterior:**</span><span class="sxs-lookup"><span data-stu-id="4d407-125">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="4d407-126">**Código nuevo:**</span><span class="sxs-lookup"><span data-stu-id="4d407-126">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="4d407-127">En general, sus llamadas `MapHub` y `MapConnectionHandler` anteriores pueden transferirse directamente desde el cuerpo de `UseSignalR` y `UseConnections` a `UseEndpoints` sin que sean necesarios muchos cambios (o ninguno).</span><span class="sxs-lookup"><span data-stu-id="4d407-127">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4d407-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4d407-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
