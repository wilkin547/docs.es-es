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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e3fb6e42270cc0a530646b656470ec99fcfc7f1f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666246"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="48d62-102">Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="48d62-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="48d62-103">En este artículo se muestra cómo crear un control de Windows Presentation Foundation (WPF) para su uso en las aplicaciones basadas en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="48d62-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48d62-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="48d62-104">Prerequisites</span></span>

<span data-ttu-id="48d62-105">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="48d62-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="48d62-106">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="48d62-106">Create the project</span></span>

<span data-ttu-id="48d62-107">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="48d62-107">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="48d62-108">Abra Visual Studio y cree un nuevo proyecto de **Windows Forms App (.NET Framework)** en Visual Basic o C# en `HostingWpf`visual denominado.</span><span class="sxs-lookup"><span data-stu-id="48d62-108">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="48d62-109">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48d62-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="48d62-110">Crear un nuevo control WPF</span><span class="sxs-lookup"><span data-stu-id="48d62-110">Create a new WPF control</span></span>

<span data-ttu-id="48d62-111">Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto.</span><span class="sxs-lookup"><span data-stu-id="48d62-111">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="48d62-112">El Diseñador de Windows Forms funciona con un tipo determinado de control denominado *control compuesto*o *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="48d62-112">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="48d62-113">Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="48d62-113">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="48d62-114">El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="48d62-114">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="48d62-115">Para crear un control de WPF nuevo:</span><span class="sxs-lookup"><span data-stu-id="48d62-115">To create a new WPF control:</span></span>

1. <span data-ttu-id="48d62-116">En **Explorador de soluciones**, agregue un nuevo proyecto **biblioteca de controles de usuario (.NET Framework) de WPF** a la solución.</span><span class="sxs-lookup"><span data-stu-id="48d62-116">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="48d62-117">Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`.</span><span class="sxs-lookup"><span data-stu-id="48d62-117">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="48d62-118">El nombre predeterminado del control es `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="48d62-118">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="48d62-119">Agregar el nuevo control tiene los siguientes efectos:</span><span class="sxs-lookup"><span data-stu-id="48d62-119">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="48d62-120">Se agrega el archivo UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="48d62-120">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="48d62-121">Se agrega el archivo UserControl1.xaml.cs (o UserControl1. Xaml. VB).</span><span class="sxs-lookup"><span data-stu-id="48d62-121">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="48d62-122">Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.</span><span class="sxs-lookup"><span data-stu-id="48d62-122">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="48d62-123">Se agregan referencias a ensamblados de WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-123">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="48d62-124">El archivo UserControl1. XAML se abre en WPF Designer para Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="48d62-124">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="48d62-125">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="48d62-125">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="48d62-126">En la ventana **propiedades** , establezca el valor de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y en **200**.</span><span class="sxs-lookup"><span data-stu-id="48d62-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="48d62-127">En el **cuadro de herramientas**, <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> arrastre un control hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="48d62-127">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="48d62-128">En la ventana **propiedades** , establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad en **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="48d62-128">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48d62-129">Por lo general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="48d62-129">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="48d62-130">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="48d62-130">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="48d62-131">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="48d62-131">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="48d62-132">Agregar un control WPF a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48d62-132">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="48d62-133">El nuevo control WPF está listo para usarse en el formulario.</span><span class="sxs-lookup"><span data-stu-id="48d62-133">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="48d62-134">Windows Forms usa el <xref:System.Windows.Forms.Integration.ElementHost> control para hospedar contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-134">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="48d62-135">Para agregar un control de WPF a un Windows Form:</span><span class="sxs-lookup"><span data-stu-id="48d62-135">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="48d62-136">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="48d62-136">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="48d62-137">En el **cuadro de herramientas**, busque la pestaña etiquetada **WPFUserControlLibrary control de usuario de WPF**.</span><span class="sxs-lookup"><span data-stu-id="48d62-137">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="48d62-138">Arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="48d62-138">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="48d62-139">Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-139">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="48d62-140">El <xref:System.Windows.Forms.Integration.ElementHost> control se denomina `elementHost1` y, en la ventana **propiedades** , puede ver que <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> su propiedad está establecida en **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="48d62-140">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="48d62-141">Se agregan referencias a ensamblados de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="48d62-141">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="48d62-142">El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="48d62-142">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="48d62-143">En el panel de etiquetas inteligentes **tareas de ElementHost** , seleccione **acoplar en contenedor primario**.</span><span class="sxs-lookup"><span data-stu-id="48d62-143">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="48d62-144">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="48d62-144">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48d62-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="48d62-145">Next steps</span></span>

<span data-ttu-id="48d62-146">Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente.</span><span class="sxs-lookup"><span data-stu-id="48d62-146">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="48d62-147">Para proporcionar una apariencia y un comportamiento más completos en las aplicaciones, intente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48d62-147">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="48d62-148">Hospede un control de Windows Forms en una página WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-148">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="48d62-149">Para obtener más información, vea [Tutorial: Hospedar un control de Windows Forms](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)en WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-149">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="48d62-150">Aplique estilos visuales de Windows Forms a su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-150">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="48d62-151">Para obtener más información, consulte [Cómo Habilitar estilos visuales en una aplicación](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)híbrida.</span><span class="sxs-lookup"><span data-stu-id="48d62-151">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="48d62-152">Cambie el estilo de su contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-152">Change the style of your WPF content.</span></span> <span data-ttu-id="48d62-153">Para obtener más información, vea [Tutorial: Aplicar estilos al](walkthrough-styling-wpf-content.md)contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="48d62-153">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48d62-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="48d62-154">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="48d62-155">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="48d62-155">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="48d62-156">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="48d62-156">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="48d62-157">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="48d62-157">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
