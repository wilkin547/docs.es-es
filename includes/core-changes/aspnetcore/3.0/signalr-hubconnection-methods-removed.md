---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032880"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: se han quitado los métodos ResetSendPing y ResetTimeout de HubConnection

Los métodos `ResetSendPing` y `ResetTimeout` se han quitado de la API `HubConnection` de SignalR. Estos métodos se diseñaron originalmente solo para uso interno, pero se hicieron públicos en ASP.NET Core 2.2. Estos métodos no estarán disponibles a partir de ASP.NET Core 3.0, versión preliminar 4. Para obtener información, vea [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).

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
