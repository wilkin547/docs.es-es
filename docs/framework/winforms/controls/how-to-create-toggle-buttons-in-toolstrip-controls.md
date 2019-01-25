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
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="ccc75-102">Procedimiento Crear botones de alternancia en los controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccc75-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="ccc75-103">Cuando un usuario hace clic en un botón de alternancia, aparece hundido y mantiene dicho aspecto hasta que el usuario hace clic en el botón nuevo.</span><span class="sxs-lookup"><span data-stu-id="ccc75-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="ccc75-104">Para crear un ToolStripButton con alternancia</span><span class="sxs-lookup"><span data-stu-id="ccc75-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="ccc75-105">Utilice código como el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="ccc75-105">Use code such as the following code example.</span></span> <span data-ttu-id="ccc75-106">Este código supone que el formulario contenga un <xref:System.Windows.Forms.ToolStrip> control y que su <xref:System.Windows.Forms.ToolStrip.Items%2A> colección contiene un <xref:System.Windows.Forms.ToolStripButton> llamado `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="ccc75-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="ccc75-107">También se supone que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="ccc75-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ccc75-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccc75-108">See also</span></span>
- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="ccc75-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="ccc75-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
