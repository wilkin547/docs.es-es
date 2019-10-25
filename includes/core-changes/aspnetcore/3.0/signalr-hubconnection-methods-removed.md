---
ms.openlocfilehash: a56c5fc32b5fd274d5da0d9b295918f5ea3b345e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394468"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: se han quitado los métodos ResetSendPing y ResetTimeout de HubConnection

Los métodos `ResetSendPing` y `ResetTimeout` se han quitado de la API `HubConnection` de SignalR. Estos métodos se diseñaron originalmente solo para uso interno, pero se hicieron públicos en ASP.NET Core 2.2. Estos métodos no estarán disponibles a partir de ASP.NET Core 3.0, versión preliminar 4. Para obtener información, consulte [aspnet/AspNetCore#8543](https://github.com/aspnet/AspNetCore/issues/8543).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Las API estaban disponibles.

#### <a name="new-behavior"></a>Comportamiento nuevo

Las API se quitan.

#### <a name="reason-for-change"></a>Motivo del cambio

Estos métodos se diseñaron originalmente solo para uso interno, pero se hicieron públicos en ASP.NET Core 2.2.

#### <a name="recommended-action"></a>Acción recomendada

No use estos métodos.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
