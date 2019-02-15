---
title: 'Tutorial: Asignar el contenido WPF en Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: a2597348075f870723abb07d13ac7a687e47ab41
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304406"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="4826b-102">Tutorial: Asignar el contenido WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="4826b-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="4826b-103">Este tutorial muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario.</span><span class="sxs-lookup"><span data-stu-id="4826b-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="4826b-104">Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="4826b-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="4826b-105">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4826b-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="4826b-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4826b-106">Create the project.</span></span>

-   <span data-ttu-id="4826b-107">Crear los tipos de controles WPF.</span><span class="sxs-lookup"><span data-stu-id="4826b-107">Create the WPF control types.</span></span>

-   <span data-ttu-id="4826b-108">Seleccionar los controles WPF.</span><span class="sxs-lookup"><span data-stu-id="4826b-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="4826b-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="4826b-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4826b-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="4826b-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4826b-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4826b-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4826b-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4826b-112">Prerequisites</span></span>  
 <span data-ttu-id="4826b-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="4826b-113">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="4826b-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="4826b-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4826b-115">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="4826b-115">Creating the Project</span></span>  
 <span data-ttu-id="4826b-116">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4826b-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4826b-117">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4826b-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4826b-118">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="4826b-118">To create the project</span></span>  
  
-   <span data-ttu-id="4826b-119">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="4826b-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="4826b-120">Crear los tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="4826b-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="4826b-121">Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="4826b-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="4826b-122">Para crear tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="4826b-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="4826b-123">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="4826b-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="4826b-124">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="4826b-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="4826b-125">Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="4826b-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="4826b-126">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4826b-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="4826b-127">Para obtener más información, vea [Cómo: Seleccionar y mover elementos en la superficie de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4826b-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="4826b-128">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="4826b-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="4826b-129">Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="4826b-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="4826b-130">Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="4826b-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="4826b-131">Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="4826b-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="4826b-132">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="4826b-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="4826b-133">Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="4826b-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="4826b-134">**Tenga en cuenta** en general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="4826b-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="4826b-135">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="4826b-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="4826b-136">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4826b-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="4826b-137">Seleccionar controles WPF</span><span class="sxs-lookup"><span data-stu-id="4826b-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="4826b-138">Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.</span><span class="sxs-lookup"><span data-stu-id="4826b-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="4826b-139">Para seleccionar controles WPF</span><span class="sxs-lookup"><span data-stu-id="4826b-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="4826b-140">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4826b-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="4826b-141">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="4826b-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="4826b-142">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="4826b-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="4826b-143">En el panel de etiquetas inteligentes para `elementHost1`, abra el **seleccionar contenido hospedable** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4826b-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="4826b-144">Seleccione **UserControl2** desde el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4826b-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="4826b-145">El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="4826b-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="4826b-146">En el **propiedades** ventana, confirme que la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="4826b-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="4826b-147">Desde el **cuadro de herramientas**, en el **interoperabilidad con WPF** grupo, arrastre un <xref:System.Windows.Forms.Integration.ElementHost> al formulario.</span><span class="sxs-lookup"><span data-stu-id="4826b-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="4826b-148">El nombre predeterminado del nuevo control es `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="4826b-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="4826b-149">En el panel de etiquetas inteligentes para `elementHost2`, abra el **seleccionar contenido hospedable** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4826b-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="4826b-150">Seleccione **UserControl1** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4826b-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="4826b-151">El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="4826b-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4826b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="4826b-152">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4826b-153">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="4826b-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="4826b-154">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="4826b-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [<span data-ttu-id="4826b-155">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4826b-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
