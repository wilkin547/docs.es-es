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
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="14a55-102">Procedimiento para crear botones de alternancia en los controles ToolStrip</span><span class="sxs-lookup"><span data-stu-id="14a55-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>

<span data-ttu-id="14a55-103">Cuando un usuario hace clic en un botón de alternancia, aparece hundido y conserva el aspecto hundido hasta que el usuario vuelve a hacer clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="14a55-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>

## <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="14a55-104">Para crear un ToolStripButton de alternancia</span><span class="sxs-lookup"><span data-stu-id="14a55-104">To create a toggling ToolStripButton</span></span>

- <span data-ttu-id="14a55-105">Utilice código como el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="14a55-105">Use code such as the following code example.</span></span> <span data-ttu-id="14a55-106">En este código se supone que el formulario <xref:System.Windows.Forms.ToolStrip> contiene un control y que <xref:System.Windows.Forms.ToolStrip.Items%2A> su colección contiene <xref:System.Windows.Forms.ToolStripButton> un `toolStripButton1`denominado.</span><span class="sxs-lookup"><span data-stu-id="14a55-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="14a55-107">También se supone que tiene un controlador de eventos denominado `toolStripButton1_CheckedChanged`.</span><span class="sxs-lookup"><span data-stu-id="14a55-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="14a55-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="14a55-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStripButton>
- [<span data-ttu-id="14a55-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="14a55-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
