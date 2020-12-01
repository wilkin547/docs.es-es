---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032903"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a>SPA: SpaServices y NodeServices ya no vuelven al registrador de la consola

<xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> y <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> no mostrarán los registros de la consola a menos que el registro esté configurado.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Antes, `Microsoft.AspNetCore.SpaServices` y `Microsoft.AspNetCore.NodeServices` creaban de forma automática un registrador de consola cuando el registro no estaba configurado.

#### <a name="new-behavior"></a>Comportamiento nuevo

`Microsoft.AspNetCore.SpaServices` y `Microsoft.AspNetCore.NodeServices` no mostrarán los registros de la consola a menos que el registro esté configurado.

#### <a name="reason-for-change"></a>Motivo del cambio

Existe la necesidad de alinearse con el modo de implementar el registro en otros paquetes de ASP.NET Core.

#### <a name="recommended-action"></a>Acción recomendada

Si se requiere el comportamiento anterior, agregue `services.AddLogging(builder => builder.AddConsole())` al método `Setup.ConfigureServices` para configurar el registro de la consola.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!--

#### Affected APIs

Not detectable via API analysis

-->
