---
title: 'Tutorial: Organizar controles de formularios Windows Forms en WPF'
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
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f78da83657c4c1bd913f67c9e612264cc5dbdf99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="6ce66-102">Tutorial: Organizar controles de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="6ce66-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="6ce66-103">En este tutorial se muestra cómo usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de diseño para organizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles en una aplicación híbrida.</span><span class="sxs-lookup"><span data-stu-id="6ce66-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="6ce66-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="6ce66-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="6ce66-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ce66-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="6ce66-106">Usar la configuración de diseño predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ce66-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="6ce66-107">Ajustar el tamaño al contenido.</span><span class="sxs-lookup"><span data-stu-id="6ce66-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="6ce66-108">Usar el posicionamiento absoluto.</span><span class="sxs-lookup"><span data-stu-id="6ce66-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="6ce66-109">Especificar el tamaño explícitamente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="6ce66-110">Establecer las propiedades de diseño.</span><span class="sxs-lookup"><span data-stu-id="6ce66-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="6ce66-111">Entender las limitaciones del orden Z.</span><span class="sxs-lookup"><span data-stu-id="6ce66-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="6ce66-112">Acoplar.</span><span class="sxs-lookup"><span data-stu-id="6ce66-112">Docking.</span></span>  
  
-   <span data-ttu-id="6ce66-113">Establecer la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="6ce66-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="6ce66-114">Hospedar un control que no se ajusta.</span><span class="sxs-lookup"><span data-stu-id="6ce66-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="6ce66-115">Ajustar la escala.</span><span class="sxs-lookup"><span data-stu-id="6ce66-115">Scaling.</span></span>  
  
-   <span data-ttu-id="6ce66-116">Girar.</span><span class="sxs-lookup"><span data-stu-id="6ce66-116">Rotating.</span></span>  
  
