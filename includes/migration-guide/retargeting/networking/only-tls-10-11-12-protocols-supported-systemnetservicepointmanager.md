---
ms.openlocfilehash: 29c5055a84e2dcc94bc4cdeab95722e4358aad89
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761130"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>En System.Net.ServicePointManager y System.Net.Security.SslStream solo se admiten los protocolos TLS 1.0, 1.1 y 1.2

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6, las clases <xref:System.Net.ServicePointManager> y <xref:System.Net.Security.SslStream> solo pueden usar uno de los tres protocolos siguientes: Tls1.0, Tls1.1 o Tls1.2. No se admite el protocolo SSL 3.0 ni el cifrado RC4.|
|Sugerencia|La mitigación recomendada consiste en actualizar la aplicación del lado servidor a Tls1.0, Tls1.1 o Tls1.2. Si esto no es posible o si las aplicaciones cliente se interrumpen, se puede usar la clase <xref:System.AppContext?displayProperty=name> para descartar esta característica de cualquiera de estas dos maneras:<ol><li>Configurando mediante programación los modificadores de compatibilidad en la instancia <xref:System.AppContext?displayProperty=name>, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</li><li>Agregando la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSchUseStrongCrypto=true&quot;/&gt;</code>;</li></ol>|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType></li></ul>|

