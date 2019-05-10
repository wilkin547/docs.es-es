---
title: 'Tutorial: Hospedar un control ActiveX en WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 976679e4b6e6bba7288756616db639ed61472591
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605442"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="ff24b-102">Tutorial: Hospedar un control ActiveX en WPF</span><span class="sxs-lookup"><span data-stu-id="ff24b-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="ff24b-103">Para habilitar la interacción mejorada con los exploradores, puede usar [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controles en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en.</span><span class="sxs-lookup"><span data-stu-id="ff24b-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="ff24b-104">Este tutorial muestra cómo puede hospedar el [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] como un control en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página.</span><span class="sxs-lookup"><span data-stu-id="ff24b-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="ff24b-105">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="ff24b-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ff24b-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff24b-106">Creating the project.</span></span>

- <span data-ttu-id="ff24b-107">Crear el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ff24b-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="ff24b-108">Hospedar el control ActiveX en una página de WPF.</span><span class="sxs-lookup"><span data-stu-id="ff24b-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="ff24b-109">Cuando haya completado este tutorial, comprenderá cómo usar [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controles en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en.</span><span class="sxs-lookup"><span data-stu-id="ff24b-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff24b-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff24b-110">Prerequisites</span></span>
 <span data-ttu-id="ff24b-111">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="ff24b-111">You need the following components to complete this walkthrough:</span></span>

- [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] <span data-ttu-id="ff24b-112">instalado en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff24b-112">installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="ff24b-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ff24b-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="ff24b-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="ff24b-114">Creating the Project</span></span>

#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="ff24b-115">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="ff24b-115">To create and set up the project</span></span>

1. <span data-ttu-id="ff24b-116">Cree un proyecto de aplicación WPF denominado `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="ff24b-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="ff24b-117">Agregar un proyecto de biblioteca de controles de Windows Forms a la solución y denomine al proyecto `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="ff24b-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="ff24b-118">En el proyecto WmpAxLib, agregue una referencia al ensamblado de Windows Media Player, que se denomina wmp.dll.</span><span class="sxs-lookup"><span data-stu-id="ff24b-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="ff24b-119">Abra el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="ff24b-120">Haga clic en el **cuadro de herramientas**y, a continuación, haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="ff24b-121">Haga clic en el **componentes COM** ficha, seleccione el **Windows Media Player** controlar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="ff24b-122">El control de Windows Media Player se agrega a la **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="ff24b-123">En el Explorador de soluciones, haga clic en el **UserControl1** de archivo y, a continuación, haga clic en **cambiar el nombre**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="ff24b-124">Cambie el nombre a `WmpAxControl.vb` o `WmpAxControl.cs`, según el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff24b-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="ff24b-125">Si se le solicite cambiar el nombre de todas las referencias, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ff24b-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="ff24b-126">Crear el Control ActiveX</span><span class="sxs-lookup"><span data-stu-id="ff24b-126">Creating the ActiveX Control</span></span>
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <span data-ttu-id="ff24b-127">genera automáticamente un <xref:System.Windows.Forms.AxHost> clase contenedora para un [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controlar cuando el control se agrega a una superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ff24b-127">automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="ff24b-128">El procedimiento siguiente crea un ensamblado administrado denominado AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="ff24b-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

#### <a name="to-create-the-activex-control"></a><span data-ttu-id="ff24b-129">Para crear el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="ff24b-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="ff24b-130">Abra WmpAxControl.vb o WmpAxControl.cs en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff24b-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="ff24b-131">Desde el **cuadro de herramientas**, agregar el control de Windows Media Player a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ff24b-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="ff24b-132">En la ventana Propiedades, establezca el valor del control de Windows Media Player <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="ff24b-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="ff24b-133">Compile el proyecto de biblioteca de control WmpAxLib.</span><span class="sxs-lookup"><span data-stu-id="ff24b-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="ff24b-134">Hospedar el Control ActiveX en una página de WPF</span><span class="sxs-lookup"><span data-stu-id="ff24b-134">Hosting the ActiveX Control on a WPF Page</span></span>

#### <a name="to-host-the-activex-control"></a><span data-ttu-id="ff24b-135">Para hospedar el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="ff24b-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="ff24b-136">En el proyecto HostingAxInWpf, agregue una referencia a generado [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] ensamblado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="ff24b-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>

     <span data-ttu-id="ff24b-137">Este ensamblado se denomina AxInterop.WMPLib.dll y se agregó a la carpeta Debug del proyecto WmpAxLib al importar el control de Windows Media Player.</span><span class="sxs-lookup"><span data-stu-id="ff24b-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="ff24b-138">Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="ff24b-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="ff24b-139">Agregue una referencia a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ensamblado, que se denomina System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="ff24b-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="ff24b-140">Abra MainWindow.xaml en el diseñador WPF.</span><span class="sxs-lookup"><span data-stu-id="ff24b-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="ff24b-141">Nombre de la <xref:System.Windows.Controls.Grid> elemento `grid1`.</span><span class="sxs-lookup"><span data-stu-id="ff24b-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="ff24b-142">En la vista Diseño o la vista XAML, seleccione el <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="ff24b-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="ff24b-143">En la ventana Propiedades, haga clic en el **eventos** ficha.</span><span class="sxs-lookup"><span data-stu-id="ff24b-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="ff24b-144">Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="ff24b-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="ff24b-145">Inserte el código siguiente para controlar el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="ff24b-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="ff24b-146">Este código crea una instancia de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> controlar y agrega una instancia de la `AxWindowsMediaPlayer` control como su elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="ff24b-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="ff24b-147">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff24b-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff24b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff24b-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ff24b-149">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff24b-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="ff24b-150">Tutorial: Hospedar un Control compuesto de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="ff24b-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="ff24b-151">Tutorial: Hospedar un Control compuesto de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff24b-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
