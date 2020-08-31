---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608468"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>WinHttpHandler quitado del entorno de ejecución de .NET

La clase `WinHttpHandler` se ha quitado del ensamblado *System.Net.Http.dll*. Ahora solo está disponible como un [paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) fuera de banda (OOB).

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, la clase <xref:System.Net.Http.WinHttpHandler> está disponible como parte de las bibliotecas básicas de .NET. A partir de .NET 5.0, la clase solo está disponible como un <xref:System.Net.Http.WinHttpHandler>[paquete NuGet](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) instalado por separado.

#### <a name="recommended-action"></a>Acción recomendada

Instale el [paquete NuGet System.Net.Http.WinHttpHandler](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). O bien, si no necesita características específicas de WinHTTP, use <xref:System.Net.Http.SocketsHttpHandler> en su lugar.

#### <a name="category"></a>Categoría

Redes

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
