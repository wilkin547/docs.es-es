---
title: "Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
f1_keywords: net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15a725f7a5a4b61f826756c4c3f0d2a20c8a5011
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="cf979-102">Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf979-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="cf979-103">El control <xref:System.Windows.Forms.TableLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="cf979-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="cf979-104">Para alinear un control secundario en una celda de TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf979-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="cf979-105">Cree un control <xref:System.Windows.Forms.TableLayoutPanel> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="cf979-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2.  <span data-ttu-id="cf979-106">Establezca el valor de la <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> propiedades **1**.</span><span class="sxs-lookup"><span data-stu-id="cf979-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3.  <span data-ttu-id="cf979-107">Cree un control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="cf979-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="cf979-108">El <xref:System.Windows.Forms.Button> ocupa la esquina superior izquierda de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4.  <span data-ttu-id="cf979-109">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Left`.</span><span class="sxs-lookup"><span data-stu-id="cf979-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="cf979-110">El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf979-111">Este comportamiento difiere del comportamiento de otros controles contenedor.</span><span class="sxs-lookup"><span data-stu-id="cf979-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="cf979-112">En otros controles contenedor, el control secundario no mueve cuando se establece la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> y la distancia entre el control delimitado y el límite del contenedor primario se fija en el momento de establecer la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf979-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5.  <span data-ttu-id="cf979-113">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="cf979-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="cf979-114">El control <xref:System.Windows.Forms.Button> se mueve para ocupar la esquina superior izquierda de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6.  <span data-ttu-id="cf979-115">Repita el paso 5 con un valor de `Top, Right` para mover el <xref:System.Windows.Forms.Button> control a la esquina superior derecha de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="cf979-116">Repita con los valores de `Bottom, Left` e `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="cf979-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="cf979-117">Para ajustar un control secundario en una celda de TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf979-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1.  <span data-ttu-id="cf979-118">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="cf979-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="cf979-119">El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al ancho de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf979-120">Este comportamiento difiere del comportamiento de otros controles contenedor.</span><span class="sxs-lookup"><span data-stu-id="cf979-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="cf979-121">En otros controles contenedor, el control secundario no cambia de tamaño cuando el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad está establecida en `Left, Right` o `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="cf979-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2.  <span data-ttu-id="cf979-122">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="cf979-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="cf979-123">El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al alto de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3.  <span data-ttu-id="cf979-124">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="cf979-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="cf979-125">El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4.  <span data-ttu-id="cf979-126">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control <xref:System.Windows.Forms.Button> a `None`.</span><span class="sxs-lookup"><span data-stu-id="cf979-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="cf979-127">El control <xref:System.Windows.Forms.Button> cambia de tamaño y se centra en la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5.  <span data-ttu-id="cf979-128">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="cf979-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="cf979-129">El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="cf979-130">El control <xref:System.Windows.Forms.Button> conserva el ancho, pero el alto cambia para rellenar la celda verticalmente.</span><span class="sxs-lookup"><span data-stu-id="cf979-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf979-131">Este es el mismo comportamiento que se produce en otros controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="cf979-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6.  <span data-ttu-id="cf979-132">Cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control <xref:System.Windows.Forms.Button> a <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="cf979-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="cf979-133">El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.</span><span class="sxs-lookup"><span data-stu-id="cf979-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf979-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf979-134">Example</span></span>  
 <span data-ttu-id="cf979-135">La ilustración siguiente muestra cinco botones delimitados en cinco celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="cf979-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="cf979-136">![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="cf979-136">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="cf979-137">En la siguiente ilustración se muestran cuatro botones delimitados en las esquinas de cuatro celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="cf979-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="cf979-138">![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="cf979-138">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="cf979-139">En la ilustración siguiente se muestran tres botones estirados por delimitación en tres celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="cf979-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="cf979-140">![Delimitación de TableLayoutPanel](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="cf979-140">![TableLayoutPanel Anchoring](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="cf979-141">En el ejemplo de código siguiente se muestran todas las combinaciones de los valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="cf979-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf979-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cf979-142">Compiling the Code</span></span>  
 <span data-ttu-id="cf979-143">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="cf979-143">This example requires:</span></span>  
  
-   <span data-ttu-id="cf979-144">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="cf979-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="cf979-145">Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cf979-145">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cf979-146">También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="cf979-146">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="cf979-147">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="cf979-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf979-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf979-148">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="cf979-149">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="cf979-149">TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
