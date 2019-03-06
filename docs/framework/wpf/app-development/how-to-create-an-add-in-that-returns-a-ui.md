---
title: Filtrar Crear un complemento que devuelva una interfaz de usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: bf69a22f60724513122b5f17c5dd55bffc1fe561
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364884"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="c6c48-102">Filtrar Crear un complemento que devuelva una interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c6c48-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="c6c48-103">En este ejemplo se muestra cómo crear un complemento que devuelve Windows Presentation Foundation (WPF) a un host de aplicación independiente de WPF.</span><span class="sxs-lookup"><span data-stu-id="c6c48-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="c6c48-104">El complemento devuelve una interfaz de usuario que es un control de usuario WPF.</span><span class="sxs-lookup"><span data-stu-id="c6c48-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="c6c48-105">El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="c6c48-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="c6c48-106">La aplicación de WPF independiente hospeda el complemento y muestra el control de usuario (devuelto por el complemento) como el contenido de la ventana principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6c48-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="c6c48-107">**Requisitos previos**</span><span class="sxs-lookup"><span data-stu-id="c6c48-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="c6c48-108">En este ejemplo se resalta las extensiones WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se da por supuesto lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6c48-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="c6c48-109">Conocimiento de que el complemento de modelo de .NET Framework, como canalización, complementos y desarrollo de host.</span><span class="sxs-lookup"><span data-stu-id="c6c48-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="c6c48-110">Si no está familiarizado con estos conceptos, consulte [complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="c6c48-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="c6c48-111">Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: Crear una aplicación Extensible](../../add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="c6c48-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="c6c48-112">Conocimiento de las extensiones WPF para el complemento de modelo de .NET Framework, que puede encontrarse aquí: [Información general sobre complementos WPF](wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c6c48-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c48-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6c48-113">Example</span></span>  
 <span data-ttu-id="c6c48-114">Para crear un complemento que devuelva que una UI de WPF necesita un código concreto para cada segmento de canalización, el complemento y la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="c6c48-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="c6c48-115">Implementar el segmento de canalización del contrato</span><span class="sxs-lookup"><span data-stu-id="c6c48-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="c6c48-116">Se debe definir un método por el contrato para devolver una interfaz de usuario y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="c6c48-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="c6c48-117">Esto se demuestra el `GetAddInUI` método de la `IWPFAddInContract` de contrato en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="c6c48-118">Implementar el segmento de canalización de la vista de complemento</span><span class="sxs-lookup"><span data-stu-id="c6c48-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="c6c48-119">Dado que el complemento implementa la [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que se correlaciona con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="c6c48-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="c6c48-120">En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6c48-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="c6c48-121">Implementar el segmento de canalización del adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="c6c48-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="c6c48-122">El método del contrato devuelve una <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve una <xref:System.Windows.FrameworkElement> (tal y como especifica la vista de complemento).</span><span class="sxs-lookup"><span data-stu-id="c6c48-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="c6c48-123">Por lo tanto, el <xref:System.Windows.FrameworkElement> deben convertirse a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="c6c48-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="c6c48-124">Este trabajo lo realiza el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="c6c48-125">Implementar el segmento de canalización de la vista host</span><span class="sxs-lookup"><span data-stu-id="c6c48-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="c6c48-126">Dado que la aplicación host mostrará un <xref:System.Windows.FrameworkElement>, el método en la vista del host que se correlaciona con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="c6c48-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="c6c48-127">En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6c48-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="c6c48-128">Implementar el segmento de canalización del adaptador del host</span><span class="sxs-lookup"><span data-stu-id="c6c48-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="c6c48-129">El método del contrato devuelve una <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un <xref:System.Windows.FrameworkElement> (tal y como especifica la vista del host).</span><span class="sxs-lookup"><span data-stu-id="c6c48-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="c6c48-130">Por lo tanto, el <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="c6c48-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="c6c48-131">Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="c6c48-132">Implementar el complemento</span><span class="sxs-lookup"><span data-stu-id="c6c48-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="c6c48-133">Con el adaptador del complemento y vista de complemento creado, el complemento (`WPFAddIn1.AddIn`) debe implementar la `IWPFAddInView.GetAddInUI` método devuelva un <xref:System.Windows.FrameworkElement> objeto (un <xref:System.Windows.Controls.UserControl> en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="c6c48-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="c6c48-134">La implementación de la <xref:System.Windows.Controls.UserControl>, `AddInUI`, se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="c6c48-135">La implementación de la `IWPFAddInView.GetAddInUI` mediante el complemento únicamente tiene que devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="c6c48-136">Implementación de la aplicación host</span><span class="sxs-lookup"><span data-stu-id="c6c48-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="c6c48-137">Con el adaptador del host y la vista host creados, la aplicación host puede utilizar el modelo de complementos de .NET Framework para abrir la canalización, adquirir una vista de host del complemento y llamada la `IWPFAddInHostView.GetAddInUI` método.</span><span class="sxs-lookup"><span data-stu-id="c6c48-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="c6c48-138">Estos pasos se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c6c48-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="c6c48-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6c48-139">See also</span></span>
- <span data-ttu-id="c6c48-140">[Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="c6c48-140">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="c6c48-141">Información general sobre los complementos de WPF</span><span class="sxs-lookup"><span data-stu-id="c6c48-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
