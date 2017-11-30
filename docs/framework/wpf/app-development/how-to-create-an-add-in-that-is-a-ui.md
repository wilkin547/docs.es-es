---
title: "Cómo: Crear un complemento que sea una interfaz de usuario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9151dd5fa36e3691361bcf6d7c7b281646982f3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Cómo: Crear un complemento que sea una interfaz de usuario
Este ejemplo muestra cómo crear un complemento que sea una [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que se hospedan en un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente.  
  
 El complemento es un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] control de usuario. El contenido del control de usuario es un botón único que muestra un cuadro de mensaje cuando se hace clic en él. El [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación independiente que hospeda el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] como el contenido de la ventana de la aplicación principal.  
  
 **Requisitos previos**  
  
 Este ejemplo se resaltan los [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos que habilitan este escenario y se da por supuesto lo siguiente:  
  
-   Conocimiento de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, incluida la canalización, complemento y desarrollo de host. Si no está familiarizado con estos conceptos, vea [complementos y extensibilidad](../../../../docs/framework/add-ins/index.md). Para obtener un tutorial que muestra la implementación de una canalización, un complemento y una aplicación host, consulte [Tutorial: crear una aplicación Extensible](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Conocimiento de la [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] extensiones a la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complemento, que puede encontrarse aquí: [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Ejemplo  
 Para crear un complemento que sea una [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] necesita un código concreto para cada segmento de la canalización, el complemento y la aplicación host.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Implementar el segmento de canalización del contrato  
 Cuando un complemento es un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], debe implementar el contrato para el complemento <xref:System.AddIn.Contract.INativeHandleContract>. En el ejemplo, `IWPFAddInContract` implementa <xref:System.AddIn.Contract.INativeHandleContract>, tal y como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista de complemento  
 Dado que el complemento se implementa como una subclase de la <xref:System.Windows.FrameworkElement> tipo, la vista de complemento también debe crear subclases <xref:System.Windows.FrameworkElement>. El código siguiente muestra la vista de complemento del contrato, implementada como la `WPFAddInView` clase.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 En este caso, la vista del complemento se deriva de <xref:System.Windows.Controls.UserControl>. Por lo tanto, el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] también debe derivarse de <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador de conversión  
 Aunque el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, el complemento es un <xref:System.Windows.FrameworkElement> (tal y como especifica el segmento de canalización de la vista de complemento). Por lo tanto, la <xref:System.Windows.FrameworkElement> deben convertirse en un <xref:System.AddIn.Contract.INativeHandleContract> antes de cruzar el límite de aislamiento. Este trabajo se realiza mediante el adaptador de conversión mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, como se muestra en el código siguiente.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 En el modelo de complemento donde un complemento devuelve un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (consulte [crear un complemento que devuelve una interfaz de usuario](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), convertir el adaptador de complemento de la <xref:System.Windows.FrameworkElement> a una <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>También debe llamar en este modelo, pero debe implementar un método desde el que se va a escribir el código para llamarlo. Para ello, reemplazar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> e implementar el código que llama <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> si el código que llama a <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> está esperando un <xref:System.AddIn.Contract.INativeHandleContract>. En este caso, el autor de la llamada será el adaptador del host, que se aborda en una subsección siguiente.  
  
> [!NOTE]
>  También necesita invalidar <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> en este modelo para habilitar la tabulación entre la aplicación host [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Para obtener más información, vea "Limitaciones de complemento WPF" en [WPF Add-Ins Overview](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Dado que el adaptador de conversión implementa una interfaz que se deriva de <xref:System.AddIn.Contract.INativeHandleContract>, también debe implementar <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, aunque se omite cuando <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> se invalida.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Implementar el segmento de canalización de la vista host  
 En este modelo, la aplicación host espera normalmente la vista del host sea un <xref:System.Windows.FrameworkElement> subclase. El adaptador del lado del host debe convertir el <xref:System.AddIn.Contract.INativeHandleContract> para un <xref:System.Windows.FrameworkElement> después de la <xref:System.AddIn.Contract.INativeHandleContract> cruza el límite de aislamiento. Dado que no se llama a un método por la aplicación host para obtener el <xref:System.Windows.FrameworkElement>, la vista de host debe "return" la <xref:System.Windows.FrameworkElement> por que lo contiene. Por lo tanto, la vista de host debe derivar de una subclase de <xref:System.Windows.FrameworkElement> que puede contener otros [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], como <xref:System.Windows.Controls.UserControl>. El código siguiente muestra la vista de host del contrato, implementada como la `WPFAddInHostView` clase.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Implementar el segmento de canalización del adaptador del host  
 Mientras que el contrato es un <xref:System.AddIn.Contract.INativeHandleContract>, la aplicación host espera un <xref:System.Windows.Controls.UserControl> (según se especifica en la vista de host). Por lo tanto, la <xref:System.AddIn.Contract.INativeHandleContract> deben convertirse en un <xref:System.Windows.FrameworkElement> después de cruzar el límite de aislamiento, antes de que se va a establecer como contenido de la vista de host (que deriva de <xref:System.Windows.Controls.UserControl>).  
  
 Este trabajo lo realiza el adaptador del host, como se muestra en el código siguiente.  
  
  
  
 Como puede ver, el adaptador del host adquiere la <xref:System.AddIn.Contract.INativeHandleContract> mediante una llamada del adaptador del complemento en el lado <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> (método) (éste es el punto donde la <xref:System.AddIn.Contract.INativeHandleContract> cruza el límite de aislamiento).  
  
 El adaptador de host, a continuación, convierte el <xref:System.AddIn.Contract.INativeHandleContract> a una <xref:System.Windows.FrameworkElement> mediante una llamada a <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Por último, el <xref:System.Windows.FrameworkElement> se establece como el contenido de la vista de host.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Implementar el complemento  
 Con el adaptador y la vista de conversión en su lugar, se puede implementar el complemento derivando de la vista de complemento, como se muestra en el código siguiente.  
  
  
  
  
  
 En este ejemplo, puede ver una ventaja interesante de este modelo: los desarrolladores de complementos solo se necesitan implementar el complemento (ya que es el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] también), en lugar de una clase de complemento y un complemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Implementación de la aplicación host  
 Con el adaptador de host y la vista de host creados, la aplicación host puede utilizar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] modelo de complementos para abrir la canalización y adquirir una vista de host del complemento. Estos pasos se muestran en el código siguiente.  
  
  
  
 La aplicación host usa típico [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] código de modelo de complementos para activar el complemento, lo que implícitamente devuelve la vista host a la aplicación host. Posteriormente, la aplicación host muestra la vista de host (que es un <xref:System.Windows.Controls.UserControl>) desde un <xref:System.Windows.Controls.Grid>.  
  
 El código para procesar las interacciones con el complemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se ejecuta en dominio de aplicación del complemento. Estas interacciones incluyen lo siguiente:  
  
-   Control de la <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
-   Mostrar la <xref:System.Windows.MessageBox>.  
  
 Esta actividad está completamente aislada de la aplicación host.  
  
## <a name="see-also"></a>Vea también  
 [Complementos y extensibilidad](../../../../docs/framework/add-ins/index.md)  
 [Información general sobre los complementos de WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
