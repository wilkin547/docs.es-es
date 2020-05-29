---
ms.openlocfilehash: 52b9caf2d5b3d44c0c6349501dafc371541fdd70
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396350"
---
### <a name="pubternal-apis-removed"></a>API "Pubternal" quitadas

Para mantener mejor la superficie de la API pública de ASP.NET Core, la mayoría de los tipos de los espacios de nombres `*.Internal` (conocidos como API :::no-loc text="\"pubternal\"":::) se han vuelto realmente internos. Los miembros de estos espacios de nombres nunca debían admitirse como API de acceso público. Las API podían dividirse en versiones secundarias y con frecuencia lo hacían. El código que depende de estas API se divide cuando se actualiza a ASP.NET Core 3.0.

Para más información, consulte [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) y [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las API afectadas se marcan con el modificador de acceso `public` y existen en los espacios de nombres `*.Internal`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Las API afectadas se marcan con el modificador de acceso [internal(~/docs/csharp/language-reference/keywords/internal.md) y ya no se pueden usar en el código fuera de ese ensamblado.

#### <a name="reason-for-change"></a>Motivo del cambio

Las instrucciones para estas API de :::no-loc text="\"pubternal\""::: eran las siguientes:

* Podían cambiar sin previo aviso.
* No estaban sujetas a las directivas de .NET para evitar cambios importantes.

La salida de las API `public` (incluso en los espacios de nombres de `*.Internal`) era confusa para los clientes.

#### <a name="recommended-action"></a>Acción recomendada

Deje de usar estas API :::no-loc text="\"pubternal\"":::. Si tiene alguna pregunta sobre API alternativas, abra una incidencia en el repositorio [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).

Por ejemplo, considere el siguiente código de almacenamiento en búfer de solicitudes HTTP en un proyecto ASP.NET Core 2.2. El método de extensión `EnableRewind` existe en el espacio de nombres `Microsoft.AspNetCore.Http.Internal`.

```csharp
HttpContext.Request.EnableRewind();
```

En un proyecto ASP.NET Core 3.0, reemplace la llamada `EnableRewind` por una llamada al método de extensión `EnableBuffering`. La característica de almacenamiento en búfer de solicitudes funciona igual que lo hacía antes. `EnableBuffering` llama a la API `internal` ahora.

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

Todas las API de los espacios de nombres `Microsoft.AspNetCore.*` y `Microsoft.Extensions.*` que tienen un segmento `Internal` en el nombre del espacio de nombres. Por ejemplo:

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
