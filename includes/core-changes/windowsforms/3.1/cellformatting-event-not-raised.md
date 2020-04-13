---
ms.openlocfilehash: b736ab743a628fdcbc53c5ee51551e5dad986885
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888150"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>El evento CellFormatting no se produce si se muestra información en pantalla.

Ahora, <xref:System.Windows.Forms.DataGridView> muestra información en pantalla del texto y los errores de una celda cuando se mantiene el mouse sobre ella y cuando se selecciona mediante el teclado. Si se muestra información en pantalla, no se produce el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>.

#### <a name="change-description"></a>Descripción del cambio

Antes de .NET Core 3.1, un elemento <xref:System.Windows.Forms.DataGridView> con la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> establecida en `true` mostraba información en pantalla del texto y los errores de una celda cuando se mantenía el mouse sobre ella. La información en pantalla no se mostraba si la celda se seleccionaba mediante el teclado (por ejemplo, mediante la tecla Tab, teclas de método abreviado o las teclas de dirección). Si el usuario editaba una celda y, luego, mientras el elemento <xref:System.Windows.Forms.DataGridView> aún estaba en modo de edición, mantenía el mouse sobre una celda que no tenía establecida la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>, se producía un evento <xref:System.Windows.Forms.DataGridView.CellFormatting> para dar formato al texto de la celda para su presentación en ella.

Para cumplir los estándares de accesibilidad, a partir de .NET Core 3.1, un elemento <xref:System.Windows.Forms.DataGridView> que tenga la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> establecida en `true` muestra información en pantalla del texto y los errores de una celda no solo cuando se mantiene el mouse sobre la celda, sino también cuando se selecciona mediante el teclado. Como consecuencia de este cambio, el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>*no* se produce cuando se mantiene el mouse sobre las celdas que no tienen establecida la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> mientras <xref:System.Windows.Forms.DataGridView> está en modo de edición. El evento no se produce porque el contenido de la celda se muestra como información en pantalla en lugar de mostrarse en la celda.

#### <a name="version-introduced"></a>Versión introducida

3.1

#### <a name="recommended-action"></a>Acción recomendada

Refactorice cualquier código que dependa del evento <xref:System.Windows.Forms.DataGridView.CellFormatting> mientras <xref:System.Windows.Forms.DataGridView> está en modo de edición.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

### Affected APIs

Not detectable via API analysis.

-->
