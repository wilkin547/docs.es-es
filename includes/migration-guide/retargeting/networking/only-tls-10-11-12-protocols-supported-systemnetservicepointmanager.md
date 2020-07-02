---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615762"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>En System.Net.ServicePointManager y System.Net.Security.SslStream solo se admiten los protocolos TLS 1.0, 1.1 y 1.2

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager> y <xref:System.Net.Security.SslStream> solo pueden usar uno de los tres protocolos siguientes: Tls1.0, Tls1.1 o Tls1.2. No se admite el protocolo SSL 3.0 ni el cifrado RC4.

#### <a name="suggestion"></a>Sugerencia

La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls1.0, Tls1.1 o Tls1.2. Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext?displayProperty=fullName> para descartar esta característica de cualquiera de estas dos maneras:

- Configurando mediante programación los modificadores de compatibilidad en la instancia <xref:System.AppContext?displayProperty=fullName>, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).
- Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
