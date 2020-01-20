---
ms.openlocfilehash: 1b4b0aba3ea24682ae972bf283ac387692c83781
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901885"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: se ha quitado la extensibilidad de DefaultHttpContext

Como parte de las mejoras de rendimiento de ASP.NET Core 3.0, se ha quitado la extensibilidad de `DefaultHttpContext`. La clase ahora es `sealed`. Para obtener más información, consulte [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504).

Si las pruebas unitarias usan `Mock<DefaultHttpContext>`, utilice `Mock<HttpContext>` en su lugar.

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
