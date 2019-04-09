---
title: Filtrar para mover un elemento ToolStrip de un control ToolStripContainer a un formulario
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 100e744e6e49fbf214488e9bbb796b5b6fb9591a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142368"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="77834-102">Filtrar para mover un elemento ToolStrip de un control ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="77834-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="77834-103">Utilice el siguiente procedimiento para mover un <xref:System.Windows.Forms.ToolStrip> fuera de un <xref:System.Windows.Forms.ToolStripContainer> a un formulario.</span><span class="sxs-lookup"><span data-stu-id="77834-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77834-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="77834-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="77834-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="77834-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="77834-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="77834-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="77834-107">Para mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario</span><span class="sxs-lookup"><span data-stu-id="77834-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="77834-108">Seleccione el control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="77834-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="77834-109">Cortar la <xref:System.Windows.Forms.ToolStrip> por presionando CTRL + X o haga clic en el <xref:System.Windows.Forms.ToolStrip> y elija **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="77834-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="77834-110">Seleccione el formulario.</span><span class="sxs-lookup"><span data-stu-id="77834-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="77834-111">Pegar la <xref:System.Windows.Forms.ToolStrip> presione CTRL+V o elija **pegar** desde el **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="77834-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="77834-112">Establecer el <xref:System.Windows.Forms.ToolStrip.Dock%2A> propiedad de la <xref:System.Windows.Forms.ToolStrip> a **superior**.</span><span class="sxs-lookup"><span data-stu-id="77834-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77834-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="77834-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="77834-114">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="77834-114">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
