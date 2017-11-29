---
title: "Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cfbe9957fa8d18f839ae656ca721c4ee88475a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="51dda-102">Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="51dda-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="51dda-103">En este tema se muestra cómo crear un control de Windows Presentation Foundation (WPF) para usarlo en aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="51dda-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="51dda-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="51dda-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="51dda-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="51dda-105">Create the project.</span></span>  
  
-   <span data-ttu-id="51dda-106">Crear un nuevo control WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="51dda-107">Agregar el nuevo control WPF a un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="51dda-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="51dda-108">El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="51dda-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51dda-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="51dda-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="51dda-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="51dda-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="51dda-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="51dda-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51dda-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="51dda-112">Prerequisites</span></span>  
 <span data-ttu-id="51dda-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="51dda-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="51dda-114">.</span><span class="sxs-lookup"><span data-stu-id="51dda-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="51dda-115">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="51dda-115">Creating the Project</span></span>  
 <span data-ttu-id="51dda-116">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="51dda-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51dda-117">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="51dda-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="51dda-118">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="51dda-118">To create the project</span></span>  
  
-   <span data-ttu-id="51dda-119">Crear un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="51dda-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="51dda-120">Crear un nuevo control WPF</span><span class="sxs-lookup"><span data-stu-id="51dda-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="51dda-121">Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto.</span><span class="sxs-lookup"><span data-stu-id="51dda-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="51dda-122">El Diseñador de Windows Forms funciona con un tipo determinado de control denominado *control compuesto*, o *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="51dda-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="51dda-123">Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="51dda-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51dda-124">El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51dda-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="51dda-125">Para crear un nuevo control WPF</span><span class="sxs-lookup"><span data-stu-id="51dda-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="51dda-126">En **el Explorador de soluciones**, agregue un nuevo **biblioteca de controles de usuario de WPF** proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="51dda-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="51dda-127">Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="51dda-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="51dda-128">El nombre predeterminado del control es `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="51dda-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="51dda-129">Agregar el nuevo control tiene los siguientes efectos.</span><span class="sxs-lookup"><span data-stu-id="51dda-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="51dda-130">Se agrega el archivo UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="51dda-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="51dda-131">Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="51dda-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="51dda-132">Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.</span><span class="sxs-lookup"><span data-stu-id="51dda-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="51dda-133">Se agregan referencias a ensamblados de WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="51dda-134">Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51dda-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="51dda-135">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="51dda-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="51dda-136">Para obtener más información, consulte [Cómo: seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="51dda-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="51dda-137">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para `200`.</span><span class="sxs-lookup"><span data-stu-id="51dda-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="51dda-138">Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="51dda-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="51dda-139">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="51dda-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51dda-140">Por lo general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="51dda-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="51dda-141">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="51dda-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="51dda-142">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="51dda-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="51dda-143">Agregar un control WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="51dda-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="51dda-144">El nuevo control WPF está listo para usarse en el formulario.</span><span class="sxs-lookup"><span data-stu-id="51dda-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="51dda-145">Windows Forms usa el control <xref:System.Windows.Forms.Integration.ElementHost> para hospedar contenido WPF</span><span class="sxs-lookup"><span data-stu-id="51dda-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="51dda-146">Para agregar un control WPF a un Windows Form</span><span class="sxs-lookup"><span data-stu-id="51dda-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="51dda-147">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="51dda-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="51dda-148">En el **cuadro de herramientas**, busque la pestaña etiquetada como **controles de usuario de WPF WPFUserControlLibrary**.</span><span class="sxs-lookup"><span data-stu-id="51dda-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="51dda-149">Arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="51dda-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="51dda-150">Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="51dda-151">El <xref:System.Windows.Forms.Integration.ElementHost> se denomina control `elementHost1` y en el **propiedades** ventana, puede ver su <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="51dda-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="51dda-152">Se agregan referencias a ensamblados de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="51dda-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="51dda-153">El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="51dda-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="51dda-154">En el **tareas de ElementHost** panel de etiquetas inteligentes, seleccione **acoplar en contenedor principal**.</span><span class="sxs-lookup"><span data-stu-id="51dda-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="51dda-155">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="51dda-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="51dda-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="51dda-156">Next Steps</span></span>  
 <span data-ttu-id="51dda-157">Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente.</span><span class="sxs-lookup"><span data-stu-id="51dda-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="51dda-158">Para proporcionar un aspecto y un comportamiento más enriquecido a sus aplicaciones, pruebe lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="51dda-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="51dda-159">Hospede un control de Windows Forms en una página WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="51dda-160">Para obtener más información, consulte [Tutorial: hospedar un Control de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="51dda-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="51dda-161">Aplique estilos visuales de Windows Forms a su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="51dda-162">Para más información, vea [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="51dda-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="51dda-163">Cambie el estilo de su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="51dda-163">Change the style of your WPF content.</span></span> <span data-ttu-id="51dda-164">Para obtener más información, consulte [Tutorial: aplicar estilos a contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="51dda-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51dda-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="51dda-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="51dda-166">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="51dda-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="51dda-167">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="51dda-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="51dda-168">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="51dda-168">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
