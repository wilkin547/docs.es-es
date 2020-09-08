---
ms.openlocfilehash: d9e1624bbeb91db63bc284b8eb52643938eb42e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497767"
---
### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-framework-45"></a><span data-ttu-id="f92d6-101">GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven otros valores a partir de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f92d6-101">GlyphRun.ComputeInkBoundingBox() and FormattedText.Extent return different values beginning in .NET Framework 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="f92d6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f92d6-102">Details</span></span>

<span data-ttu-id="f92d6-103">Se efectuaron mejoras en los elementos <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> y <xref:System.Windows.Media.FormattedText.Extent> en .NET Framework 4.5 para solucionar problemas por los que los rectángulos eran demasiado pequeños para los glifos incluidos en algunos casos en .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="f92d6-103">Improvements were made to <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> and <xref:System.Windows.Media.FormattedText.Extent> in the .NET Framework 4.5 to address issues where the boxes were too small for the contained glyphs in some cases in the .NET Framework 4.0.</span></span> <span data-ttu-id="f92d6-104">Como resultado de ello, algunos rectángulos de selección son más grandes a partir de .NET Framework 4.5, por lo que hay ligeras diferencias en el diseño de la IU.</span><span class="sxs-lookup"><span data-stu-id="f92d6-104">As a result of this, some bounding boxes will be larger beginning in the .NET Framework 4.5, resulting in subtle differences in UI layout.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f92d6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f92d6-105">Suggestion</span></span>

<span data-ttu-id="f92d6-106">Tenga en cuenta que los rectángulos de selección de algunos glifos ahora son de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="f92d6-106">Be aware that some glyph bounding box sizes have increased.</span></span> <span data-ttu-id="f92d6-107">Por lo general, estos cambios mejorarán la presentación y las pruebas de acierto de los rectángulos, pero si se quiere revertir al comportamiento anterior (previo a la versión 4.5 de .NET Framework), puede añadirse la siguiente entrada al archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="f92d6-107">These changes will usually improve presentation and hit box testing, but if the older (pre-.NET 4.5) behavior is desired, it can be opted into by adding the following entry to the app.config file:</span></span><pre><code class="lang-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f92d6-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f92d6-108">Name</span></span>    | <span data-ttu-id="f92d6-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f92d6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f92d6-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f92d6-110">Scope</span></span>   |<span data-ttu-id="f92d6-111">Borde</span><span class="sxs-lookup"><span data-stu-id="f92d6-111">Edge</span></span>|
|<span data-ttu-id="f92d6-112">Versión</span><span class="sxs-lookup"><span data-stu-id="f92d6-112">Version</span></span>|<span data-ttu-id="f92d6-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f92d6-113">4.5</span></span>|
|<span data-ttu-id="f92d6-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="f92d6-114">Type</span></span>|<span data-ttu-id="f92d6-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f92d6-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f92d6-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f92d6-116">Affected APIs</span></span>

- <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType>
- <xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Media.GlyphRun.ComputeInkBoundingBox`
- `P:System.Windows.Media.FormattedText.Extent`

-->
