---
title: 'Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 062b9b943d187ccd4105f3772688c563f540d696
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846479"
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="c08db-102">Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c08db-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="c08db-103">Este tutorial muestra cómo usar las características de diseño de Windows Forms, como la delimitación y las líneas de ajuste, para organizar los controles de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c08db-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

 <span data-ttu-id="c08db-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c08db-104">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="c08db-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c08db-105">Create the project.</span></span>

-   <span data-ttu-id="c08db-106">Crear el control WPF.</span><span class="sxs-lookup"><span data-stu-id="c08db-106">Create the WPF control.</span></span>

-   <span data-ttu-id="c08db-107">Hospedar controles WPF en un panel de diseño.</span><span class="sxs-lookup"><span data-stu-id="c08db-107">Host WPF controls in a layout panel.</span></span>

-   <span data-ttu-id="c08db-108">Usar líneas de ajuste para alinear os controles WPF.</span><span class="sxs-lookup"><span data-stu-id="c08db-108">Use snaplines to align WPF controls.</span></span>

-   <span data-ttu-id="c08db-109">Delimitar y acoplar controles WPF.</span><span class="sxs-lookup"><span data-stu-id="c08db-109">Anchor and dock WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="c08db-110">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="c08db-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c08db-111">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="c08db-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c08db-112">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c08db-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c08db-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c08db-113">Prerequisites</span></span>  
 <span data-ttu-id="c08db-114">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="c08db-114">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="c08db-115">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="c08db-115">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c08db-116">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="c08db-116">Creating the Project</span></span>  
 <span data-ttu-id="c08db-117">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c08db-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c08db-118">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c08db-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="c08db-119">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="c08db-119">To create the project</span></span>  
  
-   <span data-ttu-id="c08db-120">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="c08db-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="c08db-121">Crear el control WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="c08db-122">Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c08db-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="c08db-123">Para crear controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-123">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="c08db-124">Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c08db-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="c08db-125">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="c08db-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="c08db-126">Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c08db-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="c08db-127">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c08db-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="c08db-128">Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="c08db-128">For more information, see [How to: Select and Move Elements on the Design Surface](https://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="c08db-129">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="c08db-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="c08db-130">Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.</span><span class="sxs-lookup"><span data-stu-id="c08db-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5.  <span data-ttu-id="c08db-131">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c08db-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="c08db-132">Hospedar controles WPF en un panel de diseño</span><span class="sxs-lookup"><span data-stu-id="c08db-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="c08db-133">Puede usar controles WPF en paneles de diseño de la misma forma que usa otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c08db-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="c08db-134">Para hospedar controles WPF en un panel de diseño</span><span class="sxs-lookup"><span data-stu-id="c08db-134">To host WPF controls in a layout panel</span></span>  
  
