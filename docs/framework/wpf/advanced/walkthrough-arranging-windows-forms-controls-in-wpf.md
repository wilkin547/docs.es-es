---
title: 'Tutorial: Organización de Windows Forms en WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: bfb0aba2798179c31674377104bbff633b6f48fc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367198"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="6284b-102">Tutorial: Organización de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="6284b-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="6284b-103">En este tutorial se muestra cómo usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de diseño para organizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles en una aplicación híbrida.</span><span class="sxs-lookup"><span data-stu-id="6284b-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="6284b-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="6284b-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="6284b-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6284b-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="6284b-106">Usar la configuración de diseño predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6284b-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="6284b-107">Ajustar el tamaño al contenido.</span><span class="sxs-lookup"><span data-stu-id="6284b-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="6284b-108">Usar el posicionamiento absoluto.</span><span class="sxs-lookup"><span data-stu-id="6284b-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="6284b-109">Especificar el tamaño explícitamente.</span><span class="sxs-lookup"><span data-stu-id="6284b-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="6284b-110">Establecer las propiedades de diseño.</span><span class="sxs-lookup"><span data-stu-id="6284b-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="6284b-111">Entender las limitaciones del orden Z.</span><span class="sxs-lookup"><span data-stu-id="6284b-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="6284b-112">Acoplar.</span><span class="sxs-lookup"><span data-stu-id="6284b-112">Docking.</span></span>  
  
-   <span data-ttu-id="6284b-113">Establecer la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="6284b-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="6284b-114">Hospedar un control que no se ajusta.</span><span class="sxs-lookup"><span data-stu-id="6284b-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="6284b-115">Ajustar la escala.</span><span class="sxs-lookup"><span data-stu-id="6284b-115">Scaling.</span></span>  
  
-   <span data-ttu-id="6284b-116">Girar.</span><span class="sxs-lookup"><span data-stu-id="6284b-116">Rotating.</span></span>  
  
