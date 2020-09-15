---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616309"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a><span data-ttu-id="e29ca-101">Adición de la propiedad pública SelectionTextBrush a la selección de no basada en Adorner de TextBox y PasswordBox</span><span class="sxs-lookup"><span data-stu-id="e29ca-101">Add SelectionTextBrush public property to TextBox/PasswordBox non-adorner selection</span></span>

#### <a name="details"></a><span data-ttu-id="e29ca-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e29ca-102">Details</span></span>

<span data-ttu-id="e29ca-103">En aplicaciones de WPF [no basadas en Adorner según la selección de texto](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) para <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox>, los desarrolladores ahora pueden establecer la propiedad agregada recientemente de SelectionTextBrush con el fin de modificar la representación del texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e29ca-103">In WPF applications using [non-adorner based text selection](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) for <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox>, developers may now set the newly added SelectionTextBrush property in order to alter the rendering of the selected text.</span></span>  <span data-ttu-id="e29ca-104">De forma predeterminada, este color cambia con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span><span class="sxs-lookup"><span data-stu-id="e29ca-104">By default, this color changes with <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span></span>  <span data-ttu-id="e29ca-105">Si no está habilitada la selección de texto no basada en Adorner, esta propiedad no hace nada.</span><span class="sxs-lookup"><span data-stu-id="e29ca-105">If non-adorner based text selection is not enabled, this property does nothing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e29ca-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e29ca-106">Suggestion</span></span>

<span data-ttu-id="e29ca-107">Una vez habilitada la selección de texto no basada en Adorner, puede usar las propiedades <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> y <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> para cambiar la apariencia del texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e29ca-107">Once non-adorner based text selection is enabled, you can use the <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> property to change the appearance of the selected text.</span></span> <span data-ttu-id="e29ca-108">Esto puede realizarse mediante XAML:</span><span class="sxs-lookup"><span data-stu-id="e29ca-108">This can be achieved using XAML:</span></span>

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="e29ca-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e29ca-109">Name</span></span>    | <span data-ttu-id="e29ca-110">Valor</span><span class="sxs-lookup"><span data-stu-id="e29ca-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e29ca-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e29ca-111">Scope</span></span>   | <span data-ttu-id="e29ca-112">Major</span><span class="sxs-lookup"><span data-stu-id="e29ca-112">Major</span></span>       |
| <span data-ttu-id="e29ca-113">Versión</span><span class="sxs-lookup"><span data-stu-id="e29ca-113">Version</span></span> | <span data-ttu-id="e29ca-114">4.8</span><span class="sxs-lookup"><span data-stu-id="e29ca-114">4.8</span></span>         |
| <span data-ttu-id="e29ca-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="e29ca-115">Type</span></span>    | <span data-ttu-id="e29ca-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e29ca-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e29ca-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e29ca-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [<span data-ttu-id="e29ca-118">System.Windows.Controls.TextBox</span><span class="sxs-lookup"><span data-stu-id="e29ca-118">System.Windows.Controls.TextBox</span></span>](xref:System.Windows.Controls.TextBox)
- [<span data-ttu-id="e29ca-119">System.Windows.Controls.PasswordBox</span><span class="sxs-lookup"><span data-stu-id="e29ca-119">System.Windows.Controls.PasswordBox</span></span>](xref:System.Windows.Controls.PasswordBox)
