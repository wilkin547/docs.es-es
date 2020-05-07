---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595692"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a>Las propiedades UriBuilder ya no anteponen caracteres iniciales

<xref:System.UriBuilder.Fragment?displayProperty=nameWithType> ya no antepone un carácter `#` inicial y <xref:System.UriBuilder.Query?displayProperty=nameWithType> ya no antepone un carácter `?` inicial si ya existe uno.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework, las propiedades <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> y <xref:System.UriBuilder.Query?displayProperty=nameWithType> siempre anteponen un carácter `#` o `?`, respectivamente, al valor que se va a almacenar. Este comportamiento puede producir varios caracteres `#` o `?` en el valor almacenado si la cadena ya contiene uno de estos caracteres iniciales. Por ejemplo, el valor de <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> podría convertirse en `##main`.

A partir de .NET Core 1.0, estas propiedades ya no anteponen los caracteres `#` o `?` al valor almacenado si ya hay uno presente al principio de la cadena.

#### <a name="version-introduced"></a>Versión introducida

1.0

#### <a name="recommended-action"></a>Acción recomendada

Ya no es necesario quitar explícitamente ninguno de estos caracteres iniciales al establecer los valores de propiedad. Esto es especialmente útil cuando se anexan valores, puesto que ya no es necesario quitar los caracteres `#` iniciales o `?` al anexar.

Por ejemplo, en el siguiente fragmento de código puede verse la diferencia de comportamiento entre .NET Framework y .NET Core.

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- En .NET Framework, el resultado es `????one=1&two=2&three=3&four=4`.
- En .NET Core, el resultado es `?one=1&two=2&three=3&four=4`.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
