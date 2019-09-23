---
title: Procedimiento Crear un complemento que sea una interfaz de usuario
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
ms.openlocfilehash: b0e847061a30e93d36997ab603c52715e2730765
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182641"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedimiento Crear un complemento que sea una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que es un Windows Presentation Foundation (WPF) que se hospeda en una aplicación independiente de WPF.  
  
 El complemento es una interfaz de usuario que es un control de usuario de WPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación independiente de WPF hospeda la interfaz de usuario del complemento como el contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resaltan las extensiones de WPF al modelo de complemento .NET Framework que habilitan este escenario y se presupone lo siguiente:  
  
- Conocimiento del modelo de complementos de .NET Framework, incluidos el desarrollo de canalizaciones, complementos y hosts. Si no está familiarizado con estos conceptos, vea [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial en el que se muestra la implementación de una canalización, un complemento y una aplicación host [, vea Tutorial: Crear una aplicación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))extensible.  
  
- Conocimiento de las extensiones de WPF para el modelo de complemento de .NET Framework. Vea [información general sobre los complementos de WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que sea una interfaz de usuario de WPF, se requiere código específico para cada segmento de canalización, el complemento y la aplicación host.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato

Cuando un complemento es una interfaz de usuario, el contrato para el complemento debe implementar <xref:System.AddIn.Contract.INativeHandleContract>. En el ejemplo, `IWPFAddInContract` <xref:System.AddIn.Contract.INativeHandleContract>implementa, como se muestra en el código siguiente.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento

Dado que el complemento se implementa como una subclase del <xref:System.Windows.FrameworkElement> tipo, la vista de complemento también debe ser una subclase. <xref:System.Windows.FrameworkElement> En el código siguiente se muestra la vista de complemento del contrato, implementada como `WPFAddInView` la clase.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
Aquí, la vista de complemento se deriva de <xref:System.Windows.Controls.UserControl>. Por lo tanto, la interfaz de usuario del complemento también debe <xref:System.Windows.Controls.UserControl>derivar de.  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión

Aunque el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, el complemento es un <xref:System.Windows.FrameworkElement> (tal y como se especifica en el segmento de canalización de la vista de complemento). Por lo tanto <xref:System.Windows.FrameworkElement> , se debe convertir <xref:System.AddIn.Contract.INativeHandleContract> en antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador del complemento llamando a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, tal y como se muestra en el código siguiente.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

En el modelo de complemento en el que un complemento devuelve una interfaz de usuario (vea [crear un complemento que devuelve una interfaz de usuario](how-to-create-an-add-in-that-returns-a-ui.md)), el adaptador del complemento convirtió <xref:System.Windows.FrameworkElement> el <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>en <xref:System.AddIn.Contract.INativeHandleContract> un llamando a. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>también se debe llamar a en este modelo, aunque debe implementar un método desde el que escribir el código para llamarlo. Para ello, invalide <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implemente el código que <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> llama a si el código al <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> que llama está <xref:System.AddIn.Contract.INativeHandleContract>esperando. En este caso, el autor de la llamada será el adaptador del host, que se aborda en una subsección siguiente.  
  
> [!NOTE]
> También debe invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en este modelo para habilitar la tabulación entre la interfaz de usuario de la aplicación host y la interfaz de usuario del complemento. Para obtener más información, vea "limitaciones de los complementos de WPF" en [información general sobre](wpf-add-ins-overview.md)los complementos de WPF.  
  
Dado que el adaptador de complementos implementa una interfaz que se deriva de <xref:System.AddIn.Contract.INativeHandleContract>, también debe implementar <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, aunque se omite cuando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> se invalida.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host

En este modelo, la aplicación host suele esperar que la vista host sea una <xref:System.Windows.FrameworkElement> subclase. El adaptador del host debe convertir <xref:System.AddIn.Contract.INativeHandleContract> en una <xref:System.Windows.FrameworkElement> después de <xref:System.AddIn.Contract.INativeHandleContract> que cruce el límite de aislamiento. Dado que la aplicación host no llama a un método para obtener <xref:System.Windows.FrameworkElement>, la vista host debe "devolver" el <xref:System.Windows.FrameworkElement> objeto que lo contiene. Por consiguiente, la vista host debe derivar de una subclase <xref:System.Windows.FrameworkElement> de que puede contener otras interfaces de IU <xref:System.Windows.Controls.UserControl>, como. En el código siguiente se muestra la vista de host del contrato, implementada como la `WPFAddInHostView` clase.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host

Aunque el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, la aplicación host espera un <xref:System.Windows.Controls.UserControl> (tal y como se especifica en la vista del host). Por consiguiente, <xref:System.AddIn.Contract.INativeHandleContract> se debe convertir <xref:System.Windows.FrameworkElement> a después de cruzar el límite de aislamiento, antes de establecerse como contenido de la vista host (que deriva de <xref:System.Windows.Controls.UserControl>).  
  
Este trabajo lo realiza el adaptador del host, como se muestra en el código siguiente.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Como puede ver, el adaptador del host adquiere <xref:System.AddIn.Contract.INativeHandleContract> llamando al método del adaptador del <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> complemento (este <xref:System.AddIn.Contract.INativeHandleContract> es el punto en el que cruza el límite de aislamiento).  
  
A continuación, el adaptador del host convierte el <xref:System.AddIn.Contract.INativeHandleContract> en un <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>llamando a. Por último, <xref:System.Windows.FrameworkElement> se establece como el contenido de la vista host.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento

Con el adaptador y la vista de conversión en su lugar, se puede implementar el complemento derivando de la vista de complemento, como se muestra en el código siguiente.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

En este ejemplo, puede ver una ventaja interesante de este modelo: los desarrolladores de complementos solo necesitan implementar el complemento (puesto que también es la interfaz de usuario), en lugar de una clase de complemento y una interfaz de usuario de complemento.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host

Con el adaptador de host y la vista de host creados, la aplicación host puede usar el modelo de complemento de .NET Framework para abrir la canalización y adquirir una vista de host del complemento. Estos pasos se muestran en el código siguiente.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

La aplicación host usa el código del modelo de complementos de .NET Framework típico para activar el complemento, que implícitamente devuelve la vista de host a la aplicación host. Posteriormente, la aplicación host muestra la vista host (que es <xref:System.Windows.Controls.UserControl>una) de <xref:System.Windows.Controls.Grid>un.  
  
 El código para procesar interacciones con la interfaz de usuario del complemento se ejecuta en el dominio de aplicación del complemento. Estas interacciones incluyen lo siguiente:  
  
- Controlar el <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
- Que muestra <xref:System.Windows.MessageBox>.  
  
 Esta actividad está completamente aislada de la aplicación host.  
  
## <a name="see-also"></a>Vea también

- [Complementos y extensibilidad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](wpf-add-ins-overview.md)
