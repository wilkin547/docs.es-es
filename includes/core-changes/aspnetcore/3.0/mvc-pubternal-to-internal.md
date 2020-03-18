---
ms.openlocfilehash: 5741e8cdd51e00d5459c4c1032a56682429aab17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901643"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a>MVC: los tipos "pubternal" se han cambiado a internal

En ASP.NET Core 3.0, todos los tipos "pubternal" de MVC se actualizaron para ser `public` en un espacio de nombres compatible o `internal`, según correspondiera.

#### <a name="change-description"></a>Descripción del cambio

In ASP.NET Core, los tipos "pubternal" se declaran como `public` pero residen en un espacio de nombres con un sufijo `.Internal`. Aunque estos tipos son `public`, no tienen ninguna directiva compatible y están sujetos a cambios importantes. Desafortunadamente, el uso accidental de estos tipos es habitual, lo que da lugar a cambios importantes en estos proyectos y limita la capacidad de mantener el marco.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Algunos tipos de MVC eran `public` pero en un espacio de nombres `.Internal`. Estos tipos no tenían ninguna directiva compatible y estaban sujetos a cambios importantes.

#### <a name="new-behavior"></a>Comportamiento nuevo

Todos estos tipos se actualizan para ser `public` en un espacio de nombres compatible o que se marquen como `internal`.

#### <a name="reason-for-change"></a>Motivo del cambio

El uso accidental de los tipos "pubternal" es habitual, lo que da lugar a cambios importantes en estos proyectos y limita la capacidad de mantener el marco.

#### <a name="recommended-action"></a>Acción recomendada

Si usa tipos que se han convertido realmente en `public` y se han movido a un nuevo espacio de nombres compatible, actualice las referencias para que coincidan con los espacios de nombres nuevos.

Si utiliza tipos que se han marcado como `internal`, deberá buscar una alternativa. Los tipos "pubternal" anteriores nunca se admitieron para uso público. Si hay tipos específicos en estos espacios de nombres que son fundamentales para las aplicaciones, registre una incidencia en [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues). Se pueden pensar ideas para hacer los tipos solicitados `public`.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

Este cambio incluye tipos en los espacios de nombres siguientes:

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

<!--

#### Affected APIs

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

-->
