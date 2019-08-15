---
title: 'Tutorial: Crear contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 889e81053d4e2264755468446a4e1681216ae22e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040375"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="565a1-102">Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="565a1-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="565a1-103">En este artículo se muestra cómo crear un control de Windows Presentation Foundation (WPF) para su uso en las aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="565a1-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="565a1-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="565a1-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="565a1-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="565a1-105">Create the project.</span></span>

- <span data-ttu-id="565a1-106">Crear un nuevo control WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-106">Create a new WPF control.</span></span>

- <span data-ttu-id="565a1-107">Agregar el nuevo control WPF a un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="565a1-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="565a1-108">El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="565a1-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="565a1-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="565a1-109">Prerequisites</span></span>

<span data-ttu-id="565a1-110">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="565a1-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="565a1-111">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="565a1-111">Visual Studio</span></span>

## <a name="create-the-project"></a><span data-ttu-id="565a1-112">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="565a1-112">Create the project</span></span>

<span data-ttu-id="565a1-113">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="565a1-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="565a1-114">Abra Visual Studio y cree un nuevo proyecto de **Windows Forms App (.NET Framework)** en Visual Basic o C# en `HostingWpf`visual denominado.</span><span class="sxs-lookup"><span data-stu-id="565a1-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="565a1-115">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="565a1-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="565a1-116">Crear un nuevo control WPF</span><span class="sxs-lookup"><span data-stu-id="565a1-116">Create a new WPF control</span></span>

<span data-ttu-id="565a1-117">Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto.</span><span class="sxs-lookup"><span data-stu-id="565a1-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="565a1-118">El Diseñador de Windows Forms funciona con un tipo determinado de control denominado *control compuesto*o *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="565a1-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="565a1-119">Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="565a1-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="565a1-120">El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="565a1-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="565a1-121">Para crear un control de WPF nuevo:</span><span class="sxs-lookup"><span data-stu-id="565a1-121">To create a new WPF control:</span></span>

1. <span data-ttu-id="565a1-122">En **Explorador de soluciones**, agregue un nuevo proyecto **biblioteca de controles de usuario (.NET Framework) de WPF** a la solución.</span><span class="sxs-lookup"><span data-stu-id="565a1-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="565a1-123">Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="565a1-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="565a1-124">El nombre predeterminado del control es `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="565a1-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="565a1-125">Agregar el nuevo control tiene los siguientes efectos:</span><span class="sxs-lookup"><span data-stu-id="565a1-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="565a1-126">Se agrega el archivo UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="565a1-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="565a1-127">Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="565a1-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="565a1-128">Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.</span><span class="sxs-lookup"><span data-stu-id="565a1-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="565a1-129">Se agregan referencias a ensamblados de WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="565a1-130">Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="565a1-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="565a1-131">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="565a1-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="565a1-132">Para obtener más información, consulte [Cómo Seleccione y mueva los elementos en el](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="565a1-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="565a1-133">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.</span><span class="sxs-lookup"><span data-stu-id="565a1-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="565a1-134">En el **cuadro de herramientas**, <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> arrastre un control hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="565a1-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="565a1-135">En la ventana **propiedades** , establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad en **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="565a1-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="565a1-136">Por lo general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="565a1-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="565a1-137">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="565a1-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="565a1-138">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="565a1-138">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="565a1-139">Agregar un control WPF a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="565a1-139">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="565a1-140">El nuevo control WPF está listo para usarse en el formulario.</span><span class="sxs-lookup"><span data-stu-id="565a1-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="565a1-141">Windows Forms usa el <xref:System.Windows.Forms.Integration.ElementHost> control para hospedar contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="565a1-142">Para agregar un control de WPF a un Windows Form:</span><span class="sxs-lookup"><span data-stu-id="565a1-142">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="565a1-143">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="565a1-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="565a1-144">En el **cuadro de herramientas**, busque la pestaña etiquetada **WPFUserControlLibrary control de usuario de WPF**.</span><span class="sxs-lookup"><span data-stu-id="565a1-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="565a1-145">Arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="565a1-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="565a1-146">Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="565a1-147">El <xref:System.Windows.Forms.Integration.ElementHost> control se denomina `elementHost1` y, en la ventana **propiedades** , puede ver que <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> su propiedad está establecida en **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="565a1-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="565a1-148">Se agregan referencias a ensamblados de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="565a1-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="565a1-149">El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="565a1-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="565a1-150">En el panel de etiquetas inteligentes **tareas de ElementHost** , seleccione **acoplar en contenedor primario**.</span><span class="sxs-lookup"><span data-stu-id="565a1-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="565a1-151">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="565a1-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="565a1-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="565a1-152">Next steps</span></span>

<span data-ttu-id="565a1-153">Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente.</span><span class="sxs-lookup"><span data-stu-id="565a1-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="565a1-154">Para proporcionar una apariencia y un comportamiento más completos en las aplicaciones, intente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="565a1-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="565a1-155">Hospede un control de Windows Forms en una página WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="565a1-156">Para obtener más información, vea [Tutorial: Hospedar un control de Windows Forms](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)en WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="565a1-157">Aplique estilos visuales de Windows Forms a su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="565a1-158">Para obtener más información, consulte [Cómo Habilitar estilos visuales en una aplicación](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)híbrida.</span><span class="sxs-lookup"><span data-stu-id="565a1-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="565a1-159">Cambie el estilo de su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-159">Change the style of your WPF content.</span></span> <span data-ttu-id="565a1-160">Para obtener más información, vea [Tutorial: Aplicar estilos al](walkthrough-styling-wpf-content.md)contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="565a1-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="565a1-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="565a1-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="565a1-162">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="565a1-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="565a1-163">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="565a1-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="565a1-164">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="565a1-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
