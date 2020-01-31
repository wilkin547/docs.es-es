---
title: Control compuesto de WPF en 3D de host en Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794209"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="a5f79-102">Tutorial: hospedar un control compuesto de WPF en 3D en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5f79-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="a5f79-103">En este tutorial se muestra cómo se puede crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto y hospedarlo en Windows Forms controles y formularios mediante el control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="a5f79-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in Windows Forms controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="a5f79-104">En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="a5f79-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="a5f79-105">En el <xref:System.Windows.Controls.UserControl> se muestra un cono tridimensional (3D).</span><span class="sxs-lookup"><span data-stu-id="a5f79-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="a5f79-106">La representación de objetos 3D es mucho más fácil con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5f79-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with Windows Forms.</span></span> <span data-ttu-id="a5f79-107">Por lo tanto, tiene sentido hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> clase para crear gráficos 3D en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5f79-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in Windows Forms.</span></span>

<span data-ttu-id="a5f79-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="a5f79-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a5f79-109">Crear el <xref:System.Windows.Controls.UserControl>de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f79-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="a5f79-110">Crear el proyecto de host de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5f79-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="a5f79-111">Hospedar el <xref:System.Windows.Controls.UserControl>de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f79-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5f79-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a5f79-112">Prerequisites</span></span>

<span data-ttu-id="a5f79-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="a5f79-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a5f79-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a5f79-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="a5f79-115">Crear el UserControl</span><span class="sxs-lookup"><span data-stu-id="a5f79-115">Create the UserControl</span></span>

1. <span data-ttu-id="a5f79-116">Cree un proyecto de **biblioteca de controles de usuario de WPF** denominado `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="a5f79-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="a5f79-117">Abra UserControl1. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="a5f79-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="a5f79-118">Reemplace el código generado por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5f79-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="a5f79-119">Este código define una <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="a5f79-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="a5f79-120">El primer control secundario es un control de <xref:System.Windows.Controls.Label?displayProperty=nameWithType>; el segundo es un control <xref:System.Windows.Controls.Viewport3D> que muestra un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="a5f79-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="a5f79-121">Crear el proyecto de host</span><span class="sxs-lookup"><span data-stu-id="a5f79-121">Create the host project</span></span>

1. <span data-ttu-id="a5f79-122">Agregue un proyecto de **Windows Forms App (.NET Framework)** denominado `WpfUserControlHost` a la solución.</span><span class="sxs-lookup"><span data-stu-id="a5f79-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="a5f79-123">En **Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="a5f79-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="a5f79-124">Agregue referencias a los siguientes ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a5f79-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="a5f79-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="a5f79-125">PresentationCore</span></span>

    - <span data-ttu-id="a5f79-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="a5f79-126">PresentationFramework</span></span>

    - <span data-ttu-id="a5f79-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="a5f79-127">WindowsBase</span></span>

4. <span data-ttu-id="a5f79-128">Agregue una referencia al proyecto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="a5f79-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="a5f79-129">En Explorador de soluciones, establezca el proyecto de `WpfUserControlHost` como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="a5f79-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="a5f79-130">Hospede el UserControl</span><span class="sxs-lookup"><span data-stu-id="a5f79-130">Host the UserControl</span></span>

1. <span data-ttu-id="a5f79-131">En el Diseñador de Windows Forms, abra Form1.</span><span class="sxs-lookup"><span data-stu-id="a5f79-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="a5f79-132">En el ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el evento de <xref:System.Windows.Forms.Form.Load> para crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a5f79-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="a5f79-133">El editor de código se abre en el controlador de eventos `Form1_Load` recién generado.</span><span class="sxs-lookup"><span data-stu-id="a5f79-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="a5f79-134">Reemplace el código de Form1.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5f79-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="a5f79-135">El controlador de eventos `Form1_Load` crea una instancia de `UserControl1` y agrega trabajará a la colección de controles secundarios del control <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="a5f79-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="a5f79-136">El control <xref:System.Windows.Forms.Integration.ElementHost> se agrega a la colección de controles secundarios del formulario.</span><span class="sxs-lookup"><span data-stu-id="a5f79-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="a5f79-137">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5f79-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5f79-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5f79-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a5f79-139">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a5f79-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a5f79-140">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5f79-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="a5f79-141">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="a5f79-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a5f79-142">Hospedar un control compuesto de WPF en Windows Forms ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5f79-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
