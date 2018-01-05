---
title: 'Tutorial: Asignar propiedades mediante el uso del control ElementHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0db7b9677b5c8c415b6d0b3f49bd149c06843a33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="2b461-102">Tutorial: Asignar propiedades mediante el uso del control ElementHost</span><span class="sxs-lookup"><span data-stu-id="2b461-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="2b461-103">En este tutorial se muestra cómo utilizar el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad para asignar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="2b461-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="2b461-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="2b461-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="2b461-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b461-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="2b461-106">Definir una nueva asignación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2b461-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="2b461-107">Quitar una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b461-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="2b461-108">Extender una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b461-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="2b461-109">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [propiedades de asignación mediante el ejemplo de Control ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="2b461-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="2b461-110">Cuando haya terminado, podrá asignar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades correspondiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades en un elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="2b461-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b461-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2b461-111">Prerequisites</span></span>  
 <span data-ttu-id="2b461-112">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="2b461-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="2b461-113">.</span><span class="sxs-lookup"><span data-stu-id="2b461-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="2b461-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="2b461-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="2b461-115">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="2b461-115">To create the project</span></span>  
  
1.  <span data-ttu-id="2b461-116">Crear un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proyecto de aplicación denominado `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="2b461-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="2b461-117">Para obtener más información, consulta [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="2b461-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="2b461-118">En el Explorador de soluciones, agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados.</span><span class="sxs-lookup"><span data-stu-id="2b461-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="2b461-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="2b461-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="2b461-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="2b461-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="2b461-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="2b461-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="2b461-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="2b461-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="2b461-123">Copie el código siguiente en la parte superior de la `Form1` archivo de código.</span><span class="sxs-lookup"><span data-stu-id="2b461-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="2b461-124">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2b461-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="2b461-125">Haga doble clic en el formulario para agregar un controlador de eventos para el <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="2b461-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="2b461-126">Vuelva al diseñador de Windows Forms y agregue un controlador de eventos para el formulario <xref:System.Windows.Forms.Control.Resize> eventos.</span><span class="sxs-lookup"><span data-stu-id="2b461-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="2b461-127">Para obtener más información, consulte [Cómo: crear controladores de eventos mediante el diseñador](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).</span><span class="sxs-lookup"><span data-stu-id="2b461-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="2b461-128">Declarar un <xref:System.Windows.Forms.Integration.ElementHost> campo el `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="2b461-129">Definir nuevas asignaciones de propiedad</span><span class="sxs-lookup"><span data-stu-id="2b461-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="2b461-130">El <xref:System.Windows.Forms.Integration.ElementHost> control proporciona predeterminado varias asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="2b461-131">Agregar una nueva asignación de propiedad mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b461-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="2b461-132">Para definir nuevas asignaciones de propiedad</span><span class="sxs-lookup"><span data-stu-id="2b461-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="2b461-133">Copie el código siguiente en la definición de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="2b461-134">El `AddMarginMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Margin%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="2b461-135">El `OnMarginChange` método se traduce el <xref:System.Windows.Forms.Control.Margin%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="2b461-136">Copie el código siguiente en la definición de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="2b461-137">El `AddRegionMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Region%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="2b461-138">El `OnRegionChange` método se traduce el <xref:System.Windows.Forms.Control.Region%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="2b461-139">El `Form1_Resize` método controla el formulario <xref:System.Windows.Forms.Control.Resize> eventos y cambia el tamaño de la región de recorte para adaptarse al elemento hospedado.</span><span class="sxs-lookup"><span data-stu-id="2b461-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="2b461-140">Quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="2b461-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="2b461-141">Quitar una asignación de propiedad predeterminada mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b461-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="2b461-142">Para quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="2b461-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="2b461-143">Copie el código siguiente en la definición de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="2b461-144">El `RemoveCursorMapping` método elimina la asignación predeterminada para el <xref:System.Windows.Forms.Control.Cursor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="2b461-145">Extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="2b461-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="2b461-146">Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.</span><span class="sxs-lookup"><span data-stu-id="2b461-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="2b461-147">Para extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="2b461-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="2b461-148">Copie el código siguiente en la definición de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="2b461-149">El `ExtendBackColorMapping` método agrega un traductor de propiedades personalizadas a las existentes <xref:System.Windows.Forms.Control.BackColor%2A> asignación de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="2b461-150">El `OnBackColorChange` método asigna una imagen específica para el control hospedado <xref:System.Windows.Controls.Control.Background%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2b461-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="2b461-151">El `OnBackColorChange` método se llama después de aplica la asignación de propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2b461-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="2b461-152">Inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="2b461-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="2b461-153">Para inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="2b461-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="2b461-154">Copie el código siguiente en la definición de la `Form1` clase.</span><span class="sxs-lookup"><span data-stu-id="2b461-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="2b461-155">El `Form1_Load` método controla la <xref:System.Windows.Forms.Form.Load> eventos y realiza la inicialización siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b461-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="2b461-156">Crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="2b461-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="2b461-157">Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="2b461-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="2b461-158">Asigna los valores iniciales a las propiedades asignadas.</span><span class="sxs-lookup"><span data-stu-id="2b461-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="2b461-159">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2b461-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b461-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b461-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="2b461-161">Asignación de propiedades en formularios Windows Forms y WPF</span><span class="sxs-lookup"><span data-stu-id="2b461-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="2b461-162">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="2b461-162">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="2b461-163">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b461-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
