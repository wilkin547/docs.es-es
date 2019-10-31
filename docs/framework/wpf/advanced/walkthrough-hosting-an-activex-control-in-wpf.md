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
ms.openlocfilehash: 8679181d720d9550cf60034a7cf1809b79198e83
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197889"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="a10fa-102">Tutorial: Hospedar un control ActiveX en WPF</span><span class="sxs-lookup"><span data-stu-id="a10fa-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="a10fa-103">Para habilitar la interacción mejorada con los exploradores, puede usar los controles ActiveX de Microsoft en la aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a10fa-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="a10fa-104">En este tutorial se muestra cómo puede hospedar el Media Player de Microsoft Windows como un control en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a10fa-104">This walkthrough demonstrates how you can host the Microsoft Windows Media Player as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="a10fa-105">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="a10fa-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a10fa-106">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a10fa-106">Creating the project.</span></span>

- <span data-ttu-id="a10fa-107">Crear el control ActiveX.</span><span class="sxs-lookup"><span data-stu-id="a10fa-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="a10fa-108">Hospedar el control ActiveX en una página de WPF.</span><span class="sxs-lookup"><span data-stu-id="a10fa-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="a10fa-109">Cuando haya completado este tutorial, aprenderá a usar los controles ActiveX de Microsoft en la aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a10fa-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a10fa-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a10fa-110">Prerequisites</span></span>
 <span data-ttu-id="a10fa-111">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="a10fa-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a10fa-112">Microsoft Windows Media Player instalado en el equipo donde está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a10fa-112">Microsoft Windows Media Player installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="a10fa-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="a10fa-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a10fa-114">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="a10fa-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="a10fa-115">Para crear y configurar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a10fa-115">To create and set up the project</span></span>

1. <span data-ttu-id="a10fa-116">Cree un proyecto de aplicación de WPF denominado `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="a10fa-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="a10fa-117">Agregue un proyecto de biblioteca de controles Windows Forms a la solución y asigne al proyecto el nombre `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="a10fa-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="a10fa-118">En el proyecto WmpAxLib, agregue una referencia al ensamblado de Windows Media Player, que se denomina wmp. dll.</span><span class="sxs-lookup"><span data-stu-id="a10fa-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="a10fa-119">Abra el **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="a10fa-120">Haga clic con el botón secundario en el **cuadro de herramientas**y haga clic en **elegir elementos**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="a10fa-121">Haga clic en la pestaña **componentes com** , seleccione el control **Windows Media Player** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="a10fa-122">El control Media Player de Windows se agrega al **cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="a10fa-123">En Explorador de soluciones, haga clic con el botón secundario en el archivo **UserControl1** y, a continuación, haga clic en **cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="a10fa-124">Cambie el nombre a `WmpAxControl.vb` o `WmpAxControl.cs`, según el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a10fa-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="a10fa-125">Si se le pide que cambie el nombre de todas las referencias, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="a10fa-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="a10fa-126">Crear el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="a10fa-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="a10fa-127">Visual Studio genera automáticamente una clase contenedora <xref:System.Windows.Forms.AxHost> para un control ActiveX de Microsoft cuando el control se agrega a una superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="a10fa-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="a10fa-128">En el procedimiento siguiente se crea un ensamblado administrado denominado AxInterop. WMPLib. dll.</span><span class="sxs-lookup"><span data-stu-id="a10fa-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="a10fa-129">Para crear el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="a10fa-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="a10fa-130">Abra WmpAxControl. vb o WmpAxControl.cs en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a10fa-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="a10fa-131">En el **cuadro de herramientas**, agregue el control Media Player de Windows a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="a10fa-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="a10fa-132">En el ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control Media Player de Windows en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a10fa-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="a10fa-133">Compile el proyecto de biblioteca de controles WmpAxLib.</span><span class="sxs-lookup"><span data-stu-id="a10fa-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="a10fa-134">Hospedar el control ActiveX en una página de WPF</span><span class="sxs-lookup"><span data-stu-id="a10fa-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="a10fa-135">Para hospedar el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="a10fa-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="a10fa-136">En el proyecto HostingAxInWpf, agregue una referencia al ensamblado de interoperabilidad ActiveX generado.</span><span class="sxs-lookup"><span data-stu-id="a10fa-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="a10fa-137">Este ensamblado se denomina AxInterop. WMPLib. dll y se agregó a la carpeta de depuración del proyecto WmpAxLib cuando importó el control Media Player de Windows.</span><span class="sxs-lookup"><span data-stu-id="a10fa-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="a10fa-138">Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="a10fa-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="a10fa-139">Agregue una referencia al ensamblado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], que se denomina System. Windows. Forms. dll.</span><span class="sxs-lookup"><span data-stu-id="a10fa-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="a10fa-140">Abra MainWindow. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="a10fa-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="a10fa-141">Asigne al elemento <xref:System.Windows.Controls.Grid> el nombre `grid1`.</span><span class="sxs-lookup"><span data-stu-id="a10fa-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="a10fa-142">En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="a10fa-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="a10fa-143">En el ventana Propiedades, haga clic en la pestaña **eventos** .</span><span class="sxs-lookup"><span data-stu-id="a10fa-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="a10fa-144">Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="a10fa-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="a10fa-145">Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="a10fa-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="a10fa-146">Este código crea una instancia del control <xref:System.Windows.Forms.Integration.WindowsFormsHost> y agrega una instancia del control `AxWindowsMediaPlayer` como su elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="a10fa-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="a10fa-147">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a10fa-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10fa-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a10fa-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a10fa-149">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a10fa-149">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a10fa-150">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="a10fa-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a10fa-151">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a10fa-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
