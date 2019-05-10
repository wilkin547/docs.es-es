---
title: 'Tutorial: Organizar contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: a8f690438136450cb12dbcf5e17ddfcca617457e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211454"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="ed63d-102">Tutorial: Organizar el contenido WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ed63d-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="ed63d-103">Este tutorial muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ed63d-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

<span data-ttu-id="ed63d-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed63d-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="ed63d-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed63d-105">Create the project.</span></span>

- <span data-ttu-id="ed63d-106">Crear el control WPF.</span><span class="sxs-lookup"><span data-stu-id="ed63d-106">Create the WPF control.</span></span>

- <span data-ttu-id="ed63d-107">Hospedar controles WPF en un panel de diseño.</span><span class="sxs-lookup"><span data-stu-id="ed63d-107">Host WPF controls in a layout panel.</span></span>

- <span data-ttu-id="ed63d-108">Usar líneas de ajuste para alinear os controles WPF.</span><span class="sxs-lookup"><span data-stu-id="ed63d-108">Use snaplines to align WPF controls.</span></span>

- <span data-ttu-id="ed63d-109">Delimitar y acoplar controles WPF.</span><span class="sxs-lookup"><span data-stu-id="ed63d-109">Anchor and dock WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed63d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ed63d-110">Prerequisites</span></span>

<span data-ttu-id="ed63d-111">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ed63d-111">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ed63d-112">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ed63d-112">Create the project</span></span>

<span data-ttu-id="ed63d-113">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# denominado `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-113">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="ed63d-114">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ed63d-114">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="ed63d-115">Crear el control WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-115">Create the WPF control</span></span>

<span data-ttu-id="ed63d-116">Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ed63d-116">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="ed63d-117">Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed63d-117">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="ed63d-118">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="ed63d-119">Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ed63d-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="ed63d-120">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ed63d-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="ed63d-121">Para obtener más información, vea [Cómo: Seleccionar y mover elementos en la superficie de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ed63d-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="ed63d-122">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="ed63d-123">Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-123">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

5. <span data-ttu-id="ed63d-124">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed63d-124">Build the project.</span></span>

## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="ed63d-125">Hospedar controles WPF en un panel de diseño</span><span class="sxs-lookup"><span data-stu-id="ed63d-125">Hosting WPF Controls in a Layout Panel</span></span>
 <span data-ttu-id="ed63d-126">Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ed63d-126">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="ed63d-127">Para hospedar controles WPF en un panel de diseño</span><span class="sxs-lookup"><span data-stu-id="ed63d-127">To host WPF controls in a layout panel</span></span>

1. <span data-ttu-id="ed63d-128">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ed63d-128">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="ed63d-129">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.TableLayoutPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="ed63d-129">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="ed63d-130">En el <xref:System.Windows.Forms.TableLayoutPanel> panel de etiquetas inteligentes del control, seleccione **quitar la última fila**.</span><span class="sxs-lookup"><span data-stu-id="ed63d-130">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="ed63d-131">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.</span><span class="sxs-lookup"><span data-stu-id="ed63d-131">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="ed63d-132">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ed63d-132">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="ed63d-133">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="ed63d-134">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia en la segunda celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ed63d-134">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="ed63d-135">En el **esquema del documento** ventana, seleccione `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-135">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="ed63d-136">Para obtener más información, consulte [ventana Esquema del documento](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span><span class="sxs-lookup"><span data-stu-id="ed63d-136">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>

8. <span data-ttu-id="ed63d-137">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-137">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>

     <span data-ttu-id="ed63d-138">Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.</span><span class="sxs-lookup"><span data-stu-id="ed63d-138">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="ed63d-139">Usar líneas de ajuste para alinear controles WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-139">Using Snaplines to Align WPF Controls</span></span>
 <span data-ttu-id="ed63d-140">Las líneas de ajuste permiten alinear fácilmente los controles en un formulario.</span><span class="sxs-lookup"><span data-stu-id="ed63d-140">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="ed63d-141">Puede usar líneas de ajuste para alinear también controles WPF.</span><span class="sxs-lookup"><span data-stu-id="ed63d-141">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="ed63d-142">Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="ed63d-142">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="ed63d-143">Para usar líneas de ajuste para alinear controles WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-143">To use snaplines to align WPF controls</span></span>

1. <span data-ttu-id="ed63d-144">Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario y colóquelo en el espacio debajo el <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="ed63d-144">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="ed63d-145">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-145">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="ed63d-146">Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-146">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="ed63d-147">Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-147">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="ed63d-148">Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.</span><span class="sxs-lookup"><span data-stu-id="ed63d-148">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="ed63d-149">En el **propiedades** ventana, establezca el valor de la propiedad Margin en `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-149">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>

6. <span data-ttu-id="ed63d-150">Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ed63d-150">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="ed63d-151">Ahora, la línea de ajuste central indica un margen de 20.</span><span class="sxs-lookup"><span data-stu-id="ed63d-151">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="ed63d-152">Mueva `elementHost3` hacia la derecha, hasta que su borde izquierdo quede alineado con el borde izquierdo de `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-152">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="ed63d-153">Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-153">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="ed63d-154">Delimitar y acoplar controles WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-154">Anchoring and Docking WPF Controls</span></span>
 <span data-ttu-id="ed63d-155">La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ed63d-155">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="ed63d-156">Para delimitar y acoplar controles WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-156">To anchor and dock WPF controls</span></span>

1. <span data-ttu-id="ed63d-157">Seleccione `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-157">Select `elementHost1`.</span></span>

2. <span data-ttu-id="ed63d-158">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad **superior, inferior, izquierda, derecha**.</span><span class="sxs-lookup"><span data-stu-id="ed63d-158">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="ed63d-159">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.</span><span class="sxs-lookup"><span data-stu-id="ed63d-159">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

     <span data-ttu-id="ed63d-160">El control `elementHost1` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="ed63d-160">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="ed63d-161">Seleccione `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-161">Select `elementHost2`.</span></span>

5. <span data-ttu-id="ed63d-162">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-162">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="ed63d-163">El control `elementHost2` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="ed63d-163">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="ed63d-164">Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-164">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="ed63d-165">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-165">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="ed63d-166">Seleccione `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="ed63d-166">Select `elementHost3`.</span></span>

9. <span data-ttu-id="ed63d-167">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="ed63d-167">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="ed63d-168">El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ed63d-168">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="ed63d-169">Cambie de tamaño el formulario.</span><span class="sxs-lookup"><span data-stu-id="ed63d-169">Resize the form.</span></span>

     <span data-ttu-id="ed63d-170">Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed63d-170">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

     <span data-ttu-id="ed63d-171">Para obtener más información, vea [Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="ed63d-171">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed63d-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed63d-172">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ed63d-173">Cómo: Delimitar y acoplar controles secundarios en un Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ed63d-173">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ed63d-174">Cómo: Alinear un Control con los bordes de formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="ed63d-174">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="ed63d-175">Tutorial: Organizar controles en formularios de Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="ed63d-175">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="ed63d-176">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="ed63d-176">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="ed63d-177">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="ed63d-177">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="ed63d-178">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed63d-178">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
