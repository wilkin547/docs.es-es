---
title: 'Tutorial: Organizar controles de formularios Windows Forms en WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 484895db539b288bf388ff6c2ce3c29db55080b1
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197843"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="4b50e-102">Tutorial: Organizar controles de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="4b50e-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="4b50e-103">En este tutorial se muestra cómo usar las características de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para organizar los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en una aplicación híbrida.</span><span class="sxs-lookup"><span data-stu-id="4b50e-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="4b50e-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="4b50e-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="4b50e-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4b50e-105">Creating the project.</span></span>
- <span data-ttu-id="4b50e-106">Usar la configuración de diseño predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b50e-106">Using default layout settings.</span></span>
- <span data-ttu-id="4b50e-107">Ajustar el tamaño al contenido.</span><span class="sxs-lookup"><span data-stu-id="4b50e-107">Sizing to content.</span></span>
- <span data-ttu-id="4b50e-108">Usar el posicionamiento absoluto.</span><span class="sxs-lookup"><span data-stu-id="4b50e-108">Using absolute positioning.</span></span>
- <span data-ttu-id="4b50e-109">Especificar el tamaño explícitamente.</span><span class="sxs-lookup"><span data-stu-id="4b50e-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="4b50e-110">Establecer las propiedades de diseño.</span><span class="sxs-lookup"><span data-stu-id="4b50e-110">Setting layout properties.</span></span>
- <span data-ttu-id="4b50e-111">Entender las limitaciones del orden Z.</span><span class="sxs-lookup"><span data-stu-id="4b50e-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="4b50e-112">Acoplar.</span><span class="sxs-lookup"><span data-stu-id="4b50e-112">Docking.</span></span>
- <span data-ttu-id="4b50e-113">Establecer la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="4b50e-113">Setting visibility.</span></span>
- <span data-ttu-id="4b50e-114">Hospedar un control que no se ajusta.</span><span class="sxs-lookup"><span data-stu-id="4b50e-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="4b50e-115">Ajustar la escala.</span><span class="sxs-lookup"><span data-stu-id="4b50e-115">Scaling.</span></span>
- <span data-ttu-id="4b50e-116">Girar.</span><span class="sxs-lookup"><span data-stu-id="4b50e-116">Rotating.</span></span>
- <span data-ttu-id="4b50e-117">Establecer el relleno y los márgenes.</span><span class="sxs-lookup"><span data-stu-id="4b50e-117">Setting padding and margins.</span></span>
- <span data-ttu-id="4b50e-118">Usar contenedores de diseño dinámico.</span><span class="sxs-lookup"><span data-stu-id="4b50e-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="4b50e-119">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea el [ejemplo de organización de controles Windows Forms en WPF](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="4b50e-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="4b50e-120">Cuando haya terminado, tendrá conocimientos sobre [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] características de diseño en aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b50e-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b50e-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4b50e-121">Prerequisites</span></span>

<span data-ttu-id="4b50e-122">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="4b50e-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="4b50e-123">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="4b50e-123">Creating the Project</span></span>

<span data-ttu-id="4b50e-124">Para crear y configurar el proyecto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-125">Cree un proyecto de aplicación de WPF denominado `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="4b50e-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="4b50e-126">En Explorador de soluciones, agregue referencias a los ensamblados siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b50e-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="4b50e-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="4b50e-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="4b50e-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="4b50e-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="4b50e-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="4b50e-129">System.Drawing</span></span>

3. <span data-ttu-id="4b50e-130">Haga doble clic en *MainWindow. Xaml* para abrirlo en la vista XAML.</span><span class="sxs-lookup"><span data-stu-id="4b50e-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="4b50e-131">En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b50e-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="4b50e-132">En el elemento <xref:System.Windows.Controls.Grid>, establezca la propiedad <xref:System.Windows.Controls.Grid.ShowGridLines%2A> en `true` y defina cinco filas y tres columnas.</span><span class="sxs-lookup"><span data-stu-id="4b50e-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="4b50e-133">Usar la configuración de diseño predeterminada</span><span class="sxs-lookup"><span data-stu-id="4b50e-133">Using Default Layout Settings</span></span>

<span data-ttu-id="4b50e-134">De forma predeterminada, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> controla el diseño del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado.</span><span class="sxs-lookup"><span data-stu-id="4b50e-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="4b50e-135">Para usar la configuración de diseño predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-136">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="4b50e-137">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-138">Aparece el control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> en la <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="4b50e-139">El tamaño del control hospedado se basa en su contenido y el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se ajusta para alojar el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="4b50e-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="4b50e-140">Ajustar el tamaño al contenido</span><span class="sxs-lookup"><span data-stu-id="4b50e-140">Sizing to Content</span></span>

