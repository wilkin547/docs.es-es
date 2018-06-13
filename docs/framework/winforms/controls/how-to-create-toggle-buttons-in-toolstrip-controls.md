---
title: 'Cómo: Crear botones de alternancia en los controles ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: a04d531433273328c2d8eb0c5ef614f08c33952a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530387"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="d5072-102">Cómo: Crear botones de alternancia en los controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5072-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="d5072-103">Cuando un usuario hace clic en un botón de alternancia, aparece bajo relieve y retiene ese aspecto hasta que el usuario hace clic en el botón de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d5072-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="d5072-104">Para crear un ToolStripButton con alternancia</span><span class="sxs-lookup"><span data-stu-id="d5072-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="d5072-105">Utilice código como el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="d5072-105">Use code such as the following code example.</span></span> <span data-ttu-id="d5072-106">Este código supone que el formulario contenga un <xref:System.Windows.Forms.ToolStrip> control y que su <xref:System.Windows.Forms.ToolStrip.Items%2A> colección contiene un <xref:System.Windows.Forms.ToolStripButton> denominado `toolStripButton1`.</span><span class="sxs-lookup"><span data-stu-id="d5072-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="d5072-107">También se supone que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="d5072-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5072-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5072-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripButton>  
 [<span data-ttu-id="d5072-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d5072-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
