---
ms.openlocfilehash: 841cb06bf94844d9f4da9dc33e60bad0d43dcd84
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70997717"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Admitir una notación de URI relativo especial cuando Unicode está presente

|   |   |
|---|---|
|Detalles|<xref:System.Uri> ya no lanzará una excepción <xref:System.NullReferenceException> al llamar a <xref:System.Uri.TryCreate%2A> en ciertos URI relativos que contienen Unicode. La reproducción más sencilla de <xref:System.NullReferenceException> se muestra a continuación, donde las dos instrucciones son equivalentes:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Para reproducir la excepción <xref:System.NullReferenceException>, se debe cumplir lo siguiente:<ul><li>El URI se debe especificar como relativo anteponiendo "http:" y excluyendo "//" después.</li><li>El URI debe contener símbolos no reservados o Unicode codificados por porcentaje.</li></ul>|
|Sugerencia|Los usuarios que dependan de este comportamiento para no permitir los URI relativos deben especificar en su lugar <xref:System.UriKind.Absolute?displayProperty=nameWithType> al crear un URI.|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li></ul>|
