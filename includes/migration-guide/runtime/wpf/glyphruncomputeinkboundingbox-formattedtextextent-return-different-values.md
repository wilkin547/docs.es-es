---
ms.openlocfilehash: 059aa6f5885634b22b64d594563973f17fd2c4e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805046"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a>GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven otros valores a partir de .NET Framework 4.5

|   |   |
|---|---|
|Detalles|Se efectuaron mejoras en los elementos <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> y <xref:System.Windows.Media.FormattedText.Extent> en .NET Framework 4.5 para solucionar problemas por los que los rectángulos eran demasiado pequeños para los glifos incluidos en algunos casos en .NET Framework 4.0. Como resultado de ello, algunos rectángulos de selección son más grandes a partir de .NET Framework 4.5, por lo que hay ligeras diferencias en el diseño de la IU.|
|Sugerencia|Tenga en cuenta que los rectángulos de selección de algunos glifos ahora son de mayor tamaño. Por lo general, estos cambios mejorarán la presentación y las pruebas de acierto de los rectángulos, pero si se quiere revertir al comportamiento anterior (previo a la versión 4.5 de .NET Framework), puede añadirse la siguiente entrada al archivo app.config:<pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|
