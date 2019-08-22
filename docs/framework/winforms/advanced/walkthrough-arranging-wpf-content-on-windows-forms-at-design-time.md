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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658522"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="9c3e7-102">Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9c3e7-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="9c3e7-103">En este artículo se muestra cómo usar las características de diseño Windows Forms, como la delimitación y las guías de alineación, para organizar controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9c3e7-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c3e7-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c3e7-104">Prerequisites</span></span>

<span data-ttu-id="9c3e7-105">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="9c3e7-106">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="9c3e7-106">Create the project</span></span>

<span data-ttu-id="9c3e7-107">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o `ArrangeElementHost`en Visual denominado.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="9c3e7-108">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="9c3e7-109">Crear el control WPF</span><span class="sxs-lookup"><span data-stu-id="9c3e7-109">Create the WPF control</span></span>

<span data-ttu-id="9c3e7-110">Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="9c3e7-111">Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="9c3e7-112">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="9c3e7-113">Para obtener más información, vea [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)de diseño.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="9c3e7-114">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="9c3e7-115">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="9c3e7-116">Establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad en **azul**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="9c3e7-117">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="9c3e7-118">Hospedar controles WPF en un panel de diseño</span><span class="sxs-lookup"><span data-stu-id="9c3e7-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="9c3e7-119">Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="9c3e7-120">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="9c3e7-121">En el **cuadro de herramientas**, <xref:System.Windows.Forms.TableLayoutPanel> arrastre un control al formulario.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="9c3e7-122">En el <xref:System.Windows.Forms.TableLayoutPanel> panel de etiquetas inteligentes del control, seleccione **quitar última fila**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="9c3e7-123">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="9c3e7-124">En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear `UserControl1` una instancia de en la primera <xref:System.Windows.Forms.TableLayoutPanel> celda del control.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="9c3e7-125">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="9c3e7-126">En el **cuadro de herramientas**, haga `UserControl1` doble clic en para crear otra instancia en la <xref:System.Windows.Forms.TableLayoutPanel> segunda celda del control.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="9c3e7-127">En la ventana **esquema del documento** , `tableLayoutPanel1`seleccione.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="9c3e7-128">En la ventana **propiedades** , establezca el valor de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad en **10, 10, 10, 10**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="9c3e7-129">Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="9c3e7-130">Usar líneas de ajuste para alinear controles WPF</span><span class="sxs-lookup"><span data-stu-id="9c3e7-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="9c3e7-131">Las líneas de ajuste permiten alinear fácilmente los controles en un formulario.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="9c3e7-132">Puede usar líneas de ajuste para alinear también controles WPF.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="9c3e7-133">Para obtener más información, vea [Tutorial: Organizar controles en Windows Forms mediante las líneas](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)de ajuste.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="9c3e7-134">En el **cuadro de herramientas**, arrastre una `UserControl1` instancia de al formulario y colóquela en el espacio situado debajo del <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="9c3e7-135">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="9c3e7-136">Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="9c3e7-137">Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="9c3e7-138">Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="9c3e7-139">En la ventana **propiedades** , establezca el valor de la propiedad margin en **20, 20, 20, 20**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="9c3e7-140">Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="9c3e7-141">Ahora, la línea de ajuste central indica un margen de 20.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="9c3e7-142">Moverse `elementHost3` a la derecha hasta que su margen izquierdo se alinee con el borde izquierdo `elementHost1`de.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="9c3e7-143">Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="9c3e7-144">Delimitar y acoplar controles WPF</span><span class="sxs-lookup"><span data-stu-id="9c3e7-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="9c3e7-145">La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="9c3e7-146">Seleccione `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="9c3e7-147">En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.Control.Anchor%2A> propiedad en **superior, inferior, izquierda, derecha**.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="9c3e7-148">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="9c3e7-149">El control `elementHost1` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="9c3e7-150">Seleccione `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="9c3e7-151">En la ventana **propiedades** , establezca el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="9c3e7-152">El control `elementHost2` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="9c3e7-153">Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="9c3e7-154">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="9c3e7-155">Seleccione `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="9c3e7-156">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="9c3e7-157">El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="9c3e7-158">Cambie de tamaño el formulario.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-158">Resize the form.</span></span>

    <span data-ttu-id="9c3e7-159">Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="9c3e7-160">Para obtener más información, consulte [Cómo Delimite y acople los controles secundarios en](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)un control TableLayoutPanel.</span><span class="sxs-lookup"><span data-stu-id="9c3e7-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c3e7-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c3e7-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9c3e7-162">Procedimientos: Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="9c3e7-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="9c3e7-163">Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="9c3e7-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="9c3e7-164">Tutorial: Organizar controles en Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="9c3e7-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="9c3e7-165">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="9c3e7-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="9c3e7-166">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="9c3e7-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="9c3e7-167">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9c3e7-167">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
