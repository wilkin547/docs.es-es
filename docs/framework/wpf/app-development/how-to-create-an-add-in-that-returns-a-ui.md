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
ms.openlocfilehash: faed11bb02037ea42b31402d431e1bcdd8b70339
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115757"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Filtrar Crear un complemento que devuelva una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que devuelve Windows Presentation Foundation (WPF) a un host de aplicación independiente de WPF.  
  
 El complemento devuelve una interfaz de usuario que es un control de usuario WPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación de WPF independiente hospeda el complemento y muestra el control de usuario (devuelto por el complemento) como el contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resalta las extensiones WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se da por supuesto lo siguiente:  
  
-   Conocimiento de que el complemento de modelo de .NET Framework, como canalización, complementos y desarrollo de host. Si no está familiarizado con estos conceptos, consulte [complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: Crear una aplicación Extensible](../../add-ins/walkthrough-create-extensible-app.md).  
  
-   Conocimiento de las extensiones WPF para el complemento de modelo de .NET Framework, que puede encontrarse aquí: [Información general sobre complementos WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que devuelva que una UI de WPF necesita un código concreto para cada segmento de canalización, el complemento y la aplicación host.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Se debe definir un método por el contrato para devolver una interfaz de usuario y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>. Esto se demuestra el `GetAddInUI` método de la `IWPFAddInContract` de contrato en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento implementa la [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que se correlaciona con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 El método del contrato devuelve una <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve una <xref:System.Windows.FrameworkElement> (tal y como especifica la vista de complemento). Por lo tanto, el <xref:System.Windows.FrameworkElement> deben convertirse a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 Dado que la aplicación host mostrará un <xref:System.Windows.FrameworkElement>, el método en la vista del host que se correlaciona con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 El método del contrato devuelve una <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un <xref:System.Windows.FrameworkElement> (tal y como especifica la vista del host). Por lo tanto, el <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador del complemento y vista de complemento creado, el complemento (`WPFAddIn1.AddIn`) debe implementar la `IWPFAddInView.GetAddInUI` método devuelva un <xref:System.Windows.FrameworkElement> objeto (un <xref:System.Windows.Controls.UserControl> en este ejemplo). La implementación de la <xref:System.Windows.Controls.UserControl>, `AddInUI`, se muestra en el código siguiente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 La implementación de la `IWPFAddInView.GetAddInUI` mediante el complemento únicamente tiene que devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador del host y la vista host creados, la aplicación host puede utilizar el modelo de complementos de .NET Framework para abrir la canalización, adquirir una vista de host del complemento y llamada la `IWPFAddInHostView.GetAddInUI` método. Estos pasos se muestran en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vea también

- [Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](wpf-add-ins-overview.md)
