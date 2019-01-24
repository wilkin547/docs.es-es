---
title: Procedimiento Crear un complemento que sea una interfaz de usuario
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: f3e1ba5fe58802e42bfaf60a98767591ec13e7c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510812"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Procedimiento Crear un complemento que sea una interfaz de usuario
En este ejemplo se muestra cómo crear un complemento que es un Windows Presentation Foundation (WPF) que se hospeda en una aplicación independiente de WPF.  
  
 El complemento es una interfaz de usuario que es un control de usuario WPF. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. La aplicación de WPF independiente hospeda el complemento de la interfaz de usuario como el contenido de la ventana principal de la aplicación.  
  
 **Requisitos previos**  
  
 En este ejemplo se resalta las extensiones WPF para el modelo de complemento de .NET Framework que habilitan este escenario y se da por supuesto lo siguiente:  
  
-   Conocimiento de que el complemento de modelo de .NET Framework, como canalización, complementos y desarrollo de host. Si no está familiarizado con estos conceptos, consulte [complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Para ver un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: Crear una aplicación Extensible](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
-   Conocimiento de las extensiones WPF para el modelo de complemento de .NET Framework. Consulte [información general sobre complementos WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que sea una UI de WPF necesita un código concreto para cada segmento de canalización, el complemento y la aplicación host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Cuando un complemento es una interfaz de usuario, debe implementar el contrato para el complemento <xref:System.AddIn.Contract.INativeHandleContract>. En el ejemplo, `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento se implementa como una subclase de la <xref:System.Windows.FrameworkElement> tipo, la vista de complemento también debe crear subclases <xref:System.Windows.FrameworkElement>. El código siguiente muestra la vista de complemento del contrato, implementada como la `WPFAddInView` clase.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 En este caso, se deriva de la vista de complemento <xref:System.Windows.Controls.UserControl>. Por lo tanto, el complemento de la interfaz de usuario también debe derivar de <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 Aunque el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, el complemento es un <xref:System.Windows.FrameworkElement> (tal y como especifica el segmento de canalización de la vista de complemento). Por lo tanto, el <xref:System.Windows.FrameworkElement> deben convertirse a un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento. Este trabajo lo realiza el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 En el modelo de complemento, donde un complemento devuelve una interfaz de usuario (consulte [crear un complemento que devuelva una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), el adaptador de complemento, puede convertir el <xref:System.Windows.FrameworkElement> a un <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> También se debe llamar en este modelo, aunque deberá implementar un método desde el que se va a escribir el código para llamarlo. Para ello, reemplazar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implementar el código que llama a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> si el código que llama a <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> está esperando un <xref:System.AddIn.Contract.INativeHandleContract>. En este caso, el autor de la llamada será el adaptador del host, que se aborda en una subsección siguiente.  
  
> [!NOTE]
>  También necesita invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en este modelo para habilitar la tabulación entre la interfaz de usuario de la aplicación host y complemento de interfaz de usuario. Para obtener más información, vea "Limitaciones complementos de WPF" en [información general sobre complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Dado que el adaptador de conversión implementa una interfaz que se deriva de <xref:System.AddIn.Contract.INativeHandleContract>, también deberá implementar <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, aunque esto se omite cuando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> se reemplaza.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 En este modelo, la aplicación host suele esperar que la vista del host sea un <xref:System.Windows.FrameworkElement> subclase. El adaptador del host debe convertir el <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> después de que el <xref:System.AddIn.Contract.INativeHandleContract> cruza el límite de aislamiento. Dado que un método no llama a la aplicación host para obtener el <xref:System.Windows.FrameworkElement>, la vista host debe "return" la <xref:System.Windows.FrameworkElement> por que lo contiene. Por lo tanto, la vista host debe derivar de una subclase de <xref:System.Windows.FrameworkElement> que pueden contener otros [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], tales como <xref:System.Windows.Controls.UserControl>. El código siguiente muestra la vista de host del contrato, implementada como la `WPFAddInHostView` clase.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 Aunque el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, la aplicación host espera un <xref:System.Windows.Controls.UserControl> (tal y como especifica la vista del host). Por lo tanto, el <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse a un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento, antes de que se va a establecer como contenido de la vista de host (que se deriva de <xref:System.Windows.Controls.UserControl>).  
  
 Este trabajo lo realiza el adaptador del host, como se muestra en el código siguiente.  
  
  
  
 Como puede ver, el adaptador del host adquiere la <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a add en el lado del adaptador <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> (método) (este es el punto donde el <xref:System.AddIn.Contract.INativeHandleContract> cruza el límite de aislamiento).  
  
 El adaptador del host, a continuación, convierte el <xref:System.AddIn.Contract.INativeHandleContract> a un <xref:System.Windows.FrameworkElement> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Por último, el <xref:System.Windows.FrameworkElement> se establece como el contenido de la vista del host.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador y la vista de conversión en su lugar, se puede implementar el complemento derivando de la vista de complemento, como se muestra en el código siguiente.  
  
  
  
  
  
 En este ejemplo, puede ver una ventaja interesante de este modelo: los desarrolladores de complementos solamente necesitan implementar el complemento (ya que es la interfaz de usuario), en lugar de una clase de complemento tanto un complemento de la interfaz de usuario.  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador del host y la vista host creados, la aplicación host puede utilizar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos para abrir la canalización y adquirir una vista de host del complemento. Estos pasos se muestran en el código siguiente.  
  
  
  
 La aplicación host utiliza código típico de modelo de complementos de .NET Framework para activar el complemento, lo que implícitamente devuelve la vista del host a la aplicación host. Posteriormente, la aplicación host muestra la vista de host (que es un <xref:System.Windows.Controls.UserControl>) desde un <xref:System.Windows.Controls.Grid>.  
  
 El código para procesar las interacciones con el complemento de la interfaz de usuario se ejecuta en dominio de aplicación del complemento. Estas interacciones incluyen lo siguiente:  
  
-   Controlar la <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
-   Mostrando el <xref:System.Windows.MessageBox>.  
  
 Esta actividad está completamente aislada de la aplicación host.  
  
## <a name="see-also"></a>Vea también
- [Complementos y extensibilidad](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Información general sobre los complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
