---
title: Procedimiento para delimitar y acoplar controles secundarios en un control TableLayoutPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: 7adbf9a98b25b237ee49d2689154e903d8fc0b5a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586174"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a><span data-ttu-id="d0dc9-102">Procedimiento para delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d0dc9-102">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>
<span data-ttu-id="d0dc9-103">El control <xref:System.Windows.Forms.TableLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-103">The <xref:System.Windows.Forms.TableLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="d0dc9-104">Para alinear un control secundario en una celda de TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d0dc9-104">To align a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="d0dc9-105">Cree un control <xref:System.Windows.Forms.TableLayoutPanel> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-105">Create a <xref:System.Windows.Forms.TableLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="d0dc9-106">Establezca el valor de la <xref:System.Windows.Forms.TableLayoutPanel> del control <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> y <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> propiedades a **1**.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-106">Set the value of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> and <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> properties to **1**.</span></span>  
  
3. <span data-ttu-id="d0dc9-107">Cree un control <xref:System.Windows.Forms.Button> en el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-107">Create a <xref:System.Windows.Forms.Button> control in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="d0dc9-108">El <xref:System.Windows.Forms.Button> ocupa la esquina superior izquierda de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-108">The <xref:System.Windows.Forms.Button> occupies the upper-left corner of the cell.</span></span>  
  
4. <span data-ttu-id="d0dc9-109">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `Left`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-109">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left`.</span></span> <span data-ttu-id="d0dc9-110">El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-110">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0dc9-111">Este comportamiento difiere del comportamiento de otros controles contenedor.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-111">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="d0dc9-112">En otros controles contenedor, el control secundario no mueve cuando se establece la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> y la distancia entre el control delimitado y el límite del contenedor primario se fija en el momento de establecer la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-112">In other container controls, the child control does not move when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set, and the distance between the anchored control and the parent container's boundary is fixed at the time the <xref:System.Windows.Forms.Control.Anchor%2A> property is set.</span></span>  
  
5. <span data-ttu-id="d0dc9-113">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-113">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span> <span data-ttu-id="d0dc9-114">El control <xref:System.Windows.Forms.Button> se mueve para ocupar la esquina superior izquierda de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-114">The <xref:System.Windows.Forms.Button> control moves to occupy the top-left corner of the cell.</span></span>  
  
6. <span data-ttu-id="d0dc9-115">Repita el paso 5 con un valor de `Top, Right` para mover el <xref:System.Windows.Forms.Button> control a la esquina superior derecha de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-115">Repeat step 5 with a value of `Top, Right` to move the <xref:System.Windows.Forms.Button> control to the top-right corner of the cell.</span></span> <span data-ttu-id="d0dc9-116">Repita con los valores de `Bottom, Left` e `Bottom, Right`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-116">Repeat with values of `Bottom, Left` and `Bottom, Right`.</span></span>  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a><span data-ttu-id="d0dc9-117">Para ajustar un control secundario en una celda de TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d0dc9-117">To stretch a child control in a TableLayoutPanel cell</span></span>  
  
1. <span data-ttu-id="d0dc9-118">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-118">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left, Right`.</span></span> <span data-ttu-id="d0dc9-119">El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al ancho de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-119">The <xref:System.Windows.Forms.Button> control is resized to stretch across the cell.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0dc9-120">Este comportamiento difiere del comportamiento de otros controles contenedor.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-120">This behavior differs from the behavior of other container controls.</span></span> <span data-ttu-id="d0dc9-121">En otros controles contenedor, el control secundario no es cambia de tamaño cuando el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad está establecida en `Left, Right` o `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-121">In other container controls, the child control is not resized when the <xref:System.Windows.Forms.Control.Anchor%2A> property is set to `Left, Right` or `Top, Bottom`.</span></span>  
  
2. <span data-ttu-id="d0dc9-122">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `Top, Bottom`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-122">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom`.</span></span> <span data-ttu-id="d0dc9-123">El control <xref:System.Windows.Forms.Button> cambia de tamaño para ajustarse al alto de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-123">The <xref:System.Windows.Forms.Button> control is resized to stretch from the top to the bottom of the cell.</span></span>  
  
