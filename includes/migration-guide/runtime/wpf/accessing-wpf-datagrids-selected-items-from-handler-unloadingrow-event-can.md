---
ms.openlocfilehash: 7ac0cac53ab2fa7657d0ae58f11d9e777631acc9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620692"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>El acceso a los elementos seleccionados de un control DataGrid de WPF desde un controlador del evento UnloadingRow del control DataGrid puede producir una excepción NullReferenceException

#### <a name="details"></a>Detalles

Debido a un error de .NET Framework 4.5, los controladores de eventos para los eventos <xref:System.Windows.Controls.DataGrid> en los que se elimina una fila pueden provocar que se inicie una excepción <xref:System.NullReferenceException?displayProperty=fullName> si tienen acceso a las propiedades <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> de <xref:System.Windows.Controls.DataGrid>.

#### <a name="suggestion"></a>Sugerencia

Este problema se ha corregido en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión de .NET Framework.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
