---
ms.openlocfilehash: 2f94ec58e6fdb56cfc5147e74b6ffd6bb657228d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857493"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear no quita los duplicados de SelectedItems

|   |   |
|---|---|
|Detalles|Supongamos que un Selector (con la selección múltiple habilitada) tiene duplicados en su colección <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>: el mismo elemento aparece más de una vez.  Si esos elementos se quitan del origen de datos (por ejemplo, mediante una llamada a Items.Clear), no se quitan de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>; solo se quita la primera instancia. Además, el uso posterior de <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> (como SelectedItems.Clear()) puede tener problemas, como una excepción <xref:System.ArgumentException?displayProperty=name>, porque <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> contiene elementos que ya no están en el origen de datos.|
|Sugerencia|Si es posible, actualice a .NET Framework 4.6.2.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|

