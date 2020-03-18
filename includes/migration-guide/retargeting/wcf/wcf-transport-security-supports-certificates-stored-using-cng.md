---
ms.openlocfilehash: b57e0acb03a99f33460a7b6c880280b37e01a17b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859232"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>La seguridad de transporte de WCF admite los certificados almacenados con CNG

|   |   |
|---|---|
|Detalles|A partir de las aplicaciones destinadas a .NET Framework 4.6.2, la seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. Esta compatibilidad está limitada a los certificados con una clave pública que tengan un exponente con una longitud no superior a 32 bits. Cuando una aplicación está destinada a .NET Framework 4.6.2, esta característica está activada de manera predeterminada. En versiones anteriores de .NET Framework, el intento de usar certificados X509 con un proveedor de almacenamiento de claves CSG inicia una excepción.|
|Sugerencia|Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2, pueden habilitar la compatibilidad para los certificados de CNG si agregan la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config o web.config:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableCngCertificates=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Esto también puede realizarse mediante programación con el siguiente código:<pre><code class="lang-cs">private const string DisableCngCertificates = @&quot;Switch.System.ServiceModel.DisableCngCertificate&quot;;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, false);&#13;&#10;</code></pre><pre><code class="lang-vb">Const DisableCngCertificates As String = &quot;Switch.System.ServiceModel.DisableCngCertificates&quot;&#13;&#10;AppContext.SetSwitch(disableCngCertificates, False)&#13;&#10;</code></pre>Tenga en cuenta que, debido a este cambio, cualquier código erróneo de control de excepciones que dependa del intento de iniciar una comunicación segura con un certificado CNG dejará de ejecutarse.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Redestinación|
