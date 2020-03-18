---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901711"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a>Autorización: IAllowAnonymous se quitó de AuthorizationFilterContext.Filters

A partir de ASP.NET Core 3.0, MVC no agrega [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) para los atributos [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) que se detectaron en los controladores y métodos de acción. Este cambio se dirige localmente para los derivados de <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, pero es un cambio importante en las implementaciones de <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> y <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter>. Estas implementaciones contenidas en un atributo [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) son una [conocidas](https://stackoverflow.com/a/41348219/608220) y compatibles para lograr la autorización basada en atributos fuertemente tipados cuando se requieren tanto la configuración como la inserción de dependencias.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

<xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> aparecía en la colección [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A). La prueba de la presencia de la interfaz era un enfoque válido para invalidar o deshabilitar el filtro en métodos de controlador individuales.

#### <a name="new-behavior"></a>Comportamiento nuevo

`IAllowAnonymous` ya no aparece en la colección `AuthorizationFilterContext.Filters`. Las implementaciones `IAsyncAuthorizationFilter` que dependen del comportamiento anterior normalmente producen respuestas intermitentes HTTP 401 no autorizadas o HTTP 403 prohibidas.

#### <a name="reason-for-change"></a>Motivo del cambio

Se presentó una nueva estrategia de enrutamiento de puntos de conexión en ASP.NET Core 3.0.

#### <a name="recommended-action"></a>Acción recomendada

Busque `IAllowAnonymous` en los metadatos del punto de conexión. Por ejemplo:

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

Un ejemplo de esta técnica se encuentra en [este método HasAllowAnonymous](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
