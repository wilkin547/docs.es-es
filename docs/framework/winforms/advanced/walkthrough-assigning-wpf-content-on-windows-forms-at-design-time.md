---
title: 'Tutorial: Asignar contenido de WPF en formularios Windows Forms en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211236"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="1e818-102">Tutorial: Asignar contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="1e818-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="1e818-103">Este tutorial muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario.</span><span class="sxs-lookup"><span data-stu-id="1e818-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="1e818-104">Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e818-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="1e818-105">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e818-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="1e818-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e818-106">Create the project.</span></span>

- <span data-ttu-id="1e818-107">Crear los tipos de controles WPF.</span><span class="sxs-lookup"><span data-stu-id="1e818-107">Create the WPF control types.</span></span>

- <span data-ttu-id="1e818-108">Seleccionar los controles WPF.</span><span class="sxs-lookup"><span data-stu-id="1e818-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e818-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1e818-109">Prerequisites</span></span>

<span data-ttu-id="1e818-110">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="1e818-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="1e818-111">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="1e818-111">Create the project</span></span>

<span data-ttu-id="1e818-112">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# denominado `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="1e818-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="1e818-113">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1e818-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="1e818-114">Crear los tipos de controles WPF</span><span class="sxs-lookup"><span data-stu-id="1e818-114">Create the WPF control types</span></span>

<span data-ttu-id="1e818-115">Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="1e818-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="1e818-116">Crear tipos de controles WPF</span><span class="sxs-lookup"><span data-stu-id="1e818-116">Create WPF control types</span></span>

1. <span data-ttu-id="1e818-117">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="1e818-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="1e818-118">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="1e818-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="1e818-119">Para obtener más información, vea [Tutorial: Crear nuevo contenido WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="1e818-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="1e818-120">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1e818-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="1e818-121">Para obtener más información, vea [Cómo: Seleccionar y mover elementos en la superficie de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1e818-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="1e818-122">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="1e818-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="1e818-123">Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="1e818-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="1e818-124">Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e818-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="1e818-125">Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="1e818-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="1e818-126">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades a `200`.</span><span class="sxs-lookup"><span data-stu-id="1e818-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="1e818-127">Agregar un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> el control a la <xref:System.Windows.Controls.UserControl> y establezca el valor de la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="1e818-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="1e818-128">**Tenga en cuenta** en general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="1e818-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="1e818-129">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="1e818-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="1e818-130">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1e818-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="1e818-131">Seleccionar controles WPF</span><span class="sxs-lookup"><span data-stu-id="1e818-131">Select WPF controls</span></span>

<span data-ttu-id="1e818-132">Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.</span><span class="sxs-lookup"><span data-stu-id="1e818-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="1e818-133">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1e818-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="1e818-134">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="1e818-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="1e818-135">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="1e818-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="1e818-136">En el panel de etiquetas inteligentes para `elementHost1`, abra el **seleccionar contenido hospedable** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e818-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="1e818-137">Seleccione **UserControl2** desde el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e818-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="1e818-138">El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="1e818-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="1e818-139">En el **propiedades** ventana, confirme que la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad está establecida en **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="1e818-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="1e818-140">Desde el **cuadro de herramientas**, en el **interoperabilidad con WPF** grupo, arrastre un <xref:System.Windows.Forms.Integration.ElementHost> al formulario.</span><span class="sxs-lookup"><span data-stu-id="1e818-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="1e818-141">El nombre predeterminado del nuevo control es `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="1e818-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="1e818-142">En el panel de etiquetas inteligentes para `elementHost2`, abra el **seleccionar contenido hospedable** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e818-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="1e818-143">Seleccione **UserControl1** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1e818-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="1e818-144">El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="1e818-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e818-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e818-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1e818-146">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="1e818-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="1e818-147">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="1e818-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="1e818-148">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1e818-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
