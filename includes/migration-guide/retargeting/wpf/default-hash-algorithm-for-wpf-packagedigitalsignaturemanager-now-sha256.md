---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614914"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>El algoritmo hash predeterminado para PackageDigitalSignatureManager de WPF ahora es SHA256

#### <a name="details"></a>Detalles

`System.IO.Packaging.PackageDigitalSignatureManager` proporciona funcionalidad para las firmas digitales en relación con los paquetes de WPF.  En .NET Framework 4.7 y versiones anteriores, el algoritmo predeterminado (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) que se usaba para firmar los elementos de un paquete era SHA1.  Por motivos de seguridad recientes con SHA1, este valor predeterminado se ha cambiado a SHA256 a partir de .NET Framework 4.7.1.  Este cambio afecta a todas las firmas de paquetes, incluidos los documentos XPS.

#### <a name="suggestion"></a>Sugerencia

Un desarrollador que quiera usar este cambio mientras selecciona como destino una versión de la plataforma inferior a .NET Framework 4.7.1 o un desarrollador que requiera la funcionalidad anterior mientras selecciona como destino .NET Framework 4.7.1 o una versión posterior pueden establecer de manera apropiada la marca de AppContext siguiente.  Un valor de true dará como resultado el uso de SHA1 como el algoritmo predeterminado; false hará que se use SHA256.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