-   <span data-ttu-id="6284b-117">Establecer el relleno y los márgenes.</span><span class="sxs-lookup"><span data-stu-id="6284b-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="6284b-118">Usar contenedores de diseño dinámico.</span><span class="sxs-lookup"><span data-stu-id="6284b-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="6284b-119">Para obtener una lista de código completo de las tareas ilustradas en este tutorial, vea [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="6284b-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="6284b-120">Cuando haya terminado, tendrá un conocimiento de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] las características de diseño en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicaciones basadas en.</span><span class="sxs-lookup"><span data-stu-id="6284b-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6284b-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6284b-121">Prerequisites</span></span>  

<span data-ttu-id="6284b-122">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="6284b-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="6284b-123">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="6284b-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="6284b-124">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="6284b-124">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="6284b-125">Cree un proyecto de aplicación WPF denominado `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="6284b-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="6284b-126">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="6284b-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="6284b-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6284b-127">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="6284b-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6284b-128">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="6284b-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="6284b-129">System.Drawing</span></span>  
  
3.  <span data-ttu-id="6284b-130">Haga doble clic en MainWindow.xaml para abrirlo en la vista XAML.</span><span class="sxs-lookup"><span data-stu-id="6284b-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="6284b-131">En el <xref:System.Windows.Window> elemento, agregue las siguientes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6284b-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="6284b-132">En el <xref:System.Windows.Controls.Grid> elemento establecido el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad `true` y defina cinco filas y tres columnas.</span><span class="sxs-lookup"><span data-stu-id="6284b-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="6284b-133">Usar la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="6284b-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="6284b-134">De forma predeterminada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento controla el diseño para hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="6284b-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="6284b-135">Para usar la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="6284b-135">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="6284b-136">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="6284b-137">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-138">El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control aparece en el <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="6284b-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6284b-139">El control hospedado se dimensiona basándose en su contenido y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se ajusta para albergar el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="6284b-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="6284b-140">Ajuste del tamaño al contenido</span><span class="sxs-lookup"><span data-stu-id="6284b-140">Sizing to Content</span></span>  
 <span data-ttu-id="6284b-141">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantiza que el control hospedado tiene un tamaño para mostrar su contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="6284b-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="6284b-142">Para ajustar al contenido</span><span class="sxs-lookup"><span data-stu-id="6284b-142">To size to content</span></span>  
  
1.  <span data-ttu-id="6284b-143">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="6284b-144">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-145">El tamaño de los dos nuevos controles de botón se ajusta para mostrar la cadena de texto más larga y el tamaño de fuente mayor correctamente y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos cambian de tamaño para dar cabida a los controles hospedados.</span><span class="sxs-lookup"><span data-stu-id="6284b-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="6284b-146">Usar el posicionamiento absoluto</span><span class="sxs-lookup"><span data-stu-id="6284b-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="6284b-147">Puede usar el posicionamiento absoluto para colocar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en cualquier parte de la interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="6284b-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="6284b-148">Para usar el posicionamiento absoluto</span><span class="sxs-lookup"><span data-stu-id="6284b-148">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="6284b-149">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="6284b-150">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-151">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se coloca a 20 píxeles de la parte superior de la celda de cuadrícula y a 20 píxeles de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="6284b-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="6284b-152">Especificar el tamaño explícitamente</span><span class="sxs-lookup"><span data-stu-id="6284b-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="6284b-153">Puede especificar el tamaño de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento mediante el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="6284b-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="6284b-154">Para especificar el tamaño explícitamente</span><span class="sxs-lookup"><span data-stu-id="6284b-154">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="6284b-155">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="6284b-156">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-157">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento está establecido en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6284b-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="6284b-158">El contenido de la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se reorganiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="6284b-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="6284b-159">Establecer las propiedades de diseño</span><span class="sxs-lookup"><span data-stu-id="6284b-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="6284b-160">Siempre establece las propiedades relacionadas con el diseño del control hospedado mediante el uso de las propiedades de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6284b-161">Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.</span><span class="sxs-lookup"><span data-stu-id="6284b-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="6284b-162">Establecer las propiedades relacionadas con el diseño del control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="6284b-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="6284b-163">Para ver los efectos de establecer las propiedades en el control hospedado</span><span class="sxs-lookup"><span data-stu-id="6284b-163">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="6284b-164">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="6284b-165">En el Explorador de soluciones, haga doble clic en MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="6284b-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="6284b-166">vb o MainWindow.xaml.cs para abrirlo en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="6284b-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="6284b-167">Copie el código siguiente en el `MainWindow` definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6284b-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4.  <span data-ttu-id="6284b-168">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-168">Press F5 to build and run the application.</span></span>

5.  <span data-ttu-id="6284b-169">Haga clic en el **Click me** botón.</span><span class="sxs-lookup"><span data-stu-id="6284b-169">Click the **Click me** button.</span></span> <span data-ttu-id="6284b-170">El `button1_Click` conjuntos de controlador de eventos el <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> las propiedades del control hospedado.</span><span class="sxs-lookup"><span data-stu-id="6284b-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="6284b-171">Esto hace que el control hospedado cambie de posición dentro del <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6284b-172">El host conserva la misma área de la pantalla, pero el control hospedado se recorta.</span><span class="sxs-lookup"><span data-stu-id="6284b-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="6284b-173">En su lugar, el control hospedado siempre debe rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="6284b-174">Entender las limitaciones del orden Z</span><span class="sxs-lookup"><span data-stu-id="6284b-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="6284b-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos siempre se dibujan encima de otros elementos WPF y no se ven afectadas por el orden z.</span><span class="sxs-lookup"><span data-stu-id="6284b-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="6284b-176">Para ver este comportamiento del orden z, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6284b-176">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="6284b-177">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2.  <span data-ttu-id="6284b-178">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-179">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> se pinta el elemento sobre el elemento de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6284b-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>


## <a name="docking"></a><span data-ttu-id="6284b-180">Acoplamiento</span><span class="sxs-lookup"><span data-stu-id="6284b-180">Docking</span></span>
 <span data-ttu-id="6284b-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento admite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] acoplamiento.</span><span class="sxs-lookup"><span data-stu-id="6284b-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="6284b-182">Establecer el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado en un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="6284b-183">Para acoplar un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6284b-183">To dock a hosted control</span></span>

1.  <span data-ttu-id="6284b-184">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2.  <span data-ttu-id="6284b-185">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-186">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento se acopla a la derecha de la <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="6284b-187">Establecer la visibilidad</span><span class="sxs-lookup"><span data-stu-id="6284b-187">Setting Visibility</span></span>
 <span data-ttu-id="6284b-188">Puede hacer su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible o contraerlo estableciendo el <xref:System.Windows.UIElement.Visibility%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6284b-189">Cuando un control es invisible no se muestra, pero ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="6284b-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="6284b-190">Cuando un control está contraído no se muestra ni ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="6284b-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="6284b-191">Para establecer la visibilidad de un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6284b-191">To set the visibility of a hosted control</span></span>

1.  <span data-ttu-id="6284b-192">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2.  <span data-ttu-id="6284b-193">En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6284b-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3.  <span data-ttu-id="6284b-194">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-194">Press F5 to build and run the application.</span></span>

4.  <span data-ttu-id="6284b-195">Haga clic en el **haga clic aquí para que sea invisible** para realizar la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento sea invisible.</span><span class="sxs-lookup"><span data-stu-id="6284b-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5.  <span data-ttu-id="6284b-196">Haga clic en el **haga clic para contraer** botón para ocultar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento desde el diseño completamente.</span><span class="sxs-lookup"><span data-stu-id="6284b-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="6284b-197">Cuando el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] está contraído, los elementos circundantes se reorganizan para ocupar su espacio.</span><span class="sxs-lookup"><span data-stu-id="6284b-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="6284b-198">Hospedar un control que no se ajusta</span><span class="sxs-lookup"><span data-stu-id="6284b-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="6284b-199">Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño.</span><span class="sxs-lookup"><span data-stu-id="6284b-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="6284b-200">Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control muestra un mes en un espacio fijo.</span><span class="sxs-lookup"><span data-stu-id="6284b-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="6284b-201">Para hospedar un control que no se ajusta</span><span class="sxs-lookup"><span data-stu-id="6284b-201">To host a control that does not stretch</span></span>

1.  <span data-ttu-id="6284b-202">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2.  <span data-ttu-id="6284b-203">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-204">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se centra en la fila de cuadrícula, pero no se ajusta para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="6284b-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="6284b-205">Si la ventana es suficientemente grande, es posible que vea dos o más meses mostrados por hospedado <xref:System.Windows.Forms.MonthCalendar> control, pero estos se centran en la fila.</span><span class="sxs-lookup"><span data-stu-id="6284b-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="6284b-206">El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño centra los elementos que no se pueden tener un tamaño para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="6284b-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="6284b-207">Cambiar escala</span><span class="sxs-lookup"><span data-stu-id="6284b-207">Scaling</span></span>
 <span data-ttu-id="6284b-208">A diferencia de los elementos de WPF, la mayoría de los controles de Windows Forms no es escalable continuamente.</span><span class="sxs-lookup"><span data-stu-id="6284b-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="6284b-209">Para proporcionar escala personalizada, invalida el <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="6284b-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="6284b-210">Para escalar un control hospedado mediante el comportamiento predeterminado</span><span class="sxs-lookup"><span data-stu-id="6284b-210">To scale a hosted control by using the default behavior</span></span>

1.  <span data-ttu-id="6284b-211">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2.  <span data-ttu-id="6284b-212">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-213">El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5.</span><span class="sxs-lookup"><span data-stu-id="6284b-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="6284b-214">A pesar de ello, la fuente del control hospedado no se escala.</span><span class="sxs-lookup"><span data-stu-id="6284b-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="6284b-215">Girar</span><span class="sxs-lookup"><span data-stu-id="6284b-215">Rotating</span></span>
 <span data-ttu-id="6284b-216">A diferencia de los elementos de WPF, controles de formularios Windows Forms no admiten el giro.</span><span class="sxs-lookup"><span data-stu-id="6284b-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="6284b-217">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento no se gira con otros elementos WPF cuando se aplica una transformación de giro.</span><span class="sxs-lookup"><span data-stu-id="6284b-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="6284b-218">Cualquier valor de giro distinto de 180 grados provoca el <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos.</span><span class="sxs-lookup"><span data-stu-id="6284b-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="6284b-219">Para ver el efecto del giro en una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="6284b-219">To see the effect of rotation in a hybrid application</span></span>

1.  <span data-ttu-id="6284b-220">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2.  <span data-ttu-id="6284b-221">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-222">El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados.</span><span class="sxs-lookup"><span data-stu-id="6284b-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="6284b-223">Es posible que deba cambiar el tamaño de la ventana para ver los elementos.</span><span class="sxs-lookup"><span data-stu-id="6284b-223">You may have to resize the window to see the elements.</span></span>


## <a name="setting-padding-and-margins"></a><span data-ttu-id="6284b-224">Establecer el relleno y márgenes</span><span class="sxs-lookup"><span data-stu-id="6284b-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="6284b-225">Relleno y márgenes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares al relleno y márgenes en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6284b-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="6284b-226">Basta con establecer la <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> propiedades en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="6284b-227">Para establecer el relleno y los márgenes de un control hospedado</span><span class="sxs-lookup"><span data-stu-id="6284b-227">To set padding and margins for a hosted control</span></span>

1.  <span data-ttu-id="6284b-228">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2.  <span data-ttu-id="6284b-229">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-230">Se aplica la configuración de relleno y margen a hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles de la misma manera que se aplicaría en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6284b-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="6284b-231">Usar contenedores de diseño dinámico</span><span class="sxs-lookup"><span data-stu-id="6284b-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="6284b-232">proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="6284b-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="6284b-233">También puede usar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseños.</span><span class="sxs-lookup"><span data-stu-id="6284b-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="6284b-234">Para usar un contenedor de diseño dinámico</span><span class="sxs-lookup"><span data-stu-id="6284b-234">To use a dynamic layout container</span></span>

1.  <span data-ttu-id="6284b-235">Copie el siguiente XAML en el <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="6284b-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2.  <span data-ttu-id="6284b-236">En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="6284b-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3.  <span data-ttu-id="6284b-237">Agregue una llamada al método `InitializeFlowLayoutPanel` en el constructor.</span><span class="sxs-lookup"><span data-stu-id="6284b-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="6284b-238">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6284b-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="6284b-239">El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento rellena el <xref:System.Windows.Controls.DockPanel>, y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en el valor predeterminado <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="6284b-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6284b-240">Vea también</span><span class="sxs-lookup"><span data-stu-id="6284b-240">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6284b-241">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6284b-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6284b-242">Consideraciones sobre el diseño del elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="6284b-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="6284b-243">Organización de Windows Forms en WPF ejemplo</span><span class="sxs-lookup"><span data-stu-id="6284b-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="6284b-244">Tutorial: Hospedar un Control compuesto de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="6284b-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6284b-245">Tutorial: Hospedar un Control compuesto de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6284b-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