3. <span data-ttu-id="d0dc9-124">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `Top, Bottom, Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-124">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Bottom, Left, Right`.</span></span> <span data-ttu-id="d0dc9-125">El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-125">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
4. <span data-ttu-id="d0dc9-126">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> a `None`.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-126">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `None`.</span></span> <span data-ttu-id="d0dc9-127">El control <xref:System.Windows.Forms.Button> cambia de tamaño y se centra en la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-127">The <xref:System.Windows.Forms.Button> control is resized and centered in the cell.</span></span>  
  
5. <span data-ttu-id="d0dc9-128">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Left>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-128">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span> <span data-ttu-id="d0dc9-129">El control <xref:System.Windows.Forms.Button> se mueve para alinearse con el borde izquierdo de la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-129">The <xref:System.Windows.Forms.Button> control moves to align with the left border of the cell.</span></span> <span data-ttu-id="d0dc9-130">El control <xref:System.Windows.Forms.Button> conserva el ancho, pero el alto cambia para rellenar la celda verticalmente.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-130">The <xref:System.Windows.Forms.Button> control retains its width, but its height is resized to fill the cell vertically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0dc9-131">Este es el mismo comportamiento que se produce en otros controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-131">This is the same behavior that occurs in other container controls.</span></span>  
  
6. <span data-ttu-id="d0dc9-132">Cambie el valor de la propiedad <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-132">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="d0dc9-133">El control <xref:System.Windows.Forms.Button> cambia de tamaño para rellenar la celda.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-133">The <xref:System.Windows.Forms.Button> control is resized to fill the cell.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0dc9-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0dc9-134">Example</span></span>  
 <span data-ttu-id="d0dc9-135">La ilustración siguiente muestra cinco botones delimitados en cinco celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-135">The following illustration shows five buttons anchored in five separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d0dc9-136">![Delimitación de TableLayoutPanel](./media/vs-tlpanchor.gif "VS_TLPanchor")</span><span class="sxs-lookup"><span data-stu-id="d0dc9-136">![TableLayoutPanel Anchoring](./media/vs-tlpanchor.gif "VS_TLPanchor")</span></span>  
  
 <span data-ttu-id="d0dc9-137">En la siguiente ilustración se muestran cuatro botones delimitados en las esquinas de cuatro celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-137">The following illustration shows four buttons anchored in the corners of four separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d0dc9-138">![Delimitación de TableLayoutPanel](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="d0dc9-138">![TableLayoutPanel Anchoring](./media/vs-tlpanchor2.gif "VS_TLPanchor2")</span></span>  
  
 <span data-ttu-id="d0dc9-139">En la ilustración siguiente se muestran tres botones estirados por delimitación en tres celdas diferentes de <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-139">The following illustration shows three buttons stretched by anchoring in three separate <xref:System.Windows.Forms.TableLayoutPanel> cells.</span></span>  
  
 <span data-ttu-id="d0dc9-140">![Delimitación de TableLayoutPanel](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span><span class="sxs-lookup"><span data-stu-id="d0dc9-140">![TableLayoutPanel Anchoring](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")</span></span>  
  
 <span data-ttu-id="d0dc9-141">En el ejemplo de código siguiente se muestran todas las combinaciones de los valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-141">The following code example demonstrates all the combinations of <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0dc9-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d0dc9-142">Compiling the Code</span></span>  
 <span data-ttu-id="d0dc9-143">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="d0dc9-143">This example requires:</span></span>  
  
- <span data-ttu-id="d0dc9-144">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="d0dc9-144">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0dc9-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0dc9-145">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="d0dc9-146">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="d0dc9-146">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
