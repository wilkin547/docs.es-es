---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616309"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Adición de la propiedad pública SelectionTextBrush a la selección de no basada en Adorner de TextBox y PasswordBox

#### <a name="details"></a>Detalles

En aplicaciones de WPF [no basadas en Adorner según la selección de texto](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) para <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox>, los desarrolladores ahora pueden establecer la propiedad agregada recientemente de SelectionTextBrush con el fin de modificar la representación del texto seleccionado.  De forma predeterminada, este color cambia con <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Si no está habilitada la selección de texto no basada en Adorner, esta propiedad no hace nada.

#### <a name="suggestion"></a>Sugerencia

Una vez habilitada la selección de texto no basada en Adorner, puede usar las propiedades <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> y <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> para cambiar la apariencia del texto seleccionado. Esto puede realizarse mediante XAML:

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.8         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)
- [System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)
