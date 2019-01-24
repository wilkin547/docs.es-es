---
title: Procedimiento Reasignar controles existentes en un elemento primario diferente
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: fa1bd6c0274fdf702072e062e6eeab7078375491
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600289"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="6e03e-102">Procedimiento Reasignar controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="6e03e-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="6e03e-103">Puede asignar controles que existen en el formulario a un nuevo control contenedor.</span><span class="sxs-lookup"><span data-stu-id="6e03e-103">You can assign controls that exist on your form to a new container control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e03e-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="6e03e-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6e03e-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6e03e-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6e03e-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6e03e-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="6e03e-107">Para reasignar los controles existentes en un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="6e03e-107">To reassign existing controls to a different parent</span></span>  
  
1.  <span data-ttu-id="6e03e-108">Arrastre tres controles <xref:System.Windows.Forms.Button> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="6e03e-108">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>  
  
     <span data-ttu-id="6e03e-109">Colóquelos cerca entre sí, pero sin alinearlos.</span><span class="sxs-lookup"><span data-stu-id="6e03e-109">Position them near to each other, but leave them unaligned.</span></span>  
  
2.  <span data-ttu-id="6e03e-110">En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="6e03e-110">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>  
  
     <span data-ttu-id="6e03e-111">No arrastre el icono hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="6e03e-111">Do not drag the icon onto the form.</span></span>  
  
3.  <span data-ttu-id="6e03e-112">Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="6e03e-112">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
     <span data-ttu-id="6e03e-113">Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.</span><span class="sxs-lookup"><span data-stu-id="6e03e-113">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>  
  
4.  <span data-ttu-id="6e03e-114">Haga clic y mantenga presionado el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="6e03e-114">Click and hold the mouse button.</span></span>  
  
5.  <span data-ttu-id="6e03e-115">Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="6e03e-115">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6.  <span data-ttu-id="6e03e-116">Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="6e03e-116">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
7.  <span data-ttu-id="6e03e-117">Suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="6e03e-117">Release the mouse button.</span></span>  
  
     <span data-ttu-id="6e03e-118">Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="6e03e-118">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e03e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e03e-119">See also</span></span>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="6e03e-120">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6e03e-120">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="6e03e-121">Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="6e03e-121">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="6e03e-122">Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="6e03e-122">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
