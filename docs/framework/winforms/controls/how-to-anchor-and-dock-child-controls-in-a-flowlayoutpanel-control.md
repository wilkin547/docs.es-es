---
title: Procedimiento para delimitar y acoplar controles secundarios en un control FlowLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: f51878ed0a0f0e888074d170686b94f086c6d376
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612941"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="05600-102">Procedimiento para delimitar y acoplar controles secundarios en un control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="05600-102">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>
<span data-ttu-id="05600-103">El control <xref:System.Windows.Forms.FlowLayoutPanel> admite las propiedades <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> en sus controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="05600-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="05600-104">Para delimitar y acoplar controles secundarios en un control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="05600-104">To anchor and dock child controls in a FlowLayoutPanel control</span></span>  
  
1. <span data-ttu-id="05600-105">Cree un control <xref:System.Windows.Forms.FlowLayoutPanel> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="05600-105">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>  
  
2. <span data-ttu-id="05600-106">Establecer el <xref:System.Windows.Forms.Control.Width%2A> de la <xref:System.Windows.Forms.FlowLayoutPanel> el control a **300**y establezca su <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> a <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="05600-106">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
3. <span data-ttu-id="05600-107">Cree dos controles <xref:System.Windows.Forms.Button> y colóquelos en el control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-107">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
4. <span data-ttu-id="05600-108">Establecer el <xref:System.Windows.Forms.Control.Width%2A> del primer botón en **200**.</span><span class="sxs-lookup"><span data-stu-id="05600-108">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>  
  
5. <span data-ttu-id="05600-109">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="05600-109">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05600-110">El segundo botón toma el mismo ancho que el primer botón.</span><span class="sxs-lookup"><span data-stu-id="05600-110">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="05600-111">No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-111">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
6. <span data-ttu-id="05600-112">Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del segundo botón en `None`.</span><span class="sxs-lookup"><span data-stu-id="05600-112">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="05600-113">Esto hace que el botón tome su ancho original.</span><span class="sxs-lookup"><span data-stu-id="05600-113">This causes the button to assume its original width.</span></span>  
  
7. <span data-ttu-id="05600-114">Establezca la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del segundo botón en `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="05600-114">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="05600-115">El segundo botón toma el mismo ancho que el primer botón.</span><span class="sxs-lookup"><span data-stu-id="05600-115">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="05600-116">No se ajusta a lo ancho del control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-116">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="05600-117">Esta es la regla general para delimitar y acoplar en el control <xref:System.Windows.Forms.FlowLayoutPanel>: para direcciones de flujo verticales, el control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el ancho de una columna implícita a partir del control secundario más ancho de la columna.</span><span class="sxs-lookup"><span data-stu-id="05600-117">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="05600-118">Todos los demás controles de esta columna con propiedades <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> se alinean o cambian de tamaño para ajustarse a esta columna implícita.</span><span class="sxs-lookup"><span data-stu-id="05600-118">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="05600-119">El comportamiento funciona de forma similar para las direcciones de flujo horizontales.</span><span class="sxs-lookup"><span data-stu-id="05600-119">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="05600-120">El control <xref:System.Windows.Forms.FlowLayoutPanel> calcula el alto de una fila implícita a partir del control secundario más alto de la fila, y todos los controles secundarios delimitados o acoplados de esta fila se alinean o cambian de tamaño para ajustarse a la fila implícita.</span><span class="sxs-lookup"><span data-stu-id="05600-120">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05600-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05600-121">Example</span></span>  
 <span data-ttu-id="05600-122">La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-122">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="05600-123">El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span><span class="sxs-lookup"><span data-stu-id="05600-123">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>  
  
 <span data-ttu-id="05600-124">![Delimitación de FlowLayoutPanel](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="05600-124">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>  
  
 <span data-ttu-id="05600-125">La ilustración siguiente muestra cuatro botones que se delimitan y se acoplan con relación al botón azul en un <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-125">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="05600-126">El valor de <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> es <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="05600-126">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>  
  
 <span data-ttu-id="05600-127">![Delimitación de FlowLayoutPanel](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="05600-127">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>  
  
 <span data-ttu-id="05600-128">En el ejemplo de código siguiente se muestran varios valores de propiedad <xref:System.Windows.Forms.Control.Anchor%2A> para un control <xref:System.Windows.Forms.Button> en un control <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="05600-128">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="05600-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="05600-129">Compiling the Code</span></span>  
 <span data-ttu-id="05600-130">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="05600-130">This example requires:</span></span>  
  
- <span data-ttu-id="05600-131">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="05600-131">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="05600-132">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="05600-132">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="05600-133">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="05600-133">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05600-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="05600-134">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="05600-135">Información general sobre el control FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="05600-135">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
