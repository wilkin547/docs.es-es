---
title: 'Cómo: Acoplar controles en formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 82aef0ae9abacad33b21920f88591c0e4c33dfcb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460552"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="044c1-102">Cómo: acoplar controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="044c1-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="044c1-103">Puede acoplar controles a los bordes del formulario o hacer que rellenen el contenedor del control (ya sea un formulario o un control contenedor).</span><span class="sxs-lookup"><span data-stu-id="044c1-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="044c1-104">Por ejemplo, el explorador de Windows acopla su control <xref:System.Windows.Forms.TreeView> al lado izquierdo de la ventana y su control <xref:System.Windows.Forms.ListView> al lado derecho de la ventana.</span><span class="sxs-lookup"><span data-stu-id="044c1-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="044c1-105">Use la propiedad <xref:System.Windows.Forms.Control.Dock%2A> de todos los controles de Windows Forms visibles para definir el modo de acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="044c1-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="044c1-106">Los controles se acoplan en orden z inverso.</span><span class="sxs-lookup"><span data-stu-id="044c1-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="044c1-107">La propiedad <xref:System.Windows.Forms.Control.Dock%2A> interactúa con la propiedad <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="044c1-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="044c1-108">Para obtener más información, vea [información general sobre la propiedad AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="044c1-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="044c1-109">Para acoplar un control</span><span class="sxs-lookup"><span data-stu-id="044c1-109">To dock a control</span></span>

1. <span data-ttu-id="044c1-110">En Visual Studio, seleccione el control que desea acoplar.</span><span class="sxs-lookup"><span data-stu-id="044c1-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="044c1-111">En la ventana **propiedades** , haga clic en la flecha situada a la derecha de la propiedad <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="044c1-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="044c1-112">Se muestra un editor que muestra una serie de cuadros que representan los bordes y el centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="044c1-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="044c1-113">Haga clic en el botón que representa el borde del formulario en el que desea acoplar el control.</span><span class="sxs-lookup"><span data-stu-id="044c1-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="044c1-114">Para rellenar el contenido del control de formulario o contenedor del control, haga clic en el cuadro central.</span><span class="sxs-lookup"><span data-stu-id="044c1-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="044c1-115">Haga clic en **(ninguno)** para deshabilitar el acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="044c1-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="044c1-116">El control cambia automáticamente de tamaño para ajustarse a los límites del borde acoplado.</span><span class="sxs-lookup"><span data-stu-id="044c1-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="044c1-117">Los controles heredados deben estar `Protected` para poder acoplarse.</span><span class="sxs-lookup"><span data-stu-id="044c1-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="044c1-118">Para cambiar el nivel de acceso de un control, establezca su propiedad **modificador** en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="044c1-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="044c1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="044c1-119">See also</span></span>

- [<span data-ttu-id="044c1-120">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="044c1-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="044c1-121">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="044c1-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="044c1-122">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="044c1-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="044c1-123">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="044c1-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="044c1-124">Delimitar y acoplar controles secundarios en un control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="044c1-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="044c1-125">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="044c1-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="044c1-126">Información general sobre la propiedad AutoSize</span><span class="sxs-lookup"><span data-stu-id="044c1-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="044c1-127">Procedimiento para delimitar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="044c1-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
