---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394131"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel: las abstracciones de transporte se han quitado y se han hecho públicas

Como parte del desplazamiento de las API de "pubternal", las API de la capa de transporte de Kestrel se exponen como una interfaz pública en la biblioteca de `Microsoft.AspNetCore.Connections.Abstractions`.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

- Las abstracciones relacionadas con el transporte estaban disponibles en la biblioteca de `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.
- La propiedad `ListenOptions.NoDelay` estaba disponible.

#### <a name="new-behavior"></a>Comportamiento nuevo

- La interfaz de `IConnectionListener` se presentaba en la biblioteca de `Microsoft.AspNetCore.Connections.Abstractions` para exponer la funcionalidad más usada de la biblioteca de `...Transport.Abstractions`.
- `NoDelay` está ahora disponible en opciones de transporte (`LibuvTransportOptions` y `SocketTransportOptions`).
- `SchedulingMode` ya no está disponible.

#### <a name="reason-for-change"></a>Motivo del cambio

ASP.NET Core 3.0 se ha desplazado de las API de "pubternal".

#### <a name="recommended-action"></a>Acción recomendada

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

### Affected APIs

Not detectable via API analysis

-->
