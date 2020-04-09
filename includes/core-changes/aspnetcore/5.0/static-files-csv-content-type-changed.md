---
ms.openlocfilehash: 8e077d5cde6e824af5aac3742308593f1d91dd92
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391187"
---
### <a name="static-files-csv-content-type-changed-to-standards-compliant"></a>Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares

En ASP.NET Core 5.0, el valor de encabezado de respuesta `Content-Type` predeterminado que usa el [Middleware de archivo estático](/aspnet/core/fundamentals/static-files) para archivos *.csv* ha cambiado al valor `text/csv` compatible con los estándares.

Para obtener información sobre esta incidencia, vea [dotnet/aspnetcore#17385](https://github.com/dotnet/AspNetCore/issues/17385).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 1)

#### <a name="old-behavior"></a>Comportamiento anterior

Se usó el valor de encabezado `Content-Type` `application/octet-stream`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Se usa el valor de encabezado `Content-Type` `text/csv`.

#### <a name="reason-for-change"></a>Motivo del cambio

Cumplimiento con el estándar [RFC 7111](https://tools.ietf.org/html/rfc7111#section-5.1).

#### <a name="recommended-action"></a>Acción recomendada

Si este cambio afecta a la aplicación, se puede personalizar la extensión del archivo a una asignación de tipo MIME. Para revertir al tipo MIME `application/octet-stream`, modifique la llamada de método <xref:Microsoft.AspNetCore.Builder.StaticFileExtensions.UseStaticFiles%2A> en `Startup.Configure`. Por ejemplo:

```csharp
var provider = new FileExtensionContentTypeProvider();
provider.Mappings[".csv"] = MediaTypeNames.Application.Octet;

app.UseStaticFiles(new StaticFileOptions
{
    ContentTypeProvider = provider
});
```

Para obtener más información sobre la personalización de la asignación, vea [FileExtensionContentTypeProvider](/aspnet/core/fundamentals/static-files#fileextensioncontenttypeprovider).

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.StaticFiles.FileExtensionContentTypeProvider`

-->
