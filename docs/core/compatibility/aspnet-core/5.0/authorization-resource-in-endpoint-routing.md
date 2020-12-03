---
title: 'Cambio importante: Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 7c5a77cb8999c60a7780b9b4f7ad2a1c79fd8310
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760262"
---
# <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="7236f-103">Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext</span><span class="sxs-lookup"><span data-stu-id="7236f-103">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="7236f-104">Al usar el enrutamiento de punto de conexión en ASP.NET Core 3.1, el recurso que se usa para la autorización es el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7236f-104">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="7236f-105">Este enfoque no era suficiente para obtener acceso a los datos de ruta (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span><span class="sxs-lookup"><span data-stu-id="7236f-105">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="7236f-106">Anteriormente en MVC, se pasaba un recurso <xref:Microsoft.AspNetCore.Http.HttpContext>, que permite el acceso tanto al punto de conexión (<xref:Microsoft.AspNetCore.Http.Endpoint>) como a los datos de ruta.</span><span class="sxs-lookup"><span data-stu-id="7236f-106">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="7236f-107">Este cambio garantiza que el recurso que se pasa a la autorización siempre sea `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="7236f-107">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7236f-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7236f-108">Version introduced</span></span>

<span data-ttu-id="7236f-109">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="7236f-109">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="7236f-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7236f-110">Old behavior</span></span>

<span data-ttu-id="7236f-111">Al usar el enrutamiento de punto de conexión y los atributos de middleware de autorización (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) o [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute), el recurso que se pasa a la autorización es el punto de conexión coincidente.</span><span class="sxs-lookup"><span data-stu-id="7236f-111">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="7236f-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7236f-112">New behavior</span></span>

<span data-ttu-id="7236f-113">El enrutamiento del punto de conexión pasa `HttpContext` a la autorización.</span><span class="sxs-lookup"><span data-stu-id="7236f-113">Endpoint routing passes the `HttpContext` to authorization.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7236f-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7236f-114">Reason for change</span></span>

<span data-ttu-id="7236f-115">Puede acceder al punto de conexión desde `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="7236f-115">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="7236f-116">Pero no había ninguna manera de acceder desde el punto de conexión a elementos como los datos de ruta.</span><span class="sxs-lookup"><span data-stu-id="7236f-116">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="7236f-117">Se producía una pérdida de funcionalidad en el enrutamiento que no es de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7236f-117">There was a loss in functionality from non-endpoint routing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7236f-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7236f-118">Recommended action</span></span>

<span data-ttu-id="7236f-119">Si la aplicación usa el recurso de punto de conexión, llame a <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> en `HttpContext` para seguir accediendo al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7236f-119">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="7236f-120">En ASP.NET Core 5.0 versión preliminar 8 y versiones posteriores, puede revertir al comportamiento anterior con <xref:System.AppContext.SetSwitch%2A>.</span><span class="sxs-lookup"><span data-stu-id="7236f-120">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="7236f-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7236f-121">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

## <a name="affected-apis"></a><span data-ttu-id="7236f-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7236f-122">Affected APIs</span></span>

<span data-ttu-id="7236f-123">None</span><span class="sxs-lookup"><span data-stu-id="7236f-123">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
