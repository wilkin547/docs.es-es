---
ms.openlocfilehash: 05116d80fcd6b75f366a2542ad2eadd5f434991c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805068"
---
### <a name="improved-wcf-chain-trust-certificate-validation-for-nettcp-certificate-authentication"></a>Mejora de la validación de certificados de confianza de cadena de WCF para la autenticación de certificados de Net.Tcp

|   |   |
|---|---|
|Detalles|.NET Framework 4.7.2 mejora la validación de certificados de confianza de cadena al usar la autenticación de certificados con seguridad de transporte con WCF. Con esta mejora, los certificados de cliente que se usan para la autenticación en un servidor se deben configurar para la autenticación de cliente.  De forma similar, los certificados de servidor que sirven para autenticar un servidor se deben configurar para la autenticación de servidor. Con este cambio, si el certificado raíz está deshabilitado, se produce un error en la validación de la cadena de certificados. El mismo cambio también se realizó en .NET Framework 3.5 y versiones posteriores mediante la acumulación de seguridad de Windows. Puede encontrar más información [aquí](https://support.microsoft.com/en-us/help/4055269/security-only-update-for-net-framework-3-5-1-4-5-2-4-6-4-6-1-4-6-2-4-7). Este cambio se activa de forma predeterminada y se puede desactivar con una opción de configuración.|
|Sugerencia|<ul><li>Valide si la certificación de servidor y cliente tiene el OID del EKU necesario. Si no es así, actualice la certificación.</li><li>Compruebe si el certificado raíz no es válido. Si es así, actualice el certificado raíz.</li><li>Cómo descartar el cambio: si no puede actualizar el certificado, puede evitar temporalmente la novedad con la opción de configuración siguiente, pero no participar en el cambio hará que el sistema sea vulnerable al problema de seguridad.</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;wcf:useLegacyCertificateUsagePolicy&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|
