---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291643"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="1344f-101">SignalR: los métodos UseSignalR y UseConnections se han quitado</span><span class="sxs-lookup"><span data-stu-id="1344f-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="1344f-102">En ASP.NET Core 3.0, SignalR adoptó el enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="1344f-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="1344f-103">Como parte de ese cambio, <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A> y algunos métodos relacionados se marcaron como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="1344f-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="1344f-104">En ASP.NET Core 5.0, se quitaron los métodos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="1344f-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="1344f-105">Para ver la lista completa de métodos, consulte [API afectadas](#affected-apis).</span><span class="sxs-lookup"><span data-stu-id="1344f-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="1344f-106">Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span><span class="sxs-lookup"><span data-stu-id="1344f-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1344f-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1344f-107">Version introduced</span></span>

<span data-ttu-id="1344f-108">5.0 (versión preliminar 3)</span><span class="sxs-lookup"><span data-stu-id="1344f-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1344f-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="1344f-109">Old behavior</span></span>

<span data-ttu-id="1344f-110">Los controladores de conexión y concentradores de SignalR podrían registrarse en la canalización de software intermedio mediante los métodos `UseSignalR` o `UseConnections`.</span><span class="sxs-lookup"><span data-stu-id="1344f-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1344f-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="1344f-111">New behavior</span></span>

<span data-ttu-id="1344f-112">Los controladores de conexión y concentradores de SignalR deben registrarse en <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> mediante los métodos de extensión <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> y <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> de <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span><span class="sxs-lookup"><span data-stu-id="1344f-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1344f-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="1344f-113">Reason for change</span></span>

<span data-ttu-id="1344f-114">Los métodos anteriores tenían una lógica de enrutamiento personalizado que no interactuaba con otros componentes de enrutamiento en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1344f-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="1344f-115">En ASP.NET Core 3.0, se presentó un nuevo sistema de enrutamiento de uso general, llamado enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="1344f-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="1344f-116">El enrutamiento de puntos de conexión habilitó SignalR para interactuar con otros componentes de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1344f-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="1344f-117">Cambiar a este modelo permite a los usuarios comprender todos los beneficios del enrutamiento de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="1344f-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="1344f-118">Por consiguiente, se han quitado los métodos anteriores.</span><span class="sxs-lookup"><span data-stu-id="1344f-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1344f-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1344f-119">Recommended action</span></span>

<span data-ttu-id="1344f-120">Quite el código que llama a `UseSignalR` o `UseConnections` desde el método `Startup.Configure` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1344f-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="1344f-121">Reemplácelo por llamadas a `MapHub` o `MapConnectionHandler`, respectivamente, en el cuerpo de una llamada a `UseEndpoints`.</span><span class="sxs-lookup"><span data-stu-id="1344f-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="1344f-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1344f-122">For example:</span></span>

<span data-ttu-id="1344f-123">**Código anterior:**</span><span class="sxs-lookup"><span data-stu-id="1344f-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="1344f-124">**Código nuevo:**</span><span class="sxs-lookup"><span data-stu-id="1344f-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="1344f-125">En general, sus llamadas `MapHub` y `MapConnectionHandler` anteriores pueden transferirse directamente desde el cuerpo de `UseSignalR` y `UseConnections` a `UseEndpoints` sin que sean necesarios muchos cambios (o ninguno).</span><span class="sxs-lookup"><span data-stu-id="1344f-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="1344f-126">Categoría</span><span class="sxs-lookup"><span data-stu-id="1344f-126">Category</span></span>

<span data-ttu-id="1344f-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1344f-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1344f-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1344f-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
