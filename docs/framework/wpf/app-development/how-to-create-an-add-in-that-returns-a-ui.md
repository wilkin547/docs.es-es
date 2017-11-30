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
ms.openlocfilehash: dd6956f1934f8594a941b57066cc2d4d6214a9a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Cómo: Crear un complemento que devuelva una interfaz de usuario
Este ejemplo muestra cómo crear un complemento que devuelve una [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] a un host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente.  
  
 El complemento devuelve un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] control de usuario. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. El [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente que se hospeda el complemento y muestra el control de usuario (devuelto por el complemento) como el contenido de la ventana de la aplicación principal.  
  
 **Requisitos previos**  
  
 Este ejemplo se resaltan los [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos que habilitan este escenario y se da por supuesto lo siguiente:  
  
-   Conocimiento de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, incluida la canalización, complemento y desarrollo de host. Si no está familiarizado con estos conceptos, vea [complementos y extensibilidad](../../../../docs/framework/add-ins/index.md). Para obtener un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: crear una aplicación Extensible](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Conocimiento de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, que puede encontrarse aquí: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que devuelve una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] necesita un código concreto para cada segmento de la canalización, el complemento y la aplicación host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Se debe definir un método por el contrato para devolver un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>. Esto se demuestra la `GetAddInUI` método de la `IWPFAddInContract` de contrato en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento implementa la [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que se correlaciona con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 El método de contrato devuelve un <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve un <xref:System.Windows.FrameworkElement> (según se especifica en la vista de complemento). Por lo tanto, la <xref:System.Windows.FrameworkElement> deben convertirse en un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento. Este trabajo se realiza mediante el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 Dado que la aplicación host mostrará un <xref:System.Windows.FrameworkElement>, el método en la vista de host que se correlaciona con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 Devuelve el método de contrato de un <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un <xref:System.Windows.FrameworkElement> (según se especifica en la vista de host). Por lo tanto, la <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse en un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador de complemento de conversión y el complemento vista creada, el complemento (`WPFAddIn1.AddIn`) debe implementar la `IWPFAddInView.GetAddInUI` método para devolver un <xref:System.Windows.FrameworkElement> objeto (un <xref:System.Windows.Controls.UserControl> en este ejemplo). La implementación de la <xref:System.Windows.Controls.UserControl>, `AddInUI`, se muestra en el código siguiente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 La implementación de la `IWPFAddInView.GetAddInUI` mediante el complemento solo es necesario devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador de host y la vista de host creados, la aplicación host puede utilizar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos para abrir la canalización, adquirir una vista de host del complemento y llamada la `IWPFAddInHostView.GetAddInUI` método. Estos pasos se muestran en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vea también  
 [Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md)  
 [Información general sobre los complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
