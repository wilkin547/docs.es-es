---
title: Procedimiento Acoplar controles en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: f4a9d3bcf7f9db1634da2b2f06177c05061af28e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733550"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="0dd7b-102">Procedimiento Acoplar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dd7b-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="0dd7b-103">Puede acoplar controles a los bordes del formulario o hacer que rellene el contenedor del control (un formulario o un control contenedor).</span><span class="sxs-lookup"><span data-stu-id="0dd7b-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="0dd7b-104">Por ejemplo, en el Explorador de Windows se acopla su <xref:System.Windows.Forms.TreeView> control a la izquierda de la ventana y su <xref:System.Windows.Forms.ListView> control a la derecha de la ventana.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="0dd7b-105">Use el <xref:System.Windows.Forms.Control.Dock%2A> propiedad para todos los controles de Windows Forms visibles definir el modo de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0dd7b-106">Los controles se acoplan en orden z inverso.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="0dd7b-107">El <xref:System.Windows.Forms.Control.Dock%2A> propiedad interactúa con el <xref:System.Windows.Forms.Control.AutoSize%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="0dd7b-108">Para obtener más información, consulte [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0dd7b-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="0dd7b-109">Para acoplar un control</span><span class="sxs-lookup"><span data-stu-id="0dd7b-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="0dd7b-110">Seleccione el control que desee acoplar.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="0dd7b-111">En la ventana Propiedades, haga clic en la flecha situada a la derecha de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="0dd7b-112">Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="0dd7b-113">Haga clic en el botón que representa el borde del formulario donde desea acoplar el control.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="0dd7b-114">Para rellenar el contenido del control de contenedor o el formulario del control, haga clic en el cuadro del centro.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="0dd7b-115">Haga clic en **(ninguno)** para deshabilitar el acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="0dd7b-116">El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0dd7b-117">Los controles heredados deben estar `Protected` que puedan estar acoplada.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="0dd7b-118">Para cambiar el nivel de acceso de un control, establezca su **modificador** propiedad en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="0dd7b-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd7b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dd7b-119">See also</span></span>
- [<span data-ttu-id="0dd7b-120">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dd7b-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
- [<span data-ttu-id="0dd7b-121">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dd7b-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="0dd7b-122">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="0dd7b-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0dd7b-123">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dd7b-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0dd7b-124">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="0dd7b-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
- [<span data-ttu-id="0dd7b-125">Cómo: Delimitar y acoplar controles secundarios en un Control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0dd7b-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="0dd7b-126">Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0dd7b-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="0dd7b-127">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="0dd7b-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [<span data-ttu-id="0dd7b-128">Cómo: Delimitar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dd7b-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
