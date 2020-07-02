---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622124"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>Las llamadas a DataGrid.CommitEdit desde un controlador CellEditEnding eliminan el foco

#### <a name="details"></a>Detalles

Las llamadas a <xref:System.Windows.Controls.DataGrid.CommitEdit> desde uno de los controladores de eventos <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> de <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> provoca que <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> pierda el foco.

#### <a name="suggestion"></a>Sugerencia

Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework. Como alternativa, se puede evitar si se selecciona <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> de forma explícita después de llamar a <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
