---
title: 'Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: d84fe4314a162b4ed5d7d710964882dec85e8524
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486875"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="cb628-102">Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb628-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="cb628-103">Este tutorial muestra cómo puede crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] compuesto controlar y hospedarlo en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y formularios mediante el uso de la <xref:System.Windows.Forms.Integration.ElementHost> control.</span><span class="sxs-lookup"><span data-stu-id="cb628-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="cb628-104">En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="cb628-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="cb628-105">La <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional de (3D).</span><span class="sxs-lookup"><span data-stu-id="cb628-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="cb628-106">Representar objetos 3D es mucho más fácil con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb628-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="cb628-107">Por lo tanto, tiene sentido para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> clase para crear gráficos en 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb628-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="cb628-108">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="cb628-108">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="cb628-109">Crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="cb628-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

-   <span data-ttu-id="cb628-110">Crear el proyecto de host de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cb628-110">Creating the Windows Forms host project.</span></span>

-   <span data-ttu-id="cb628-111">Hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="cb628-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb628-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cb628-112">Prerequisites</span></span>

<span data-ttu-id="cb628-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="cb628-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="cb628-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="cb628-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="cb628-115">Crear la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="cb628-115">Create the UserControl</span></span>

1.  <span data-ttu-id="cb628-116">Crear un **biblioteca de controles de usuario de WPF** proyecto denominado `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="cb628-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2.  <span data-ttu-id="cb628-117">Abra UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb628-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3.  <span data-ttu-id="cb628-118">Reemplace el código generado por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="cb628-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="cb628-119">Este código define un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="cb628-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="cb628-120">El primer control secundario es un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; el segundo es un <xref:System.Windows.Controls.Viewport3D> control que muestra un cono 3D.</span><span class="sxs-lookup"><span data-stu-id="cb628-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="cb628-121">Crear el proyecto de host</span><span class="sxs-lookup"><span data-stu-id="cb628-121">Create the host project</span></span>

1.  <span data-ttu-id="cb628-122">Agregar un **aplicación de WPF (.NET Framework)** proyecto denominado `WpfUserControlHost` a la solución.</span><span class="sxs-lookup"><span data-stu-id="cb628-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="cb628-123">Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="cb628-123">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>

2.  <span data-ttu-id="cb628-124">En **el Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="cb628-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="cb628-125">Agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados:</span><span class="sxs-lookup"><span data-stu-id="cb628-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    -   <span data-ttu-id="cb628-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="cb628-126">PresentationCore</span></span>

    -   <span data-ttu-id="cb628-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="cb628-127">PresentationFramework</span></span>

    -   <span data-ttu-id="cb628-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="cb628-128">WindowsBase</span></span>

4.  <span data-ttu-id="cb628-129">Agregue una referencia al proyecto `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="cb628-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5.  <span data-ttu-id="cb628-130">En el Explorador de soluciones, establezca el `WpfUserControlHost` proyecto para que sea el proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="cb628-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="cb628-131">Hospedar el control de usuario</span><span class="sxs-lookup"><span data-stu-id="cb628-131">Host the UserControl</span></span>

1.  <span data-ttu-id="cb628-132">En el Diseñador de formularios de Windows, abra Form1.</span><span class="sxs-lookup"><span data-stu-id="cb628-132">In the Windows Forms Designer, open Form1.</span></span>

2.  <span data-ttu-id="cb628-133">En la ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el <xref:System.Windows.Forms.Form.Load> evento para crear un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cb628-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="cb628-134">Se abre el Editor de código en la recién generado `Form1_Load` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cb628-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3.  <span data-ttu-id="cb628-135">Reemplace el código en Form1.cs con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb628-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="cb628-136">El `Form1_Load` controlador de eventos crea una instancia de `UserControl1` y agrega sus el <xref:System.Windows.Forms.Integration.ElementHost> colección de controles secundarios del control.</span><span class="sxs-lookup"><span data-stu-id="cb628-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="cb628-137">El <xref:System.Windows.Forms.Integration.ElementHost> control se agrega a la colección del formulario de controles secundarios.</span><span class="sxs-lookup"><span data-stu-id="cb628-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4.  <span data-ttu-id="cb628-138">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cb628-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb628-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb628-139">See Also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="cb628-140">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb628-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="cb628-141">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb628-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="cb628-142">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="cb628-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="cb628-143">Hospedar un Control compuesto de WPF en el ejemplo de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb628-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)