-   <span data-ttu-id="6ce66-117">Establecer el relleno y los márgenes.</span><span class="sxs-lookup"><span data-stu-id="6ce66-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="6ce66-118">Usar contenedores de diseño dinámico.</span><span class="sxs-lookup"><span data-stu-id="6ce66-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="6ce66-119">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [organizar los controles de Windows Forms en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="6ce66-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="6ce66-120">Cuando haya terminado, tendrá un conocimiento de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] características de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicaciones basadas en.</span><span class="sxs-lookup"><span data-stu-id="6ce66-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ce66-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6ce66-121">Prerequisites</span></span>  
 <span data-ttu-id="6ce66-122">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="6ce66-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="6ce66-123">.</span><span class="sxs-lookup"><span data-stu-id="6ce66-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6ce66-124">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="6ce66-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="6ce66-125">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="6ce66-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="6ce66-126">Cree un proyecto de aplicación WPF denominado `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="6ce66-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="6ce66-127">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="6ce66-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="6ce66-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6ce66-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="6ce66-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6ce66-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="6ce66-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="6ce66-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="6ce66-131">Haga doble clic en MainWindow.xaml para abrirlo en la vista XAML.</span><span class="sxs-lookup"><span data-stu-id="6ce66-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="6ce66-132">En el <xref:System.Windows.Window> elemento, agregue las siguientes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6ce66-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="6ce66-133">En el <xref:System.Windows.Controls.Grid> el elemento establecido el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad `true` y definir cinco filas y tres columnas.</span><span class="sxs-lookup"><span data-stu-id="6ce66-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="6ce66-134">Usar la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="6ce66-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="6ce66-135">De forma predeterminada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento controla el diseño de hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="6ce66-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="6ce66-136">Para usar la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="6ce66-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="6ce66-137">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="6ce66-138">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-139">El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control aparece en el <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6ce66-140">El control hospedado se dimensiona basándose en su contenido y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento cambiará de tamaño para alojar el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="6ce66-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="6ce66-141">Ajuste del tamaño al contenido</span><span class="sxs-lookup"><span data-stu-id="6ce66-141">Sizing to Content</span></span>  
 <span data-ttu-id="6ce66-142">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantiza que el control hospedado tiene un tamaño para mostrar su contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="6ce66-143">Para ajustar al contenido</span><span class="sxs-lookup"><span data-stu-id="6ce66-143">To size to content</span></span>  
  
1.  <span data-ttu-id="6ce66-144">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="6ce66-145">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-146">El tamaño de los dos nuevos controles de botón se ajusta para mostrar correctamente, la cadena de texto más larga y el tamaño de fuente y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos cambian de tamaño para dar cabida a los controles hospedados.</span><span class="sxs-lookup"><span data-stu-id="6ce66-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="6ce66-147">Usar el posicionamiento absoluto</span><span class="sxs-lookup"><span data-stu-id="6ce66-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="6ce66-148">Puede usar la ubicación absoluta para colocar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en cualquier parte de la interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="6ce66-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="6ce66-149">Para usar el posicionamiento absoluto</span><span class="sxs-lookup"><span data-stu-id="6ce66-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="6ce66-150">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="6ce66-151">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-152">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se coloca a 20 píxeles de la parte superior de la celda de cuadrícula y 20 píxeles desde la izquierda.</span><span class="sxs-lookup"><span data-stu-id="6ce66-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="6ce66-153">Especificar el tamaño explícitamente</span><span class="sxs-lookup"><span data-stu-id="6ce66-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="6ce66-154">Puede especificar el tamaño de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utilizando el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="6ce66-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="6ce66-155">Para especificar el tamaño explícitamente</span><span class="sxs-lookup"><span data-stu-id="6ce66-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="6ce66-156">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="6ce66-157">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-158">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ce66-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="6ce66-159">El contenido de la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se reorganiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="6ce66-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="6ce66-160">Establecer las propiedades de diseño</span><span class="sxs-lookup"><span data-stu-id="6ce66-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="6ce66-161">Siempre establece las propiedades relacionadas con el diseño del control hospedado mediante las propiedades de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6ce66-162">Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.</span><span class="sxs-lookup"><span data-stu-id="6ce66-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="6ce66-163">Establecer las propiedades relacionadas con el diseño en el control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="6ce66-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="6ce66-164">Para ver los efectos de establecer las propiedades en el control hospedado</span><span class="sxs-lookup"><span data-stu-id="6ce66-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="6ce66-165">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="6ce66-166">En el Explorador de soluciones, haga doble clic en MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="6ce66-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="6ce66-167">vb o MainWindow.xaml.cs para abrirlo en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="6ce66-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="6ce66-168">Copie el código siguiente en el `MainWindow` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6ce66-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="6ce66-169">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="6ce66-170">Haga clic en el **Click me** botón.</span><span class="sxs-lookup"><span data-stu-id="6ce66-170">Click the **Click me** button.</span></span> <span data-ttu-id="6ce66-171">El `button1_Click` conjuntos de controlador de eventos el <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> propiedades en el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="6ce66-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="6ce66-172">Esto hace que el control hospedado cambiar de posición dentro de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6ce66-173">El host conserva la misma área de la pantalla, pero el control hospedado se recorta.</span><span class="sxs-lookup"><span data-stu-id="6ce66-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="6ce66-174">En su lugar, el control hospedado siempre debe rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="6ce66-175">Entender las limitaciones del orden Z</span><span class="sxs-lookup"><span data-stu-id="6ce66-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="6ce66-176">De forma predeterminada, visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos siempre se dibujan sobre otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos y se ven afectados por orden z.</span><span class="sxs-lookup"><span data-stu-id="6ce66-176">By default, visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="6ce66-177">Para habilitar el orden z, establezca el <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> propiedad de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> propiedad <xref:System.Windows.Interop.CompositionMode.Full> o <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-177">To enable z-ordering, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-default-z-order-behavior"></a><span data-ttu-id="6ce66-178">Para ver el comportamiento predeterminado del orden Z</span><span class="sxs-lookup"><span data-stu-id="6ce66-178">To see the default z-order behavior</span></span>  
  
1.  <span data-ttu-id="6ce66-179">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-179">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  <span data-ttu-id="6ce66-180">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-180">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-181">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> se pinta el elemento sobre el elemento de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6ce66-181">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a><span data-ttu-id="6ce66-182">Para ver el comportamiento del orden Z cuando IsRedirected es true</span><span class="sxs-lookup"><span data-stu-id="6ce66-182">To see the z-order behavior when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="6ce66-183">Reemplazar el anterior ejemplo de orden z con el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-183">Replace the previous z-order example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     <span data-ttu-id="6ce66-184">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-184">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-185">Se pinta el elemento de etiqueta sobre la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-185">The label element is painted over the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="docking"></a><span data-ttu-id="6ce66-186">Acoplamiento</span><span class="sxs-lookup"><span data-stu-id="6ce66-186">Docking</span></span>  
 <span data-ttu-id="6ce66-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>elemento admite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="6ce66-188">Establecer el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado en un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-188">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="6ce66-189">Para acoplar un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6ce66-189">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="6ce66-190">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-190">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="6ce66-191">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-191">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-192">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento se acopla a la derecha de la <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-192">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="6ce66-193">Establecer la visibilidad</span><span class="sxs-lookup"><span data-stu-id="6ce66-193">Setting Visibility</span></span>  
 <span data-ttu-id="6ce66-194">Puede hacer que su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlar invisible o contraerlo estableciendo la <xref:System.Windows.UIElement.Visibility%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-194">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6ce66-195">Cuando un control es invisible no se muestra, pero ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="6ce66-195">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="6ce66-196">Cuando un control está contraído no se muestra ni ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="6ce66-196">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="6ce66-197">Para establecer la visibilidad de un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6ce66-197">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="6ce66-198">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-198">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="6ce66-199">En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6ce66-199">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="6ce66-200">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-200">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="6ce66-201">Haga clic en el **haga clic aquí para hacer que sea invisible** botón para realizar la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento sea invisible.</span><span class="sxs-lookup"><span data-stu-id="6ce66-201">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="6ce66-202">Haga clic en el **, haga clic para contraer** botón para ocultar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento del diseño completamente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-202">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="6ce66-203">Cuando el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] está contraído, los elementos adyacentes se reorganizan para ocupar su espacio.</span><span class="sxs-lookup"><span data-stu-id="6ce66-203">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="6ce66-204">Hospedar un control que no se ajusta</span><span class="sxs-lookup"><span data-stu-id="6ce66-204">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="6ce66-205">Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño.</span><span class="sxs-lookup"><span data-stu-id="6ce66-205">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="6ce66-206">Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control muestra un mes en un espacio fijo.</span><span class="sxs-lookup"><span data-stu-id="6ce66-206">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="6ce66-207">Para hospedar un control que no se ajusta</span><span class="sxs-lookup"><span data-stu-id="6ce66-207">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="6ce66-208">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-208">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="6ce66-209">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-209">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-210">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se centra en la fila de cuadrícula, pero no se expande para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="6ce66-210">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="6ce66-211">Si la ventana es lo suficientemente grande, es posible que vea dos o más meses mostrados por hospedado <xref:System.Windows.Forms.MonthCalendar> control, pero éstos se centran en la fila.</span><span class="sxs-lookup"><span data-stu-id="6ce66-211">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="6ce66-212">El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño centra elementos que no se deben preverse para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="6ce66-212">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="6ce66-213">Cambiar escala</span><span class="sxs-lookup"><span data-stu-id="6ce66-213">Scaling</span></span>  
 <span data-ttu-id="6ce66-214">A diferencia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos, más [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles no son escalables continuamente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-214">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, most [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls are not continuously scalable.</span></span> <span data-ttu-id="6ce66-215">De forma predeterminada, la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento escala el control hospedado siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="6ce66-215">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element scales its hosted control when possible.</span></span>  <span data-ttu-id="6ce66-216">Para habilitar el ajuste de escala completa, establezca el <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> propiedad de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> propiedad <xref:System.Windows.Interop.CompositionMode.Full> o <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-216">To enable full-fledged scaling, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="6ce66-217">Para escalar un control hospedado mediante el comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="6ce66-217">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="6ce66-218">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-218">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="6ce66-219">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-219">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-220">El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5.</span><span class="sxs-lookup"><span data-stu-id="6ce66-220">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="6ce66-221">A pesar de ello, la fuente del control hospedado no se escala.</span><span class="sxs-lookup"><span data-stu-id="6ce66-221">However, the hosted control's font is not scaled.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a><span data-ttu-id="6ce66-222">Para escalar un control hospedado mediante el establecimiento de IsRedirected en true</span><span class="sxs-lookup"><span data-stu-id="6ce66-222">To scale a hosted control by setting IsRedirected to true</span></span>  
  
1.  <span data-ttu-id="6ce66-223">Reemplace el ejemplo de escalado anterior por el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-223">Replace the previous scaling example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  <span data-ttu-id="6ce66-224">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-224">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-225">El control hospedado, sus elementos adyacentes y la fuente del control hospedado se escalan por un factor de 0,5.</span><span class="sxs-lookup"><span data-stu-id="6ce66-225">The hosted control, its surrounding elements, and the hosted control's font are scaled by a factor of 0.5.</span></span>  
  
## <a name="rotating"></a><span data-ttu-id="6ce66-226">Girar</span><span class="sxs-lookup"><span data-stu-id="6ce66-226">Rotating</span></span>  
 <span data-ttu-id="6ce66-227">A diferencia de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] los controles no admiten la rotación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-227">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls do not support rotation.</span></span> <span data-ttu-id="6ce66-228">De forma predeterminada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> no girar el elemento con otro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos cuando se aplica una transformación de giro.</span><span class="sxs-lookup"><span data-stu-id="6ce66-228">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements when a rotation transformation is applied.</span></span> <span data-ttu-id="6ce66-229">Cualquier valor de giro distinto de 180 grados genera el <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos.</span><span class="sxs-lookup"><span data-stu-id="6ce66-229">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>  <span data-ttu-id="6ce66-230">Para permitir la rotación a cualquier ángulo, establezca el <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> propiedad de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> en true y la <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> propiedad <xref:System.Windows.Interop.CompositionMode.Full> o <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-230">To enable rotating to any angle, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="6ce66-231">Para ver el efecto del giro en una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="6ce66-231">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="6ce66-232">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-232">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="6ce66-233">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-233">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-234">El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados.</span><span class="sxs-lookup"><span data-stu-id="6ce66-234">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="6ce66-235">Es posible que deba cambiar el tamaño de la ventana para ver los elementos.</span><span class="sxs-lookup"><span data-stu-id="6ce66-235">You may have to resize the window to see the elements.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a><span data-ttu-id="6ce66-236">Para ver el efecto del giro en una aplicación híbrida si IsRedirected es true</span><span class="sxs-lookup"><span data-stu-id="6ce66-236">To see the effect of rotation in a hybrid application when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="6ce66-237">Reemplace el ejemplo de giro anterior por el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="6ce66-237">Replace the previous rotation example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  <span data-ttu-id="6ce66-238">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-239">El control hospedado se gira.</span><span class="sxs-lookup"><span data-stu-id="6ce66-239">The hosted control is rotated.</span></span>  <span data-ttu-id="6ce66-240">Tenga en cuenta que el <xref:System.Windows.Media.RotateTransform.Angle%2A> propiedad puede establecerse en cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="6ce66-240">Note that the <xref:System.Windows.Media.RotateTransform.Angle%2A> property can be set to any value.</span></span> <span data-ttu-id="6ce66-241">Es posible que deba cambiar el tamaño de la ventana para ver los elementos.</span><span class="sxs-lookup"><span data-stu-id="6ce66-241">You may have to resize the window to see the elements.</span></span>  
  
## <a name="setting-padding-and-margins"></a><span data-ttu-id="6ce66-242">Establecer el relleno y márgenes</span><span class="sxs-lookup"><span data-stu-id="6ce66-242">Setting Padding and Margins</span></span>  
 <span data-ttu-id="6ce66-243">Padding y Margin en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares a padding y Margin en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ce66-243">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="6ce66-244">Basta con establecer la <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> propiedades en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-244">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="6ce66-245">Para establecer el relleno y los márgenes de un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6ce66-245">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="6ce66-246">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-246">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="6ce66-247">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-247">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-248">Se aplica la configuración de relleno y margen para hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles de la misma manera que se aplicarían en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ce66-248">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="6ce66-249">Usar contenedores de diseño dinámico</span><span class="sxs-lookup"><span data-stu-id="6ce66-249">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="6ce66-250">proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-250"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="6ce66-251">También puede utilizar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseños.</span><span class="sxs-lookup"><span data-stu-id="6ce66-251">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="6ce66-252">Para usar un contenedor de diseño dinámico</span><span class="sxs-lookup"><span data-stu-id="6ce66-252">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="6ce66-253">Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6ce66-253">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="6ce66-254">En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6ce66-254">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="6ce66-255">Agregue una llamada a la `InitializeFlowLayoutPanel` método en el constructor.</span><span class="sxs-lookup"><span data-stu-id="6ce66-255">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="6ce66-256">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ce66-256">Press F5 to build and run the application.</span></span> <span data-ttu-id="6ce66-257">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento rellena el <xref:System.Windows.Controls.DockPanel>, y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en el valor predeterminado <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ce66-257">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce66-258">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ce66-258">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="6ce66-259">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="6ce66-259">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="6ce66-260">Consideraciones sobre el diseño del elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="6ce66-260">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="6ce66-261">Organizar Windows Forms en el ejemplo WPF</span><span class="sxs-lookup"><span data-stu-id="6ce66-261">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="6ce66-262">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="6ce66-262">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="6ce66-263">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ce66-263">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
