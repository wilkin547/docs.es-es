---
title: "C&#243;mo: Crear un complemento que devuelva una interfaz de usuario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "complemento [WPF], devuelve una interfaz de usuario"
  - "crear un complemento que devuelva una interfaz de usuario [WPF]"
  - "implementar segmentos de canalización de complemento [WPF]"
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear un complemento que devuelva una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que devuelve una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] a una aplicación host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] independiente.  
  
 El complemento devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que es un control de usuario de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él.  La aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] independiente hospeda el complemento y muestra el control de usuario \(devuelto por el complemento\) como el contenido de la ventana de la aplicación principal.  
  
 **Requisitos previos**  
  
 En este ejemplo se resaltan las extensiones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] del modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que habilitan este escenario y se supone lo siguiente:  
  
-   Conocimientos del modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], lo que incluye la programación de canalizaciones, complementos y host.  Si no está familiarizado con estos conceptos, vea [Complementos y extensibilidad](../../../../ml/index.xml).  Para obtener un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, vea [Tutorial: Crear una aplicación extensible](../Topic/Walkthrough:%20Creating%20an%20Extensible%20Application.md).  
  
-   Conocimientos de las extensiones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] del modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que encontrará en [Información general sobre los complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## Ejemplo  
 Para crear un complemento que devuelve una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se necesita un código concreto para cada segmento de la canalización, el complemento y la aplicación host.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Contract"></a>   
## Implementar el segmento de canalización del contrato  
 El contrato debe definir un método para devolver una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>.  El método `GetAddInUI` del contrato `IWPFAddInContract` lo muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento implementa las [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] que proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que guarda correlación con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.  En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## Implementar el segmento de canalización del adaptador de conversión  
 El método del contrato devuelve una interfaz <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve un objeto <xref:System.Windows.FrameworkElement> \(según lo especificado en la vista de complemento\).  Por consiguiente, el objeto <xref:System.Windows.FrameworkElement> se debe convertir en una interfaz <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento.  Este trabajo lo realiza el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## Implementar el segmento de canalización de la vista de host  
 Dado que la aplicación host mostrará un objeto <xref:System.Windows.FrameworkElement>, el método en la vista de host que guarda correlación con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>.  En el código siguiente se muestra la vista de host del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## Implementar el segmento de canalización del adaptador del host  
 El método del contrato devuelve una interfaz <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un objeto <xref:System.Windows.FrameworkElement> \(según lo especificado por la vista de host\).  Por consiguiente, la interfaz <xref:System.AddIn.Contract.INativeHandleContract> se debe convertir en un objeto <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento.  Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## Implementar el complemento  
 Con el adaptador y la vista de conversión creados, el complemento \(`WPFAddIn1.AddIn`\) debe implementar el método `IWPFAddInView.GetAddInUI` para que se devuelva un objeto <xref:System.Windows.FrameworkElement> \(<xref:System.Windows.Controls.UserControl> en este ejemplo\).  La implementación de <xref:System.Windows.Controls.UserControl>, `AddInUI`, se muestra en el código siguiente.  
  
 [!code-xml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 La implementación de `IWPFAddInView.GetAddInUI` por parte del complemento únicamente tiene que devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## Implementar la aplicación host  
 Con el adaptador y la vista de host creados, la aplicación host puede utilizar el modelo de complementos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para abrir la canalización, adquirir una vista de host del complemento y llamar al método `IWPFAddInHostView.GetAddInUI`.  Estos pasos se muestran en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## Vea también  
 [Complementos y extensibilidad](../../../../ml/index.xml)   
 [Información general sobre los complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)