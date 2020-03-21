---
title: 'Cómo: Crear un complemento que devuelva una interfaz de usuario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174594"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="4a2cc-102">Cómo: Crear un complemento que devuelva una interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4a2cc-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="4a2cc-103">En este ejemplo se muestra cómo crear un complemento que devuelve un Windows Presentation Foundation (WPF) a un host WPFWPF aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="4a2cc-104">El complemento devuelve una interfaz de usuario que es un CONTROL de usuario WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="4a2cc-105">El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="4a2cc-106">La aplicación independiente WPFWPF hospeda el complemento y muestra el control de usuario (devuelta por el complemento) como el contenido de la ventana principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="4a2cc-107">**Requisitos previos**</span><span class="sxs-lookup"><span data-stu-id="4a2cc-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="4a2cc-108">En este ejemplo se resaltan las extensiones de WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se supone lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a2cc-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="4a2cc-109">Conocimiento del modelo de complemento de .NET Framework, incluida la canalización, el complemento y el desarrollo de hosts.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="4a2cc-110">Si no está familiarizado con estos [conceptos, consulte Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="4a2cc-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="4a2cc-111">Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, vea [Tutorial: crear una aplicación extensible](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="4a2cc-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="4a2cc-112">Conocimiento de las extensiones de WPFwpf para el modelo de complemento de .NET Framework, que se puede encontrar aquí: Información general sobre [complementos](wpf-add-ins-overview.md)de WPF .</span><span class="sxs-lookup"><span data-stu-id="4a2cc-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a2cc-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a2cc-113">Example</span></span>  
 <span data-ttu-id="4a2cc-114">Para crear un complemento que devuelve una interfaz de usuario de WPFWPF requiere código específico para cada segmento de canalización, el complemento y la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="4a2cc-115">Implementar el segmento de canalización del contrato</span><span class="sxs-lookup"><span data-stu-id="4a2cc-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="4a2cc-116">Un método debe definirse por el contrato para devolver una interfaz de usuario y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="4a2cc-117">Esto se demuestra `GetAddInUI` mediante `IWPFAddInContract` el método del contrato en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="4a2cc-118">Implementar el segmento de canalización de la vista de complemento</span><span class="sxs-lookup"><span data-stu-id="4a2cc-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="4a2cc-119">Dado que el complemento implementa las configuraciones de <xref:System.Windows.FrameworkElement>usuario que proporciona como subclases de `IWPFAddInView.GetAddInUI` , el método <xref:System.Windows.FrameworkElement>en la vista de complemento que se correlaciona con debe devolver un valor de tipo .</span><span class="sxs-lookup"><span data-stu-id="4a2cc-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4a2cc-120">En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="4a2cc-121">Implementar el segmento de canalización del adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="4a2cc-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="4a2cc-122">El método contract <xref:System.AddIn.Contract.INativeHandleContract>devuelve un , pero <xref:System.Windows.FrameworkElement> el complemento devuelve un (según lo especificado por la vista del complemento).</span><span class="sxs-lookup"><span data-stu-id="4a2cc-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="4a2cc-123">Por lo <xref:System.Windows.FrameworkElement> tanto, el <xref:System.AddIn.Contract.INativeHandleContract> debe convertirse en un antes de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="4a2cc-124">Este trabajo lo realiza el adaptador de <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>complemento mediante una llamada a , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="4a2cc-125">Implementar el segmento de canalización de la vista host</span><span class="sxs-lookup"><span data-stu-id="4a2cc-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="4a2cc-126">Dado que la aplicación <xref:System.Windows.FrameworkElement>host mostrará un , el método `IWPFAddInHostView.GetAddInUI` en la vista <xref:System.Windows.FrameworkElement>de host que se correlaciona con debe devolver un valor de tipo .</span><span class="sxs-lookup"><span data-stu-id="4a2cc-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4a2cc-127">En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="4a2cc-128">Implementar el segmento de canalización del adaptador del host</span><span class="sxs-lookup"><span data-stu-id="4a2cc-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="4a2cc-129">El método contract <xref:System.AddIn.Contract.INativeHandleContract>devuelve un , pero <xref:System.Windows.FrameworkElement> la aplicación host espera un (según lo especificado por la vista de host).</span><span class="sxs-lookup"><span data-stu-id="4a2cc-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="4a2cc-130">Por lo <xref:System.AddIn.Contract.INativeHandleContract> tanto, el <xref:System.Windows.FrameworkElement> debe convertirse en un después de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="4a2cc-131">Este trabajo lo realiza el adaptador <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>del lado host llamando a , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a><span data-ttu-id="4a2cc-132">Implementar el complemento</span><span class="sxs-lookup"><span data-stu-id="4a2cc-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="4a2cc-133">Con el adaptador de complemento y la vista de complemento`WPFAddIn1.AddIn`creados, `IWPFAddInView.GetAddInUI` el complemento <xref:System.Windows.FrameworkElement> ( ) <xref:System.Windows.Controls.UserControl> debe implementar el método para devolver un objeto (a en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="4a2cc-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="4a2cc-134">La implementación <xref:System.Windows.Controls.UserControl> `AddInUI`de la , , se muestra mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="4a2cc-135">La implementación `IWPFAddInView.GetAddInUI` del complemento by simply necesita return `AddInUI`a new instance of , como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="4a2cc-136">Implementación de la aplicación host</span><span class="sxs-lookup"><span data-stu-id="4a2cc-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="4a2cc-137">Con el adaptador del lado host y la vista de host creados, la aplicación host puede usar el modelo de `IWPFAddInHostView.GetAddInUI` complemento de .NET Framework para abrir la canalización, adquirir una vista de host del complemento y llamar al método.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="4a2cc-138">Estos pasos se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a2cc-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="4a2cc-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a2cc-139">See also</span></span>

- <span data-ttu-id="4a2cc-140">[Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="4a2cc-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="4a2cc-141">Información general sobre los complementos de WPF</span><span class="sxs-lookup"><span data-stu-id="4a2cc-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
