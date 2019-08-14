---
title: Procedimiento para crear botones de alternancia en los controles ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972362"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Procedimiento para crear botones de alternancia en los controles ToolStrip

Cuando un usuario hace clic en un botón de alternancia, aparece hundido y conserva el aspecto hundido hasta que el usuario vuelve a hacer clic en el botón.

## <a name="to-create-a-toggling-toolstripbutton"></a>Para crear un ToolStripButton de alternancia

- Utilice código como el siguiente ejemplo de código. En este código se supone que el formulario <xref:System.Windows.Forms.ToolStrip> contiene un control y que <xref:System.Windows.Forms.ToolStrip.Items%2A> su colección contiene <xref:System.Windows.Forms.ToolStripButton> un `toolStripButton1`denominado. También se supone que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.

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
- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
