---
title: "Cómo: Crear un complemento que devuelva una interfaz de usuario"
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
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 361983c4e2b392cdf8410fdb1193a56f6d26d067
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="88612-102">Cómo: Crear un complemento que devuelva una interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="88612-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="88612-103">Este ejemplo muestra cómo crear un complemento que devuelve una [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a un host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="88612-103">This example shows how to create an add-in that returns a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)][!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to a host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application.</span></span>  
  
 <span data-ttu-id="88612-104">El complemento devuelve un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] control de usuario.</span><span class="sxs-lookup"><span data-stu-id="88612-104">The add-in returns a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that is a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] user control.</span></span> <span data-ttu-id="88612-105">El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él.</span><span class="sxs-lookup"><span data-stu-id="88612-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="88612-106">El [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente que se hospeda el complemento y muestra el control de usuario (devuelto por el complemento) como el contenido de la ventana de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="88612-106">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="88612-107">**Requisitos previos**</span><span class="sxs-lookup"><span data-stu-id="88612-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="88612-108">Este ejemplo se resaltan los [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos que habilitan este escenario y se da por supuesto lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88612-108">This example highlights the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model that enable this scenario, and assumes the following:</span></span>  
  
-   <span data-ttu-id="88612-109">Conocimiento de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, incluida la canalización, complemento y desarrollo de host.</span><span class="sxs-lookup"><span data-stu-id="88612-109">Knowledge of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="88612-110">Si no está familiarizado con estos conceptos, vea [complementos y extensibilidad](../../../../docs/framework/add-ins/index.md).</span><span class="sxs-lookup"><span data-stu-id="88612-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](../../../../docs/framework/add-ins/index.md).</span></span> <span data-ttu-id="88612-111">Para obtener un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: crear una aplicación Extensible](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="88612-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
-   <span data-ttu-id="88612-112">Conocimiento de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, que puede encontrarse aquí: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span><span class="sxs-lookup"><span data-stu-id="88612-112">Knowledge of the [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensions to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model, which can be found here: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="88612-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88612-113">Example</span></span>  
 <span data-ttu-id="88612-114">Para crear un complemento que devuelve una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] necesita un código concreto para cada segmento de la canalización, el complemento y la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="88612-114">To create an add-in that returns a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)][!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="88612-115">Implementar el segmento de canalización del contrato</span><span class="sxs-lookup"><span data-stu-id="88612-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="88612-116">Se debe definir un método por el contrato para devolver un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="88612-116">A method must be defined by the contract for returning a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="88612-117">Esto se demuestra la `GetAddInUI` método de la `IWPFAddInContract` de contrato en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="88612-118">Implementar el segmento de canalización de la vista de complemento</span><span class="sxs-lookup"><span data-stu-id="88612-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="88612-119">Dado que el complemento implementa la [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que se correlaciona con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="88612-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="88612-120">En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="88612-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="88612-121">Implementar el segmento de canalización del adaptador de conversión</span><span class="sxs-lookup"><span data-stu-id="88612-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="88612-122">El método de contrato devuelve un <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve un <xref:System.Windows.FrameworkElement> (según se especifica en la vista de complemento).</span><span class="sxs-lookup"><span data-stu-id="88612-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="88612-123">Por lo tanto, la <xref:System.Windows.FrameworkElement> deben convertirse en un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="88612-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="88612-124">Este trabajo se realiza mediante el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="88612-125">Implementar el segmento de canalización de la vista host</span><span class="sxs-lookup"><span data-stu-id="88612-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="88612-126">Dado que la aplicación host mostrará un <xref:System.Windows.FrameworkElement>, el método en la vista de host que se correlaciona con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="88612-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="88612-127">En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.</span><span class="sxs-lookup"><span data-stu-id="88612-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="88612-128">Implementar el segmento de canalización del adaptador del host</span><span class="sxs-lookup"><span data-stu-id="88612-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="88612-129">Devuelve el método de contrato de un <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un <xref:System.Windows.FrameworkElement> (según se especifica en la vista de host).</span><span class="sxs-lookup"><span data-stu-id="88612-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="88612-130">Por lo tanto, la <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse en un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="88612-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="88612-131">Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="88612-132">Implementar el complemento</span><span class="sxs-lookup"><span data-stu-id="88612-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="88612-133">Con el adaptador de complemento de conversión y el complemento vista creada, el complemento (`WPFAddIn1.AddIn`) debe implementar la `IWPFAddInView.GetAddInUI` método para devolver un <xref:System.Windows.FrameworkElement> objeto (un <xref:System.Windows.Controls.UserControl> en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="88612-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="88612-134">La implementación de la <xref:System.Windows.Controls.UserControl>, `AddInUI`, se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="88612-135">La implementación de la `IWPFAddInView.GetAddInUI` mediante el complemento solo es necesario devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="88612-136">Implementación de la aplicación host</span><span class="sxs-lookup"><span data-stu-id="88612-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="88612-137">Con el adaptador de host y la vista de host creados, la aplicación host puede utilizar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos para abrir la canalización, adquirir una vista de host del complemento y llamada la `IWPFAddInHostView.GetAddInUI` método.</span><span class="sxs-lookup"><span data-stu-id="88612-137">With the host-side adapter and host view created, the host application can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="88612-138">Estos pasos se muestran en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="88612-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="88612-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="88612-139">See Also</span></span>  
 [<span data-ttu-id="88612-140">Complementos y extensibilidad</span><span class="sxs-lookup"><span data-stu-id="88612-140">Add-ins and Extensibility</span></span>](../../../../docs/framework/add-ins/index.md)  
 [<span data-ttu-id="88612-141">Información general sobre los complementos de WPF</span><span class="sxs-lookup"><span data-stu-id="88612-141">WPF Add-Ins Overview</span></span>](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
