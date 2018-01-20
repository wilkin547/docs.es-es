---
title: 'Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost'
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
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaab6b7724a1e6145dfce3998ccf75904df01802
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="632eb-102">Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="632eb-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="632eb-103">En este tutorial se muestra cómo utilizar el <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> propiedad para asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="632eb-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="632eb-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="632eb-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="632eb-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="632eb-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="632eb-106">Definir el diseño de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="632eb-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="632eb-107">Definir una nueva asignación de propiedades.</span><span class="sxs-lookup"><span data-stu-id="632eb-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="632eb-108">Quitar una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="632eb-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="632eb-109">Reemplazar una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="632eb-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="632eb-110">Extender una asignación de propiedades predeterminada.</span><span class="sxs-lookup"><span data-stu-id="632eb-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="632eb-111">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [propiedades de asignación mediante el ejemplo de elemento WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="632eb-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="632eb-112">Cuando haya terminado, podrá asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="632eb-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="632eb-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="632eb-113">Prerequisites</span></span>  
 <span data-ttu-id="632eb-114">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="632eb-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="632eb-115">.</span><span class="sxs-lookup"><span data-stu-id="632eb-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="632eb-116">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="632eb-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="632eb-117">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="632eb-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="632eb-118">Cree un proyecto de aplicación WPF denominado `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="632eb-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="632eb-119">En el Explorador de soluciones, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="632eb-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="632eb-120">En el Explorador de soluciones, agregue referencias a los ensamblados System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="632eb-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="632eb-121">Definir el diseño de la aplicación</span><span class="sxs-lookup"><span data-stu-id="632eb-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="632eb-122">El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basado en aplicación usa el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento para hospedar un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="632eb-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="632eb-123">Para definir el diseño de la aplicación</span><span class="sxs-lookup"><span data-stu-id="632eb-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="632eb-124">Abra Window1.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="632eb-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="632eb-125">Reemplace el código existente por el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="632eb-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="632eb-126">Abra Window1.xaml.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="632eb-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="632eb-127">En la parte superior del archivo, importe los siguientes espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="632eb-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="632eb-128">Definir una nueva asignación de propiedades</span><span class="sxs-lookup"><span data-stu-id="632eb-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="632eb-129">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento proporciona predeterminado varias asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="632eb-130">Agregar una nueva asignación de propiedad mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="632eb-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="632eb-131">Para definir una nueva asignación de propiedades</span><span class="sxs-lookup"><span data-stu-id="632eb-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="632eb-132">Copie el código siguiente en la definición de la `Window1` clase.</span><span class="sxs-lookup"><span data-stu-id="632eb-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="632eb-133">El `AddClipMapping` método agrega una nueva asignación para el <xref:System.Windows.UIElement.Clip%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="632eb-134">El `OnClipChange` método se traduce el <xref:System.Windows.UIElement.Clip%2A> propiedad a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="632eb-135">El `Window1_SizeChanged` método controla la ventana <xref:System.Windows.FrameworkElement.SizeChanged> eventos y cambia el tamaño de la región de recorte para ajustarse a la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="632eb-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="632eb-136">Quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="632eb-137">Quitar una asignación de propiedad predeterminada mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="632eb-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="632eb-138">Para quitar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="632eb-139">Copie el código siguiente en la definición de la `Window1` clase.</span><span class="sxs-lookup"><span data-stu-id="632eb-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="632eb-140">El `RemoveCursorMapping` método elimina la asignación predeterminada para el <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="632eb-141">Reemplazar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="632eb-142">Reemplazar una asignación de propiedad predeterminada mediante la eliminación de la asignación predeterminada y la llamada la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="632eb-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="632eb-143">Para reemplazar una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="632eb-144">Copie el código siguiente en la definición de la `Window1` clase.</span><span class="sxs-lookup"><span data-stu-id="632eb-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="632eb-145">El `ReplaceFlowDirectionMapping` método reemplaza la asignación predeterminada para el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="632eb-146">El `OnFlowDirectionChange` método se traduce el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="632eb-147">El `cb_CheckedChanged` método controla la <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento en el <xref:System.Windows.Forms.CheckBox> control.</span><span class="sxs-lookup"><span data-stu-id="632eb-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="632eb-148">Asigna la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad basándose en el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad</span><span class="sxs-lookup"><span data-stu-id="632eb-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="632eb-149">Extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="632eb-150">Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.</span><span class="sxs-lookup"><span data-stu-id="632eb-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="632eb-151">Para extender una asignación de propiedades predeterminada</span><span class="sxs-lookup"><span data-stu-id="632eb-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="632eb-152">Copie el código siguiente en la definición de la `Window1` clase.</span><span class="sxs-lookup"><span data-stu-id="632eb-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="632eb-153">El `ExtendBackgroundMapping` método agrega un traductor de propiedades personalizadas a las existentes <xref:System.Windows.Controls.Control.Background%2A> asignación de propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="632eb-154">El `OnBackgroundChange` método asigna una imagen específica para el control hospedado <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="632eb-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="632eb-155">El `OnBackgroundChange` método se llama después de aplica la asignación de propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="632eb-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="632eb-156">Inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="632eb-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="632eb-157">Configurar las asignaciones de propiedad llamando a los métodos descritos anteriormente el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="632eb-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="632eb-158">Para inicializar las asignaciones de propiedades</span><span class="sxs-lookup"><span data-stu-id="632eb-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="632eb-159">Copie el código siguiente en la definición de la `Window1` clase.</span><span class="sxs-lookup"><span data-stu-id="632eb-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="632eb-160">El `WindowLoaded` método controla la <xref:System.Windows.FrameworkElement.Loaded> eventos y realiza la inicialización siguiente.</span><span class="sxs-lookup"><span data-stu-id="632eb-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="632eb-161">Crea un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> control.</span><span class="sxs-lookup"><span data-stu-id="632eb-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="632eb-162">Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="632eb-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="632eb-163">Asigna los valores iniciales a las propiedades asignadas.</span><span class="sxs-lookup"><span data-stu-id="632eb-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="632eb-164">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="632eb-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="632eb-165">Haga clic en la casilla de verificación para ver el efecto de la <xref:System.Windows.FrameworkElement.FlowDirection%2A> asignación.</span><span class="sxs-lookup"><span data-stu-id="632eb-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="632eb-166">Al hacer clic en la casilla, el diseño invierte su orientación de izquierda a derecha.</span><span class="sxs-lookup"><span data-stu-id="632eb-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="632eb-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="632eb-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="632eb-168">Asignación de propiedades en formularios Windows Forms y WPF</span><span class="sxs-lookup"><span data-stu-id="632eb-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="632eb-169">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="632eb-169">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="632eb-170">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="632eb-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
