---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441560"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="9d0f1-101">Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext</span><span class="sxs-lookup"><span data-stu-id="9d0f1-101">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="9d0f1-102">Al usar el enrutamiento de punto de conexión en ASP.NET Core 3.1, el recurso que se usa para la autorización es el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-102">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="9d0f1-103">Este enfoque no era suficiente para obtener acceso a los datos de ruta (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span><span class="sxs-lookup"><span data-stu-id="9d0f1-103">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="9d0f1-104">Anteriormente en MVC, se pasaba un recurso <xref:Microsoft.AspNetCore.Http.HttpContext>, que permite el acceso tanto al punto de conexión (<xref:Microsoft.AspNetCore.Http.Endpoint>) como a los datos de ruta.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-104">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="9d0f1-105">Este cambio garantiza que el recurso que se pasa a la autorización siempre sea `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-105">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9d0f1-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9d0f1-106">Version introduced</span></span>

<span data-ttu-id="9d0f1-107">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="9d0f1-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9d0f1-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="9d0f1-108">Old behavior</span></span>

<span data-ttu-id="9d0f1-109">Al usar el enrutamiento de punto de conexión y los atributos de middleware de autorización (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) o [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute), el recurso que se pasa a la autorización es el punto de conexión coincidente.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-109">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9d0f1-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="9d0f1-110">New behavior</span></span>

<span data-ttu-id="9d0f1-111">El enrutamiento del punto de conexión pasa `HttpContext` a la autorización.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-111">Endpoint routing passes the `HttpContext` to authorization.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9d0f1-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="9d0f1-112">Reason for change</span></span>

<span data-ttu-id="9d0f1-113">Puede acceder al punto de conexión desde `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-113">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="9d0f1-114">Pero no había ninguna manera de acceder desde el punto de conexión a elementos como los datos de ruta.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-114">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="9d0f1-115">Se producía una pérdida de funcionalidad en el enrutamiento que no es de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-115">There was a loss in functionality from non-endpoint routing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9d0f1-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9d0f1-116">Recommended action</span></span>

<span data-ttu-id="9d0f1-117">Si la aplicación usa el recurso de punto de conexión, llame a <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> en `HttpContext` para seguir accediendo al punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-117">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="9d0f1-118">En ASP.NET Core 5.0 versión preliminar 8 y versiones posteriores, puede revertir al comportamiento anterior con <xref:System.AppContext.SetSwitch%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d0f1-118">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="9d0f1-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d0f1-119">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a><span data-ttu-id="9d0f1-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="9d0f1-120">Category</span></span>

<span data-ttu-id="9d0f1-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9d0f1-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9d0f1-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9d0f1-122">Affected APIs</span></span>

<span data-ttu-id="9d0f1-123">None</span><span class="sxs-lookup"><span data-stu-id="9d0f1-123">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
