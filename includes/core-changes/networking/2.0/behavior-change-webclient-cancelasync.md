---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859620"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a>WebClient.CancelAsync no siempre se cancela inmediatamente

A partir de .NET Core 2.0, al llamar a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, no se cancela inmediatamente la solicitud si la respuesta ha empezado a recuperar cambios.

#### <a name="change-description"></a>Descripción del cambio

Antes, si se llamaba a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, la solicitud se cancelaba inmediatamente. A partir de .NET Core 2.0, al llamar a <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType>, la solicitud se cancela inmediatamente solo si la respuesta no ha empezado a recuperar cambios. Si la respuesta ha empezado a recuperar cambios, la solicitud se cancela solo después de leer una respuesta completa.

Este cambio se implementó porque la API de <xref:System.Net.WebClient> quedó en desuso en favor de <xref:System.Net.Http.HttpClient>.

#### <a name="version-introduced"></a>Versión introducida

2.0

#### <a name="recommended-action"></a>Acción recomendada

Use la clase <xref:System.Net.Http.HttpClient?displayProperty=fullName> en lugar de <xref:System.Net.WebClient?displayProperty=fullName>, que está en desuso.

#### <a name="category"></a>Categoría

Redes

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
