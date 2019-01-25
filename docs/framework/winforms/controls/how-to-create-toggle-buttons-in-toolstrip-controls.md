---
title: Procedimiento Crear botones de alternancia en los controles ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 723916eb0c1e242df301c49bf0716e0262a3ba42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614983"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Procedimiento Crear botones de alternancia en los controles ToolStrip
Cuando un usuario hace clic en un botón de alternancia, aparece hundido y mantiene dicho aspecto hasta que el usuario hace clic en el botón nuevo.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>Para crear un ToolStripButton con alternancia  
  
-   Utilice código como el siguiente ejemplo de código. Este código supone que el formulario contenga un <xref:System.Windows.Forms.ToolStrip> control y que su <xref:System.Windows.Forms.ToolStrip.Items%2A> colección contiene un <xref:System.Windows.Forms.ToolStripButton> llamado `toolStripButton1`. También se supone que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolStripButton>
- [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
