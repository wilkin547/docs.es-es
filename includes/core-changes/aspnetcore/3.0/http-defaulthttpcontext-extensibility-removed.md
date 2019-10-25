---
ms.openlocfilehash: 177617569a93e09f4c2a05acc21dce362edd58bc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394037"
---
### <a name="http-defaulthttpcontext-extensibility-removed"></a>HTTP: se ha quitado la extensibilidad de DefaultHttpContext

Como parte de las mejoras de rendimiento de ASP.NET Core 3.0, se ha quitado la extensibilidad de `DefaultHttpContext`. La clase ahora es `sealed`. Para obtener más información, consulte [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504).

Si las pruebas unitarias usan `Mock<DefaultHttpContext>`, utilice `Mock<HttpContext>` en su lugar. 

Para obtener información, consulte [aspnet/AspNetCore#6534](https://github.com/aspnet/AspNetCore/issues/6534).

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