<span data-ttu-id="4b50e-141">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que el tamaño del control hospedado se ajusta para mostrar su contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b50e-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="4b50e-142">Para ajustar el tamaño al contenido, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-143">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="4b50e-144">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-145">Los dos nuevos controles de botón tienen el tamaño para mostrar la cadena de texto más larga y el tamaño de fuente más grande correctamente, y se cambia el tamaño de los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> para alojar los controles hospedados.</span><span class="sxs-lookup"><span data-stu-id="4b50e-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="4b50e-146">Usar el posicionamiento absoluto</span><span class="sxs-lookup"><span data-stu-id="4b50e-146">Using Absolute Positioning</span></span>

<span data-ttu-id="4b50e-147">Puede usar la posición absoluta para colocar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> en cualquier parte de la interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="4b50e-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="4b50e-148">Para usar el posicionamiento absoluto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-149">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="4b50e-150">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-151">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se coloca 20 píxeles desde el lado superior de la celda de la cuadrícula y 20 píxeles desde la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4b50e-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="4b50e-152">Especificar el tamaño explícitamente</span><span class="sxs-lookup"><span data-stu-id="4b50e-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="4b50e-153">Puede especificar el tamaño del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> mediante las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="4b50e-154">Para especificar el tamaño explícitamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-155">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="4b50e-156">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-157">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b50e-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="4b50e-158">El contenido del control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se reorganiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="4b50e-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="4b50e-159">Establecer las propiedades de diseño</span><span class="sxs-lookup"><span data-stu-id="4b50e-159">Setting Layout Properties</span></span>

<span data-ttu-id="4b50e-160">Establezca siempre las propiedades relacionadas con el diseño en el control hospedado mediante las propiedades del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="4b50e-161">Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.</span><span class="sxs-lookup"><span data-stu-id="4b50e-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="4b50e-162">Establecer las propiedades relacionadas con el diseño en el control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4b50e-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="4b50e-163">Para ver los efectos de establecer las propiedades en el control hospedado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-164">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="4b50e-165">En **Explorador de soluciones**, haga doble clic en *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS* para abrirlo en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="4b50e-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="4b50e-166">Copie el código siguiente en la definición de clase `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="4b50e-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="4b50e-167">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="4b50e-168">Haga clic en el botón **click me** .</span><span class="sxs-lookup"><span data-stu-id="4b50e-168">Click the **Click me** button.</span></span> <span data-ttu-id="4b50e-169">El controlador de eventos `button1_Click` establece las propiedades <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> en el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="4b50e-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="4b50e-170">Esto hace que el control hospedado se cambie de posición dentro del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="4b50e-171">El host conserva la misma área de la pantalla, pero el control hospedado se recorta.</span><span class="sxs-lookup"><span data-stu-id="4b50e-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="4b50e-172">En su lugar, el control hospedado siempre debe rellenar el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="4b50e-173">Entender las limitaciones del orden Z</span><span class="sxs-lookup"><span data-stu-id="4b50e-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="4b50e-174">Los elementos <xref:System.Windows.Forms.Integration.WindowsFormsHost> visibles siempre se dibujan encima de otros elementos de WPF y no se ven afectados por el orden z.</span><span class="sxs-lookup"><span data-stu-id="4b50e-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="4b50e-175">Para ver este comportamiento del orden z, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b50e-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="4b50e-176">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="4b50e-177">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-178">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se dibuja sobre el elemento de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="4b50e-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="4b50e-179">Acoplamiento</span><span class="sxs-lookup"><span data-stu-id="4b50e-179">Docking</span></span>

<span data-ttu-id="4b50e-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento admite el acoplamiento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b50e-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="4b50e-181">Establezca el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado en un elemento <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="4b50e-182">Para acoplar un control hospedado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-183">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="4b50e-184">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-185">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se acopla al lado derecho del elemento <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="4b50e-186">Establecer la visibilidad</span><span class="sxs-lookup"><span data-stu-id="4b50e-186">Setting Visibility</span></span>

