---
ms.openlocfilehash: 75f176133697056bab9349ba1d18d7a0e1aa7da2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620529"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear no quita los duplicados de SelectedItems

#### <a name="details"></a>Detalles

Supongamos que un Selector (con la selección múltiple habilitada) tiene duplicados en su colección <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>: el mismo elemento aparece más de una vez.  Si esos elementos se quitan del origen de datos (por ejemplo, mediante una llamada a Items.Clear), no se quitan de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; solo se quita la primera instancia. Además, el uso posterior de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (como SelectedItems.Clear()) puede tener problemas, como una excepción <xref:System.ArgumentException?displayProperty=fullName>, porque <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contiene elementos que ya no están en el origen de datos.

#### <a name="suggestion"></a>Sugerencia

Si es posible, actualice a .NET Framework 4.6.2.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
