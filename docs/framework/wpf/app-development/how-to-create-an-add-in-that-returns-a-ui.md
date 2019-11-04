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
ms.openlocfilehash: d799c91b9abdf7882a0fcd3f0b656eac553b188c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460148"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Cómo: Crear un complemento que devuelva una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que devuelve una Windows Presentation Foundation (WPF) a una aplicación independiente de WPF de host.  
  
 El complemento devuelve una interfaz de usuario que es un control de usuario de WPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación independiente de WPF hospeda el complemento y muestra el control de usuario (devuelto por el complemento) como contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resaltan las extensiones de WPF al modelo de complemento .NET Framework que habilitan este escenario y se presupone lo siguiente:  
  
- Conocimiento del modelo de complementos de .NET Framework, incluidos el desarrollo de canalizaciones, complementos y hosts. Si no está familiarizado con estos conceptos, vea [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: crear una aplicación extensible](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Conocimiento de las extensiones de WPF para el modelo de complemento de .NET Framework, que se puede encontrar aquí: Introducción a los [Complementos de WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que devuelva una interfaz de usuario de WPF, se requiere código específico para cada segmento de canalización, el complemento y la aplicación host.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Un método debe definirse mediante el contrato para devolver una interfaz de usuario y su valor devuelto debe ser de tipo <xref:System.AddIn.Contract.INativeHandleContract>. Lo demuestra el método `GetAddInUI` del contrato de `IWPFAddInContract` en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento implementa las interfaces de IU que proporciona como subclases de <xref:System.Windows.FrameworkElement>, el método en la vista de complemento que se correlaciona con `IWPFAddInView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista de complemento del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 El método de contrato devuelve una <xref:System.AddIn.Contract.INativeHandleContract>, pero el complemento devuelve un <xref:System.Windows.FrameworkElement> (tal y como se especifica en la vista de complemento). Por consiguiente, el <xref:System.Windows.FrameworkElement> se debe convertir en una <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador del complemento llamando a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 Dado que la aplicación host mostrará un <xref:System.Windows.FrameworkElement>, el método en la vista host que se correlaciona con `IWPFAddInHostView.GetAddInUI` debe devolver un valor de tipo <xref:System.Windows.FrameworkElement>. En el código siguiente se muestra la vista host del contrato, implementada como una interfaz.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 El método de contrato devuelve un <xref:System.AddIn.Contract.INativeHandleContract>, pero la aplicación host espera un <xref:System.Windows.FrameworkElement> (tal y como se especifica en la vista del host). Por consiguiente, el <xref:System.AddIn.Contract.INativeHandleContract> se debe convertir en un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador del host mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador de complemento y la vista de complemento creados, el complemento (`WPFAddIn1.AddIn`) debe implementar el método `IWPFAddInView.GetAddInUI` para devolver un objeto <xref:System.Windows.FrameworkElement> (un <xref:System.Windows.Controls.UserControl> en este ejemplo). El código siguiente muestra la implementación del <xref:System.Windows.Controls.UserControl>, `AddInUI`.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 La implementación de `IWPFAddInView.GetAddInUI` por parte del complemento simplemente necesita devolver una nueva instancia de `AddInUI`, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador de host y la vista de host creados, la aplicación host puede usar el modelo de complemento de .NET Framework para abrir la canalización, adquirir una vista de host del complemento y llamar al método `IWPFAddInHostView.GetAddInUI`. Estos pasos se muestran en el código siguiente.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>Vea también

- [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](wpf-add-ins-overview.md)
