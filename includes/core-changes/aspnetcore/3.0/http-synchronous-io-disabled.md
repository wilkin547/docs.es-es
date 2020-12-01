---
ms.openlocfilehash: 53d2c989120c92f4e2d18f50ce4b364bd4c9b604
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032778"
---
### <a name="http-synchronous-io-disabled-in-all-servers"></a>HTTP: se ha deshabilitado la E/S sincrónica en todos los servidores

A partir de ASP.NET Core 3.0, las operaciones de servidor sincrónicas están deshabilitadas de forma predeterminada.

#### <a name="change-description"></a>Descripción del cambio

`AllowSynchronousIO` es una opción en cada servidor que habilita o deshabilita las API de E/S sincrónicas, como `HttpRequest.Body.Read`, `HttpResponse.Body.Write` y `Stream.Flush`. Estas API han sido durante mucho tiempo una fuente de colapsos de subprocesos y de bloqueos de la aplicación. A partir de ASP.NET Core 3.0, versión preliminar 3, estas operaciones sincrónicas están deshabilitadas de forma predeterminada.

Servidores afectados:

- Kestrel
- HttpSys
- IIS en proceso
- TestServer

Se esperan errores parecidos a los siguientes:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

Cada servidor tiene una opción `AllowSynchronousIO` que controla este comportamiento y el valor predeterminado para todos ellos ahora es `false`.

El comportamiento también se puede invalidar en función de cada solicitud como una mitigación temporal. Por ejemplo:

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

Si tiene problemas con una elemento `TextWriter` u otra secuencia que llama a una API sincrónica en `Dispose`, llame a la nueva API de `DisposeAsync` en su lugar.

Para obtener información, vea [dotnet/aspnetcore#7644](https://github.com/dotnet/aspnetcore/issues/7644).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

De manera predeterminada, solo se permitían `HttpRequest.Body.Read`, `HttpResponse.Body.Write` y `Stream.Flush`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Estas API sincrónicas no están permitidas de forma predeterminada:

Se esperan errores parecidos a los siguientes:

- `Synchronous operations are disallowed. Call ReadAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call WriteAsync or set AllowSynchronousIO to true instead.`
- `Synchronous operations are disallowed. Call FlushAsync or set AllowSynchronousIO to true instead.`

#### <a name="reason-for-change"></a>Motivo del cambio

Estas API sincrónicas han sido durante mucho tiempo una fuente de colapsos de subprocesos y de bloqueos de la aplicación. A partir de ASP.NET Core 3.0, versión preliminar 3, las operaciones sincrónicas están deshabilitadas de forma predeterminada.

#### <a name="recommended-action"></a>Acción recomendada

Use las versiones asincrónicas de los métodos. El comportamiento también se puede invalidar en función de cada solicitud como una mitigación temporal.

```csharp
var syncIOFeature = HttpContext.Features.Get<IHttpBodyControlFeature>();
if (syncIOFeature != null)
{
    syncIOFeature.AllowSynchronousIO = true;
}
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Stream.Flush%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>
- <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.IO.Stream.Flush`
- `Overload:System.IO.Stream.Read`
- `Overload:System.IO.Stream.Write`

-->
