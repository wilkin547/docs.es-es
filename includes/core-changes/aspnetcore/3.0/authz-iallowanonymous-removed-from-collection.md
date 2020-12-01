---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032714"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="b1d5f-101">Autorización: IAllowAnonymous se quitó de AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="b1d5f-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="b1d5f-102">A partir de ASP.NET Core 3.0, MVC no agrega [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) para los atributos [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) que se detectaron en los controladores y métodos de acción.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="b1d5f-103">Este cambio se dirige localmente para los derivados de <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, pero es un cambio importante en las implementaciones de <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> y <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="b1d5f-104">Estas implementaciones contenidas en un atributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) son una [conocidas](https://stackoverflow.com/a/41348219/608220) y compatibles para lograr la autorización basada en atributos fuertemente tipados cuando se requieren tanto la configuración como la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b1d5f-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b1d5f-105">Version introduced</span></span>

<span data-ttu-id="b1d5f-106">3.0</span><span class="sxs-lookup"><span data-stu-id="b1d5f-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b1d5f-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b1d5f-107">Old behavior</span></span>

<span data-ttu-id="b1d5f-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> aparecía en la colección [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A).</span><span class="sxs-lookup"><span data-stu-id="b1d5f-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="b1d5f-109">La prueba de la presencia de la interfaz era un enfoque válido para invalidar o deshabilitar el filtro en métodos de controlador individuales.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b1d5f-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b1d5f-110">New behavior</span></span>

<span data-ttu-id="b1d5f-111">`IAllowAnonymous` ya no aparece en la colección `AuthorizationFilterContext.Filters`.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="b1d5f-112">Las implementaciones `IAsyncAuthorizationFilter` que dependen del comportamiento anterior normalmente producen respuestas intermitentes HTTP 401 no autorizadas o HTTP 403 prohibidas.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b1d5f-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b1d5f-113">Reason for change</span></span>

<span data-ttu-id="b1d5f-114">Se presentó una nueva estrategia de enrutamiento de puntos de conexión en ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b1d5f-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b1d5f-115">Recommended action</span></span>

<span data-ttu-id="b1d5f-116">Busque `IAllowAnonymous` en los metadatos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b1d5f-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="b1d5f-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1d5f-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="b1d5f-118">Un ejemplo de esta técnica se encuentra en [este método HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span><span class="sxs-lookup"><span data-stu-id="b1d5f-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="b1d5f-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="b1d5f-119">Category</span></span>

<span data-ttu-id="b1d5f-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b1d5f-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b1d5f-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b1d5f-121">Affected APIs</span></span>

<span data-ttu-id="b1d5f-122">None</span><span class="sxs-lookup"><span data-stu-id="b1d5f-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
