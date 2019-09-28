---
title: 'Tutorial: Hospedar un control compuesto 3D de WPF en formularios Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a35f2b4062edb18914c55046a69dcd9b8825d778
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353840"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="773d2-102">Tutorial: Hospedar un control compuesto 3D de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="773d2-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="773d2-103">En este tutorial se muestra cómo se puede crear un control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y cómo hospedarlo en controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y formularios mediante el control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="773d2-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="773d2-104">En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="773d2-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="773d2-105">El <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional (3D).</span><span class="sxs-lookup"><span data-stu-id="773d2-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="773d2-106">La representación de objetos 3D es mucho más fácil con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="773d2-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="773d2-107">Por lo tanto, tiene sentido hospedar una clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> para crear gráficos 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="773d2-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="773d2-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="773d2-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="773d2-109">Crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="773d2-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="773d2-110">Crear el proyecto de host de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="773d2-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="773d2-111">Hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="773d2-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="773d2-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="773d2-112">Prerequisites</span></span>

<span data-ttu-id="773d2-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="773d2-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="773d2-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="773d2-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="773d2-115">Crear el UserControl</span><span class="sxs-lookup"><span data-stu-id="773d2-115">Create the UserControl</span></span>

1. <span data-ttu-id="773d2-116">Cree un proyecto de **biblioteca de controles de usuario de WPF** denominado `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="773d2-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="773d2-117">Abra UserControl1. XAML en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="773d2-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="773d2-118">Reemplace el código generado por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="773d2-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="773d2-119">Este código define un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="773d2-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="773d2-120">El primer control secundario es un control <xref:System.Windows.Controls.Label?displayProperty=nameWithType>; el segundo es un control <xref:System.Windows.Controls.Viewport3D> que muestra un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="773d2-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="773d2-121">Crear el proyecto de host</span><span class="sxs-lookup"><span data-stu-id="773d2-121">Create the host project</span></span>

1. <span data-ttu-id="773d2-122">Agregue un proyecto de **Windows Forms App (.NET Framework)** denominado `WpfUserControlHost` a la solución.</span><span class="sxs-lookup"><span data-stu-id="773d2-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="773d2-123">En **Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="773d2-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="773d2-124">Agregue referencias a los siguientes ensamblados [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="773d2-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="773d2-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="773d2-125">PresentationCore</span></span>

    - <span data-ttu-id="773d2-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="773d2-126">PresentationFramework</span></span>

    - <span data-ttu-id="773d2-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="773d2-127">WindowsBase</span></span>

4. <span data-ttu-id="773d2-128">Agregue una referencia al proyecto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="773d2-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="773d2-129">En Explorador de soluciones, establezca el proyecto `WpfUserControlHost` como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="773d2-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="773d2-130">Hospede el UserControl</span><span class="sxs-lookup"><span data-stu-id="773d2-130">Host the UserControl</span></span>

1. <span data-ttu-id="773d2-131">En el Diseñador de Windows Forms, abra Form1.</span><span class="sxs-lookup"><span data-stu-id="773d2-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="773d2-132">En el ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el evento <xref:System.Windows.Forms.Form.Load> para crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="773d2-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="773d2-133">El editor de código se abre en el controlador de eventos `Form1_Load` recién generado.</span><span class="sxs-lookup"><span data-stu-id="773d2-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="773d2-134">Reemplace el código de Form1.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="773d2-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="773d2-135">El controlador de eventos `Form1_Load` crea una instancia de `UserControl1` y agrega trabajará a la colección de controles secundarios del control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="773d2-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="773d2-136">El control <xref:System.Windows.Forms.Integration.ElementHost> se agrega a la colección de controles secundarios del formulario.</span><span class="sxs-lookup"><span data-stu-id="773d2-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="773d2-137">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="773d2-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="773d2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="773d2-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="773d2-139">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="773d2-139">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="773d2-140">Tutorial: Hospedar un control compuesto de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="773d2-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="773d2-141">Tutorial: Hospedar un control compuesto de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="773d2-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="773d2-142">Hospedar un control compuesto de WPF en Windows Forms ejemplo</span><span class="sxs-lookup"><span data-stu-id="773d2-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
