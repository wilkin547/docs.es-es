---
ms.openlocfilehash: fc17efbad63ee43ddcdfd14e2fbd1557d2b3d31c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72424795"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>De forma predeterminada, TLS 1.x pasa la marca SCH_SEND_AUX_RECORD a la API SCHANNEL subyacente.

|   |   |
|---|---|
|Detalles|Cuando se usa TLS 1.x, .NET Framework se basa en la API SCHANNEL de Windows subyacente. A partir de .NET Framework 4.6, de forma predeterminada se pasa la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) a SCHANNEL. Esto hace que SCHANNEL divida los datos que se van a cifrar en dos registros independientes, el primero de un solo byte y el segundo con <em>n</em>-1 bytes. En raras ocasiones, esto interrumpe la comunicación entre los clientes y los servidores existentes que dan por hecho que los datos residen en un único registro.|
|Sugerencia|Si este cambio interrumpe la comunicación con un servidor existente, puede deshabilitar el envío de la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) y restaurar el comportamiento anterior de no dividir los datos en registros independientes si agrega el modificador siguiente al elemento [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores. Pero no se recomienda su uso.</blockquote> |
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