<span data-ttu-id="4b50e-187">Puede hacer que el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sea invisible o contraerlo si establece la propiedad <xref:System.Windows.UIElement.Visibility%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-187">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="4b50e-188">Cuando un control es invisible no se muestra, pero ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="4b50e-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="4b50e-189">Cuando un control está contraído no se muestra ni ocupa espacio de diseño.</span><span class="sxs-lookup"><span data-stu-id="4b50e-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="4b50e-190">Para establecer la visibilidad de un control hospedado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-191">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="4b50e-192">En *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*, copie el código siguiente en la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="4b50e-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="4b50e-193">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="4b50e-194">Haga clic en el botón **hacer clic para hacer invisible** para hacer que el elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> sea invisible.</span><span class="sxs-lookup"><span data-stu-id="4b50e-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="4b50e-195">Haga clic en el botón **haga clic para contraer** para ocultar completamente el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> del diseño.</span><span class="sxs-lookup"><span data-stu-id="4b50e-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="4b50e-196">Cuando se contrae el control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], los elementos circundantes se reorganizan para ocupar su espacio.</span><span class="sxs-lookup"><span data-stu-id="4b50e-196">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="4b50e-197">Hospedar un control que no se ajusta</span><span class="sxs-lookup"><span data-stu-id="4b50e-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="4b50e-198">Algunos controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño.</span><span class="sxs-lookup"><span data-stu-id="4b50e-198">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="4b50e-199">Por ejemplo, el control <xref:System.Windows.Forms.MonthCalendar> muestra un mes en un espacio fijo.</span><span class="sxs-lookup"><span data-stu-id="4b50e-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="4b50e-200">Para hospedar un control que no se ajusta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-201">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="4b50e-202">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-203">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se centra en la fila de la cuadrícula, pero no se ajusta para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="4b50e-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="4b50e-204">Si la ventana es suficientemente grande, puede ver dos o más meses mostrados por el control de <xref:System.Windows.Forms.MonthCalendar> hospedado, pero se centran en la fila.</span><span class="sxs-lookup"><span data-stu-id="4b50e-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="4b50e-205">El motor de diseño [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] centra los elementos que no se pueden ajustar para rellenar el espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="4b50e-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="4b50e-206">Cambiar escala</span><span class="sxs-lookup"><span data-stu-id="4b50e-206">Scaling</span></span>

<span data-ttu-id="4b50e-207">A diferencia de los elementos de WPF, la mayoría de los controles Windows Forms no son continuamente escalables.</span><span class="sxs-lookup"><span data-stu-id="4b50e-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="4b50e-208">Para proporcionar escalado personalizado, invalide el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="4b50e-209">Para escalar un control hospedado con el comportamiento predeterminado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-210">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="4b50e-211">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-212">El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5.</span><span class="sxs-lookup"><span data-stu-id="4b50e-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="4b50e-213">A pesar de ello, la fuente del control hospedado no se escala.</span><span class="sxs-lookup"><span data-stu-id="4b50e-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="4b50e-214">Girar</span><span class="sxs-lookup"><span data-stu-id="4b50e-214">Rotating</span></span>

<span data-ttu-id="4b50e-215">A diferencia de los elementos de WPF, los controles de Windows Forms no admiten la rotación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="4b50e-216">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> no gira con otros elementos de WPF cuando se aplica una transformación de giro.</span><span class="sxs-lookup"><span data-stu-id="4b50e-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="4b50e-217">Cualquier valor de rotación que no sea 180 grados produce el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="4b50e-218">Para ver el efecto de la rotación en una aplicación híbrida, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-219">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="4b50e-220">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-221">El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados.</span><span class="sxs-lookup"><span data-stu-id="4b50e-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="4b50e-222">Es posible que deba cambiar el tamaño de la ventana para ver los elementos.</span><span class="sxs-lookup"><span data-stu-id="4b50e-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="4b50e-223">Establecer el relleno y márgenes</span><span class="sxs-lookup"><span data-stu-id="4b50e-223">Setting Padding and Margins</span></span>

<span data-ttu-id="4b50e-224">El relleno y los márgenes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares al relleno y los márgenes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b50e-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="4b50e-225">Simplemente establezca las propiedades <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> en el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="4b50e-226">Para establecer el relleno y los márgenes de un control hospedado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-227">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="4b50e-228">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-229">Los valores de relleno y margen se aplican a los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados de la misma manera que se aplicarían en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b50e-229">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="4b50e-230">Usar contenedores de diseño dinámico</span><span class="sxs-lookup"><span data-stu-id="4b50e-230">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="4b50e-231">proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="4b50e-231">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="4b50e-232">También puede usar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseños.</span><span class="sxs-lookup"><span data-stu-id="4b50e-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="4b50e-233">Para usar un contenedor de diseño dinámico, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4b50e-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="4b50e-234">Copie el siguiente código XAML en el elemento <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="4b50e-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="4b50e-235">En *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*, copie el código siguiente en la definición de clase:</span><span class="sxs-lookup"><span data-stu-id="4b50e-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="4b50e-236">Agregue una llamada al método `InitializeFlowLayoutPanel` en el constructor:</span><span class="sxs-lookup"><span data-stu-id="4b50e-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="4b50e-237">Presione <kbd>F5</kbd> para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b50e-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="4b50e-238">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> rellena el <xref:System.Windows.Controls.DockPanel>y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en la <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b50e-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b50e-239">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b50e-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4b50e-240">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4b50e-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="4b50e-241">Consideraciones sobre el diseño del elemento WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="4b50e-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="4b50e-242">Ejemplo de cómo organizar controles Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="4b50e-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="4b50e-243">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="4b50e-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="4b50e-244">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b50e-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
