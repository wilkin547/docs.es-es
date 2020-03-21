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
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Cómo: Crear un complemento que devuelva una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que devuelve un Windows Presentation Foundation (WPF) a un host WPFWPF aplicación independiente.  
  
 El complemento devuelve una interfaz de usuario que es un CONTROL de usuario WPFWPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación independiente WPFWPF hospeda el complemento y muestra el control de usuario (devuelta por el complemento) como el contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resaltan las extensiones de WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se supone lo siguiente:  
  
- Conocimiento del modelo de complemento de .NET Framework, incluida la canalización, el complemento y el desarrollo de hosts. Si no está familiarizado con estos [conceptos, consulte Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, vea [Tutorial: crear una aplicación extensible](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Conocimiento de las extensiones de WPFwpf para el modelo de complemento de .NET Framework, que se puede encontrar aquí: Información general sobre [complementos](wpf-add-ins-overview.md)de WPF .  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que devuelve una interfaz de usuario de WPFWPF requiere código específico para cada segmento de canalización, el complemento y la aplicación host.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Un método debe definirse por el contrato para devolver una interfaz de usuario y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>. Esto se demuestra `GetAddInUI` mediante `IWPFAddInContract` el método del contrato en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento implementa las configuraciones de <xref:System.Windows.FrameworkElement>usuario que proporciona como subclases de `IWPFAddInView.GetAddInUI` , el método <xref:System.Windows.FrameworkElement>en la vista de complemento que se correlaciona con debe devolver un valor de tipo . En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 El método contract <xref:System.AddIn.Contract.INativeHandleContract>devuelve un , pero <xref:System.Windows.FrameworkElement> el complemento devuelve un (según lo especificado por la vista del complemento). Por lo <xref:System.Windows.FrameworkElement> tanto, el <xref:System.AddIn.Contract.INativeHandleContract> debe convertirse en un antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador de <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>complemento mediante una llamada a , como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 Dado que la aplicación <xref:System.Windows.FrameworkElement>host mostrará un , el método `IWPFAddInHostView.GetAddInUI` en la vista <xref:System.Windows.FrameworkElement>de host que se correlaciona con debe devolver un valor de tipo . En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 El método contract <xref:System.AddIn.Contract.INativeHandleContract>devuelve un , pero <xref:System.Windows.FrameworkElement> la aplicación host espera un (según lo especificado por la vista de host). Por lo <xref:System.AddIn.Contract.INativeHandleContract> tanto, el <xref:System.Windows.FrameworkElement> debe convertirse en un después de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>del lado host llamando a , como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador de complemento y la vista de complemento`WPFAddIn1.AddIn`creados, `IWPFAddInView.GetAddInUI` el complemento <xref:System.Windows.FrameworkElement> ( ) <xref:System.Windows.Controls.UserControl> debe implementar el método para devolver un objeto (a en este ejemplo). La implementación <xref:System.Windows.Controls.UserControl> `AddInUI`de la , , se muestra mediante el código siguiente.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 La implementación `IWPFAddInView.GetAddInUI` del complemento by simply necesita return `AddInUI`a new instance of , como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador del lado host y la vista de host creados, la aplicación host puede usar el modelo de `IWPFAddInHostView.GetAddInUI` complemento de .NET Framework para abrir la canalización, adquirir una vista de host del complemento y llamar al método. Estos pasos se muestran en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Consulte también

- [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](wpf-add-ins-overview.md)
