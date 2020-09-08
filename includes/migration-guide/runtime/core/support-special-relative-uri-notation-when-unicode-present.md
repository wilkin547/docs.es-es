---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496838"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a>Admitir una notación de URI relativo especial cuando Unicode está presente

#### <a name="details"></a>Detalles

<xref:System.Uri> ya no lanzará una excepción <xref:System.NullReferenceException> al llamar a <xref:System.Uri.TryCreate%2A> en ciertos URI relativos que contienen Unicode. La reproducción más sencilla de <xref:System.NullReferenceException> se muestra a continuación, donde las dos instrucciones son equivalentes:<pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre>Para reproducir la excepción <xref:System.NullReferenceException>, se debe cumplir lo siguiente:<ul><li>El URI se debe especificar como relativo anteponiendo "http:" y excluyendo "//" después.</li><li>El URI debe contener símbolos no reservados o Unicode codificados por porcentaje.</li></ul>

#### <a name="suggestion"></a>Sugerencia

Los usuarios que dependan de este comportamiento para no permitir los URI relativos deben especificar en su lugar <xref:System.UriKind.Absolute?displayProperty=nameWithType> al crear un URI.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
