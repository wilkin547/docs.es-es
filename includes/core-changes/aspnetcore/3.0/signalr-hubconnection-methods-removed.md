---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901894"
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
