---
title: 'Cómo: Habilitar la tecla TAB para salir de un control ToolStrip'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 0af6c4c308ac1988b5f1babd80897afd5bf6a4d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531220"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="429af-102">Cómo: Habilitar la tecla TAB para salir de un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="429af-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="429af-103">Utilice el procedimiento siguiente para permitir al usuario que presione la tecla TAB para desplazarse de un <xref:System.Windows.Forms.ToolStrip> al siguiente control en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="429af-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="429af-104">El <xref:System.Windows.Forms.ToolStrip> acepta la primera que presiona la tecla TAB y la selección de elementos de teclas de flecha dentro de la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="429af-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="429af-105">Cuando el usuario presiona la tecla TAB una segunda vez, lleva al usuario al siguiente control en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="429af-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="429af-106">Para permitir al usuario que presione la tecla TAB para salir de un control ToolStrip al control siguiente</span><span class="sxs-lookup"><span data-stu-id="429af-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="429af-107">Establecer el <xref:System.Windows.Forms.ToolStrip.TabStop%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a `true`.</span><span class="sxs-lookup"><span data-stu-id="429af-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429af-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="429af-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [<span data-ttu-id="429af-109">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="429af-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
