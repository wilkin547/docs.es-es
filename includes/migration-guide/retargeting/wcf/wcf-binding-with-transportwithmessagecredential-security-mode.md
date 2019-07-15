---
ms.openlocfilehash: ce7e2db3f74ec24f47b1c224335451c997c4c349
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804324"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Enlace de WCF con el modo de seguridad de TransportWithMessageCredential

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6.1, el enlace de WCF que usa el modo de seguridad de TransportWithMessageCredential se puede configurar para recibir mensajes con encabezados &quot;para&quot; sin firmar para las claves de seguridad asimétricas. De forma predeterminada, en .NET Framework 4.6.1 se seguirán rechazando los encabezados &quot;para&quot; sin firmar. Solo se aceptarán si una aplicación incluye este modo de operación nuevo mediante el modificador de configuración Switch.System.ServiceModel.AllowUnsignedToHeader.|
|Sugerencia|Como es una característica opcional, no debería afectar al comportamiento de las aplicaciones existentes.<br/>Para controlar si se usa el comportamiento nuevo o no, use la opción de configuración siguiente:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Transparente|
|Versión|4.6.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|

