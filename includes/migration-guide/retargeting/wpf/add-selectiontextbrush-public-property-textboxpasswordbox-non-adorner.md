---
ms.openlocfilehash: e04134ec731c5e7bede3388621078c6518805ec2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803534"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Adición de la propiedad pública SelectionTextBrush a la selección de no basada en Adorner de TextBox y PasswordBox

|   |   |
|---|---|
|Detalles|En aplicaciones de WPF [no basadas en Adorner según la selección de texto](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) para <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox>, los desarrolladores ahora pueden establecer la propiedad agregada recientemente de SelectionTextBrush con el fin de modificar la representación del texto seleccionado.  De forma predeterminada, este color cambia con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Si no está habilitada la selección de texto no basada en Adorner, esta propiedad no hace nada.|
|Sugerencia|Una vez habilitada la selección de texto no basada en Adorner, puede usar las propiedades <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> y <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> para cambiar la apariencia del texto seleccionado. Esto puede realizarse mediante XAML:<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>|
|Ámbito|Major|
|Versión|4.8|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType></li><li>[System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)</li><li>[System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)</li></ul>|
