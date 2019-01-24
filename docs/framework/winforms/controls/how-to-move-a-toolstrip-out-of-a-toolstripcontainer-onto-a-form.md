---
title: Procedimiento Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 4e5c621b9738ce6b5f259425e63a2369556c4ded
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597725"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="1c93e-102">Procedimiento Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="1c93e-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="1c93e-103">Utilice el siguiente procedimiento para mover un <xref:System.Windows.Forms.ToolStrip> fuera de un <xref:System.Windows.Forms.ToolStripContainer> a un formulario.</span><span class="sxs-lookup"><span data-stu-id="1c93e-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c93e-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="1c93e-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1c93e-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="1c93e-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1c93e-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1c93e-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="1c93e-107">Para mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="1c93e-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="1c93e-108">Seleccione el control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="1c93e-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="1c93e-109">Cortar la <xref:System.Windows.Forms.ToolStrip> por presionando CTRL + X o haga clic en el <xref:System.Windows.Forms.ToolStrip> y elija **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="1c93e-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="1c93e-110">Seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="1c93e-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="1c93e-111">Pegar la <xref:System.Windows.Forms.ToolStrip> presione CTRL+V o elija **pegar** desde el **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="1c93e-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="1c93e-112">Establecer el <xref:System.Windows.Forms.ToolStrip.Dock%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a **superior**.</span><span class="sxs-lookup"><span data-stu-id="1c93e-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c93e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c93e-113">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="1c93e-114">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1c93e-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
