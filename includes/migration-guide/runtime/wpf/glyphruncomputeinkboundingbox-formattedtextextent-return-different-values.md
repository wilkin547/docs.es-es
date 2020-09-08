---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497767"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven otros valores a partir de .NET Framework 4.5

#### <a name="details"></a>Detalles

Se efectuaron mejoras en los elementos <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> y <xref:System.Windows.Media.FormattedText.Extent> en .NET Framework 4.5 para solucionar problemas por los que los rectángulos eran demasiado pequeños para los glifos incluidos en algunos casos en .NET Framework 4.0. Como resultado de ello, algunos rectángulos de selección son más grandes a partir de .NET Framework 4.5, por lo que hay ligeras diferencias en el diseño de la IU.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que los rectángulos de selección de algunos glifos ahora son de mayor tamaño. Por lo general, estos cambios mejorarán la presentación y las pruebas de acierto de los rectángulos, pero si se quiere revertir al comportamiento anterior (previo a la versión 4.5 de .NET Framework), puede añadirse la siguiente entrada al archivo app.config:<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
