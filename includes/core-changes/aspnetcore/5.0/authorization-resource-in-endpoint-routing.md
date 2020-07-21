---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441560"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a>Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext

Al usar el enrutamiento de punto de conexión en ASP.NET Core 3.1, el recurso que se usa para la autorización es el punto de conexión. Este enfoque no era suficiente para obtener acceso a los datos de ruta (<xref:Microsoft.AspNetCore.Routing.RouteData>). Anteriormente en MVC, se pasaba un recurso <xref:Microsoft.AspNetCore.Http.HttpContext>, que permite el acceso tanto al punto de conexión (<xref:Microsoft.AspNetCore.Http.Endpoint>) como a los datos de ruta. Este cambio garantiza que el recurso que se pasa a la autorización siempre sea `HttpContext`.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 7)

#### <a name="old-behavior"></a>Comportamiento anterior

Al usar el enrutamiento de punto de conexión y los atributos de middleware de autorización (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) o [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute), el recurso que se pasa a la autorización es el punto de conexión coincidente.

#### <a name="new-behavior"></a>Comportamiento nuevo

El enrutamiento del punto de conexión pasa `HttpContext` a la autorización.

#### <a name="reason-for-change"></a>Motivo del cambio

Puede acceder al punto de conexión desde `HttpContext`. Pero no había ninguna manera de acceder desde el punto de conexión a elementos como los datos de ruta. Se producía una pérdida de funcionalidad en el enrutamiento que no es de punto de conexión.

#### <a name="recommended-action"></a>Acción recomendada

Si la aplicación usa el recurso de punto de conexión, llame a <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> en `HttpContext` para seguir accediendo al punto de conexión.

En ASP.NET Core 5.0 versión preliminar 8 y versiones posteriores, puede revertir al comportamiento anterior con <xref:System.AppContext.SetSwitch%2A>. Por ejemplo:

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
