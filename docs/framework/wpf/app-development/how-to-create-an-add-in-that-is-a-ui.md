---
title: 'Cómo: Crear un complemento que sea una interfaz de usuario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141034"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Cómo: Crear un complemento que sea una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que es un Windows Presentation Foundation (WPF) hospedado por una aplicación independiente de WPFWPF.  
  
 El complemento es una interfaz de usuario que es un CONTROL de usuario WPFWPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación independiente WPFWPF hospeda la interfaz de usuario del complemento como el contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resaltan las extensiones de WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se supone lo siguiente:  
  
- Conocimiento del modelo de complemento de .NET Framework, incluida la canalización, el complemento y el desarrollo de hosts. Si no está familiarizado con estos [conceptos, consulte Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, vea [Tutorial: crear una aplicación extensible](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Conocimiento de las extensiones de WPFWPF para el modelo de complemento de .NET Framework. Consulte Información general sobre [complementos](wpf-add-ins-overview.md)de WPF .  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que es una interfaz de usuario de WPFWPF requiere código específico para cada segmento de canalización, el complemento y la aplicación host.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato

Cuando un complemento es una interfaz de usuario, <xref:System.AddIn.Contract.INativeHandleContract>el contrato del complemento debe implementar . En el `IWPFAddInContract` ejemplo, <xref:System.AddIn.Contract.INativeHandleContract>implementa , como se muestra en el código siguiente.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento

Dado que el complemento se implementa como <xref:System.Windows.FrameworkElement> una subclase del tipo, la <xref:System.Windows.FrameworkElement>vista de complemento también debe subclase . El código siguiente muestra la vista de complemento del `WPFAddInView` contrato, implementada como la clase.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
Aquí, la vista del complemento <xref:System.Windows.Controls.UserControl>se deriva de . Por lo tanto, la interfaz <xref:System.Windows.Controls.UserControl>de usuario del complemento también debe derivar de .  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión

Mientras que <xref:System.AddIn.Contract.INativeHandleContract>el contrato es un <xref:System.Windows.FrameworkElement> , el complemento es un (según lo especificado por el segmento de canalización de vista del complemento). Por lo <xref:System.Windows.FrameworkElement> tanto, el <xref:System.AddIn.Contract.INativeHandleContract> debe convertirse en un antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador de <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>complemento mediante una llamada a , como se muestra en el código siguiente.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

En el modelo de complemento donde un complemento devuelve una interfaz de usuario (consulte Crear un <xref:System.Windows.FrameworkElement> complemento <xref:System.AddIn.Contract.INativeHandleContract> que <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> [devuelve una interfaz](how-to-create-an-add-in-that-returns-a-ui.md)de usuario ), el adaptador de complemento convirtió el en un mediante una llamada a . <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>También se debe llamar en este modelo, aunque debe implementar un método desde el que escribir el código para llamarlo. Para ello, <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> invalide e implemente <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> el código que <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> llama a <xref:System.AddIn.Contract.INativeHandleContract>si el código que llama espera un archivo . En este caso, el autor de la llamada será el adaptador del host, que se aborda en una subsección siguiente.  
  
> [!NOTE]
> También debe invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en este modelo para habilitar la tabulación entre la interfaz de usuario de la aplicación host y la interfaz de usuario del complemento. Para obtener más información, vea "Limitaciones del complemento WPF" en Información general sobre [complementos](wpf-add-ins-overview.md)de WPF .  
  
Dado que el adaptador de complemento implementa una <xref:System.AddIn.Contract.INativeHandleContract>interfaz que deriva <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>de , también <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> es necesario implementar , aunque esto se omite cuando se invalida.  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host

En este modelo, la aplicación host normalmente espera <xref:System.Windows.FrameworkElement> que la vista de host sea una subclase. El adaptador del lado <xref:System.AddIn.Contract.INativeHandleContract> host <xref:System.Windows.FrameworkElement> debe <xref:System.AddIn.Contract.INativeHandleContract> convertir el a a después de que el cruce el límite de aislamiento. Dado que la aplicación host no llama a <xref:System.Windows.FrameworkElement>un método para obtener <xref:System.Windows.FrameworkElement> el , la vista de host debe "devolver" el que lo contiene. Por consiguiente, la vista de host <xref:System.Windows.FrameworkElement> debe derivar de una subclase que puede contener otras opciones de usuario, como <xref:System.Windows.Controls.UserControl>. El código siguiente muestra la vista de host `WPFAddInHostView` del contrato, implementada como clase.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host

Mientras que <xref:System.AddIn.Contract.INativeHandleContract>el contrato es un <xref:System.Windows.Controls.UserControl> , la aplicación host espera un (según lo especificado por la vista de host). Por consiguiente, <xref:System.AddIn.Contract.INativeHandleContract> se debe <xref:System.Windows.FrameworkElement> convertir el valor en un después de cruzar el límite <xref:System.Windows.Controls.UserControl>de aislamiento, antes de establecerse como contenido de la vista host (que se deriva de ).  
  
Este trabajo lo realiza el adaptador del host, como se muestra en el código siguiente.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Como puede ver, el adaptador del <xref:System.AddIn.Contract.INativeHandleContract> lado host adquiere el mediante una <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> llamada al método del <xref:System.AddIn.Contract.INativeHandleContract> adaptador del complemento (este es el punto donde el cruce el límite de aislamiento).  
  
A continuación, el adaptador <xref:System.AddIn.Contract.INativeHandleContract> del <xref:System.Windows.FrameworkElement> lado <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>host convierte el en un mediante una llamada a . Por último, <xref:System.Windows.FrameworkElement> se establece como el contenido de la vista de host.  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Implementar el complemento

Con el adaptador y la vista de conversión en su lugar, se puede implementar el complemento derivando de la vista de complemento, como se muestra en el código siguiente.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

En este ejemplo, puede ver una ventaja interesante de este modelo: los desarrolladores de complementos solo necesitan implementar el complemento (ya que también es la interfaz de usuario), en lugar de una clase de complemento y una interfaz de usuario de complemento.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host

Con el adaptador del lado host y la vista de host creados, la aplicación host puede usar el modelo de complemento de .NET Framework para abrir la canalización y adquirir una vista de host del complemento. Estos pasos se muestran en el código siguiente.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

La aplicación host usa código de modelo de complemento típico de .NET Framework para activar el complemento, que devuelve implícitamente la vista de host a la aplicación host. La aplicación host muestra posteriormente la <xref:System.Windows.Controls.UserControl>vista de <xref:System.Windows.Controls.Grid>host (que es un ) desde un archivo .  
  
 El código para procesar interacciones con la interfaz de usuario del complemento se ejecuta en el dominio de aplicación del complemento. Estas interacciones incluyen lo siguiente:  
  
- Manejo <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del evento.  
  
- Mostrando <xref:System.Windows.MessageBox>el archivo .  
  
 Esta actividad está completamente aislada de la aplicación host.  
  
## <a name="see-also"></a>Consulte también

- [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](wpf-add-ins-overview.md)
