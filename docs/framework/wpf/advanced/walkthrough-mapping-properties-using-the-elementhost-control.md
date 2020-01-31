---
title: 'Tutorial: Asignar propiedades mediante el uso del control ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794119"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="5a86c-102">Tutorial: Asignar propiedades mediante el uso del control ElementHost</span><span class="sxs-lookup"><span data-stu-id="5a86c-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="5a86c-103">En este tutorial se muestra cómo utilizar la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> para asignar Windows Forms propiedades a las propiedades correspondientes de un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado.</span><span class="sxs-lookup"><span data-stu-id="5a86c-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="5a86c-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="5a86c-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="5a86c-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5a86c-105">Creating the project.</span></span>

- <span data-ttu-id="5a86c-106">Definir una nueva asignación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5a86c-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="5a86c-107">Quitar una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a86c-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="5a86c-108">Extender una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a86c-108">Extending a default property mapping.</span></span>

<span data-ttu-id="5a86c-109">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [asignación de propiedades mediante el ejemplo de control ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="5a86c-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="5a86c-110">Cuando haya terminado, podrá asignar Windows Forms propiedades a las propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondientes en un elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="5a86c-110">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a86c-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5a86c-111">Prerequisites</span></span>

<span data-ttu-id="5a86c-112">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="5a86c-112">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="5a86c-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="5a86c-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="5a86c-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="5a86c-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="5a86c-115">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="5a86c-115">To create the project</span></span>

1. <span data-ttu-id="5a86c-116">Cree un proyecto de **aplicación de Windows Forms** denominado `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="5a86c-117">En **Explorador de soluciones**, agregue referencias a los siguientes ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a86c-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="5a86c-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="5a86c-118">PresentationCore</span></span>

    - <span data-ttu-id="5a86c-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="5a86c-119">PresentationFramework</span></span>

    - <span data-ttu-id="5a86c-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="5a86c-120">WindowsBase</span></span>

    - <span data-ttu-id="5a86c-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="5a86c-121">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="5a86c-122">Copie el código siguiente en la parte superior del archivo de código `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="5a86c-123">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5a86c-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="5a86c-124">Haga doble clic en el formulario para agregar un controlador de eventos para el evento <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="5a86c-125">Vuelva al Diseñador de Windows Forms y agregue un controlador de eventos para el evento de <xref:System.Windows.Forms.Control.Resize> del formulario.</span><span class="sxs-lookup"><span data-stu-id="5a86c-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="5a86c-126">Para obtener más información, vea [Cómo: crear controladores de eventos mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5a86c-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="5a86c-127">Declare un campo <xref:System.Windows.Forms.Integration.ElementHost> en la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="5a86c-128">Definir nuevas asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="5a86c-128">Defining New Property Mappings</span></span>

<span data-ttu-id="5a86c-129">El control <xref:System.Windows.Forms.Integration.ElementHost> proporciona varias asignaciones de propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="5a86c-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="5a86c-130">Agregue una nueva asignación de propiedad llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> en el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="5a86c-131">Para definir nuevas asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="5a86c-131">To define new property mappings</span></span>

1. <span data-ttu-id="5a86c-132">Copie el código siguiente en la definición de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="5a86c-133">El método `AddMarginMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Margin%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="5a86c-134">El método `OnMarginChange` traduce la propiedad <xref:System.Windows.Forms.Control.Margin%2A> a la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="5a86c-135">Copie el código siguiente en la definición de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="5a86c-136">El método `AddRegionMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Region%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="5a86c-137">El método `OnRegionChange` traduce la propiedad <xref:System.Windows.Forms.Control.Region%2A> a la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="5a86c-138">El método `Form1_Resize` controla el evento de <xref:System.Windows.Forms.Control.Resize> del formulario y ajusta el tamaño de la región de recorte para que quepa en el elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="5a86c-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="5a86c-139">Quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="5a86c-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="5a86c-140">Quitar una asignación de propiedades predeterminada llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> en el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="5a86c-141">Para quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="5a86c-141">To remove a default property mapping</span></span>

- <span data-ttu-id="5a86c-142">Copie el código siguiente en la definición de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="5a86c-143">El método `RemoveCursorMapping` elimina la asignación predeterminada para la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a86c-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="5a86c-144">Extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="5a86c-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="5a86c-145">Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.</span><span class="sxs-lookup"><span data-stu-id="5a86c-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="5a86c-146">Para extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="5a86c-146">To extend a default property mapping</span></span>

- <span data-ttu-id="5a86c-147">Copie el código siguiente en la definición de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="5a86c-148">El método `ExtendBackColorMapping` agrega un traductor de propiedades personalizado a la asignación de propiedades de <xref:System.Windows.Forms.Control.BackColor%2A> existente.</span><span class="sxs-lookup"><span data-stu-id="5a86c-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="5a86c-149">El método `OnBackColorChange` asigna una imagen específica a la propiedad <xref:System.Windows.Controls.Control.Background%2A> del control hospedado.</span><span class="sxs-lookup"><span data-stu-id="5a86c-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="5a86c-150">Se llama al método `OnBackColorChange` después de aplicar la asignación de propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a86c-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="5a86c-151">Inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="5a86c-151">Initialize your property mappings</span></span>

1. <span data-ttu-id="5a86c-152">Copie el código siguiente en la definición de la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5a86c-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="5a86c-153">El método `Form1_Load` controla el evento <xref:System.Windows.Forms.Form.Load> y realiza la inicialización siguiente.</span><span class="sxs-lookup"><span data-stu-id="5a86c-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="5a86c-154">Crea un elemento de <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a86c-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="5a86c-155">Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="5a86c-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="5a86c-156">Asigna los valores iniciales a las propiedades asignadas.</span><span class="sxs-lookup"><span data-stu-id="5a86c-156">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="5a86c-157">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a86c-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a86c-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a86c-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5a86c-159">Asignación de propiedades en formularios Windows Forms y WPF</span><span class="sxs-lookup"><span data-stu-id="5a86c-159">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="5a86c-160">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a86c-160">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="5a86c-161">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a86c-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
