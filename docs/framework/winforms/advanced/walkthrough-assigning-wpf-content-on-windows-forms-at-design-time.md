---
title: Seleccionar controles WPF para Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746803"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="b33c4-102">Tutorial: asignar contenido de WPF en Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="b33c4-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="b33c4-103">En este artículo se muestra cómo seleccionar los tipos de control de Windows Presentation Foundation (WPF) que desea mostrar en el formulario.</span><span class="sxs-lookup"><span data-stu-id="b33c4-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="b33c4-104">Puede seleccionar los tipos de control de WPF que se incluyen en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b33c4-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b33c4-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b33c4-105">Prerequisites</span></span>

<span data-ttu-id="b33c4-106">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b33c4-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="b33c4-107">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="b33c4-107">Create the project</span></span>

<span data-ttu-id="b33c4-108">Abra Visual Studio y cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic C# o visual denominado `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="b33c4-109">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b33c4-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="b33c4-110">Crear los tipos de control WPF</span><span class="sxs-lookup"><span data-stu-id="b33c4-110">Create the WPF control types</span></span>

<span data-ttu-id="b33c4-111">Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="b33c4-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="b33c4-112">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="b33c4-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="b33c4-113">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="b33c4-114">Para obtener más información, vea [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="b33c4-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="b33c4-115">En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b33c4-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="b33c4-116">En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en **200**.</span><span class="sxs-lookup"><span data-stu-id="b33c4-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="b33c4-117">Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en **contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="b33c4-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="b33c4-118">Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b33c4-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="b33c4-119">Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="b33c4-120">En la ventana **propiedades** , establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en **200**.</span><span class="sxs-lookup"><span data-stu-id="b33c4-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="b33c4-121">Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en **contenido hospedado 2**.</span><span class="sxs-lookup"><span data-stu-id="b33c4-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b33c4-122">Por lo general, debería hospedar contenido WPF más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="b33c4-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="b33c4-123">El control <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> se usa aquí únicamente con fines ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="b33c4-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="b33c4-124">Generar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b33c4-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="b33c4-125">Seleccionar controles WPF</span><span class="sxs-lookup"><span data-stu-id="b33c4-125">Select WPF controls</span></span>

<span data-ttu-id="b33c4-126">Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.</span><span class="sxs-lookup"><span data-stu-id="b33c4-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="b33c4-127">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b33c4-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b33c4-128">En el **cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="b33c4-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="b33c4-129">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="b33c4-130">En el panel de etiquetas inteligentes de `elementHost1`, abra la lista desplegable **seleccionar contenido hospedado** .</span><span class="sxs-lookup"><span data-stu-id="b33c4-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="b33c4-131">Seleccione **UserControl2** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b33c4-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="b33c4-132">El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="b33c4-133">En la ventana **propiedades** , confirme que la propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> está establecida en **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="b33c4-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="b33c4-134">En el **cuadro de herramientas**, en el grupo **interoperabilidad de WPF** , arrastre un control <xref:System.Windows.Forms.Integration.ElementHost> al formulario.</span><span class="sxs-lookup"><span data-stu-id="b33c4-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="b33c4-135">El nombre predeterminado del nuevo control es `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="b33c4-136">En el panel de etiquetas inteligentes de `elementHost2`, abra la lista desplegable **seleccionar contenido hospedado** .</span><span class="sxs-lookup"><span data-stu-id="b33c4-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="b33c4-137">Seleccione **UserControl1** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b33c4-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="b33c4-138">El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="b33c4-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="b33c4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b33c4-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b33c4-140">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="b33c4-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="b33c4-141">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="b33c4-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="b33c4-142">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b33c4-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