1.  <span data-ttu-id="c08db-135">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c08db-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="c08db-136">En el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.TableLayoutPanel> al formulario.</span><span class="sxs-lookup"><span data-stu-id="c08db-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3.  <span data-ttu-id="c08db-137">En el <xref:System.Windows.Forms.TableLayoutPanel> panel de etiquetas inteligentes del control, seleccione **quitar la última fila**.</span><span class="sxs-lookup"><span data-stu-id="c08db-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4.  <span data-ttu-id="c08db-138">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un ancho y alto mayor.</span><span class="sxs-lookup"><span data-stu-id="c08db-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5.  <span data-ttu-id="c08db-139">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en la primera celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="c08db-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="c08db-140">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c08db-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6.  <span data-ttu-id="c08db-141">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear otra instancia en la segunda celda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="c08db-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="c08db-142">En el **esquema del documento** ventana, seleccione `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="c08db-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="c08db-143">Para obtener más información, consulte [ventana Esquema del documento](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span><span class="sxs-lookup"><span data-stu-id="c08db-143">For more information, see [Document Outline Window](https://msdn.microsoft.com/library/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span></span>  
  
8.  <span data-ttu-id="c08db-144">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Padding%2A> propiedad `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="c08db-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="c08db-145">Ambos controles <xref:System.Windows.Forms.Integration.ElementHost> cambian de tamaño para ajustarse al nuevo diseño.</span><span class="sxs-lookup"><span data-stu-id="c08db-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="c08db-146">Usar líneas de ajuste para alinear controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="c08db-147">Las líneas de ajuste permiten alinear fácilmente los controles en un formulario.</span><span class="sxs-lookup"><span data-stu-id="c08db-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="c08db-148">Puede usar líneas de ajuste para alinear también controles WPF.</span><span class="sxs-lookup"><span data-stu-id="c08db-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="c08db-149">Para obtener más información, consulte [Tutorial: organizar controles en Windows Forms utilizando las guías de alineación](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="c08db-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="c08db-150">Para usar líneas de ajuste para alinear controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-150">To use snaplines to align WPF controls</span></span>  
  
1.  <span data-ttu-id="c08db-151">Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario y colóquelo en el espacio debajo el <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="c08db-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="c08db-152">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="c08db-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2.  <span data-ttu-id="c08db-153">Use las líneas de ajuste para alinear el borde izquierdo de `elementHost3` con el borde izquierdo del control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c08db-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="c08db-154">Use las líneas de ajuste para ajustar el tamaño de `elementHost3` al mismo ancho que el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c08db-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="c08db-155">Mueva `elementHost3` hacia el control <xref:System.Windows.Forms.TableLayoutPanel> hasta que aparezca una línea de ajuste central entre los controles.</span><span class="sxs-lookup"><span data-stu-id="c08db-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5.  <span data-ttu-id="c08db-156">En el **propiedades** ventana, establezca el valor de la propiedad Margin en `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="c08db-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6.  <span data-ttu-id="c08db-157">Aleje `elementHost3` del control <xref:System.Windows.Forms.TableLayoutPanel> hasta que la línea de ajuste central aparezca de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c08db-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="c08db-158">Ahora, la línea de ajuste central indica un margen de 20.</span><span class="sxs-lookup"><span data-stu-id="c08db-158">The center snapline now indicates a margin of 20.</span></span>  
  
7.  <span data-ttu-id="c08db-159">Mueva `elementHost3` hacia la derecha, hasta que su borde izquierdo quede alineado con el borde izquierdo de `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c08db-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8.  <span data-ttu-id="c08db-160">Cambie el ancho de `elementHost3` hasta que su borde derecho quede alineado con el borde derecho de `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="c08db-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="c08db-161">Delimitar y acoplar controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="c08db-162">La delimitación y el acoplamiento de un control WPF hospedado en un formulario se comportan igual que los de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c08db-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="c08db-163">Para delimitar y acoplar controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-163">To anchor and dock WPF controls</span></span>  
  
1.  <span data-ttu-id="c08db-164">Seleccione `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c08db-164">Select `elementHost1`.</span></span>  
  
2.  <span data-ttu-id="c08db-165">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad **superior, inferior, izquierda, derecha**.</span><span class="sxs-lookup"><span data-stu-id="c08db-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3.  <span data-ttu-id="c08db-166">Cambie el tamaño del control <xref:System.Windows.Forms.TableLayoutPanel> a un tamaño mayor.</span><span class="sxs-lookup"><span data-stu-id="c08db-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="c08db-167">El control `elementHost1` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="c08db-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4.  <span data-ttu-id="c08db-168">Seleccione `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="c08db-168">Select `elementHost2`.</span></span>  
  
5.  <span data-ttu-id="c08db-169">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c08db-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="c08db-170">El control `elementHost2` cambia de tamaño para llenar la celda.</span><span class="sxs-lookup"><span data-stu-id="c08db-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6.  <span data-ttu-id="c08db-171">Seleccione el control <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c08db-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="c08db-172">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="c08db-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8.  <span data-ttu-id="c08db-173">Seleccione `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="c08db-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="c08db-174">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c08db-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="c08db-175">El control `elementHost3` cambia de tamaño para llenar el espacio restante en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c08db-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="c08db-176">Cambie de tamaño el formulario.</span><span class="sxs-lookup"><span data-stu-id="c08db-176">Resize the form.</span></span>  
  
     <span data-ttu-id="c08db-177">Los tres controles <xref:System.Windows.Forms.Integration.ElementHost> ajustan su tamaño correctamente.</span><span class="sxs-lookup"><span data-stu-id="c08db-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="c08db-178">Para obtener más información, consulte [Cómo: delimitador y acoplar controles secundarios en un TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="c08db-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08db-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="c08db-179">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c08db-180">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c08db-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="c08db-181">Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="c08db-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="c08db-182">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="c08db-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="c08db-183">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="c08db-183">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="c08db-184">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="c08db-184">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="c08db-185">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c08db-185">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
