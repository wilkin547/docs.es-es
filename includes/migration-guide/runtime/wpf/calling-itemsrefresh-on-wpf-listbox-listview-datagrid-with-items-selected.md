---
ms.openlocfilehash: 710d1517397f423fa40cc0c4a26c3499aac6179e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620683"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Llamar a Items.Refresh en un elemento ListBox o ListView, o una cuadrícula de datos de WPF con elementos seleccionados puede hacer que aparezcan elementos duplicados en el elemento

#### <a name="details"></a>Detalles

En .NET Framework 4.5, llamar a ListBox.Items.Refresh desde el código con elementos seleccionados en un elemento <xref:System.Windows.Controls.ListBox?displayProperty=fullName> puede hacer que los elementos seleccionados se dupliquen en la lista. Se produce un problema similar con <xref:System.Windows.Controls.ListView?displayProperty=fullName> y <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>. Este problema se corrigió en .NET Framework 4.6.

#### <a name="suggestion"></a>Sugerencia

Una solución alternativa para este problema consiste en, mediante programación, anular la selección de los elementos antes de llamar a <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> y volver a seleccionarlos después de que la llamada se complete. Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
