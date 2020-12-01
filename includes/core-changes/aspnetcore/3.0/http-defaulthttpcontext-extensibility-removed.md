---
ms.openlocfilehash: 9d138f79fcede4acac837f8d7793aa343ced737c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032770"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: se ha quitado la extensibilidad de DefaultHttpContext

Como parte de las mejoras de rendimiento de ASP.NET Core 3.0, se ha quitado la extensibilidad de `DefaultHttpContext`. La clase ahora es `sealed`. Para obtener más información, consulte [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).

Si en las pruebas unitarias se usa `Mock<DefaultHttpContext>`, use `Mock<HttpContext>` o `new DefaultHttpContext()` en su lugar.

Para obtener información, vea [dotnet/aspnetcore#6534](https://github.com/dotnet/aspnetcore/issues/6534).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las clases se pueden derivar de `DefaultHttpContext`.

#### <a name="new-behavior"></a>Comportamiento nuevo

Las clases se pueden derivar de `DefaultHttpContext`.

#### <a name="reason-for-change"></a>Motivo del cambio

La extensibilidad se proporcionó inicialmente para permitir la agrupación de `HttpContext`, pero incorporaba una complejidad innecesaria e impedía otras optimizaciones.

#### <a name="recommended-action"></a>Acción recomendada

Si usa `Mock<DefaultHttpContext>` en las pruebas unitarias, empiece a usar `Mock<HttpContext>` en su lugar.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Http.DefaultHttpContext?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Http.DefaultHttpContext`

-->
