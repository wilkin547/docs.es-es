---
ms.openlocfilehash: 0ea8c4843bb0dfb4e4208f2bfad4c416bfae7a1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805074"
---
### <a name="tls-1x-by-default-passes-the-schsendauxrecord-flag-to-the-underlying-schannel-api"></a>De forma predeterminada, TLS 1.x pasa la marca SCH_SEND_AUX_RECORD a la API SCHANNEL subyacente.

|   |   |
|---|---|
|Detalles|Cuando se usa TLS 1.x, .NET Framework se basa en la API SCHANNEL de Windows subyacente. A partir de .NET Framework 4.6, de forma predeterminada se pasa la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) a SCHANNEL. Esto hace que SCHANNEL divida los datos para que se cifren en dos registros independientes, el primero de un solo byte y el segundo de <em>n</em>-1 bytes. En raras ocasiones, esto interrumpe la comunicación entre los clientes y los servidores existentes; con esto se supone que los datos residen en un único registro.|
|Sugerencia|Si este cambio interrumpe la comunicación con un servidor existente, puede deshabilitar el envío de la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/desktop/api/schannel/ns-schannel-_schannel_cred) y restaurar el comportamiento anterior de no dividir los datos en registros independientes si agrega el modificador siguiente al elemento [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) de la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontEnableSchSendAuxRecord=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores. Pero no se recomienda su uso.</blockquote> |
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
