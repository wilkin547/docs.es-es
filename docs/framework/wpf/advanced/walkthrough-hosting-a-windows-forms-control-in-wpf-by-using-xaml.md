---
title: 'Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f99dc055c5b5dc2f71008dce4e489025304bfceb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un conjunto de características enriquecidas. Sin embargo, en ocasiones, puede usar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas. Por ejemplo, puede tener una inversión sustancial en existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles, o tal vez tenga un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que proporciona la funcionalidad exclusiva.  
  
 En este tutorial se muestra cómo hospedar un formulario Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> controlar en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Para obtener una lista de código completa de las tareas mostradas en este tutorial, vea [hospedar un Control de formularios Windows Forms en WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="hosting-the-windows-forms-control"></a>Hospedar el control de Windows Forms  
  
#### <a name="to-host-the-maskedtextbox-control"></a>Para hospedar el control MaskedTextBox  
  
1.  Cree un proyecto de aplicación WPF denominado `HostingWfInWpfWithXaml`.  
  
2.  Agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  En el <xref:System.Windows.Window> elemento, agregue la siguiente asignación de espacio de nombres. El `wf` asignación de espacio de nombres establece una referencia al ensamblado que contiene el [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  En el <xref:System.Windows.Controls.Grid> elemento Agregar el código XAML siguiente.  
  
     El <xref:System.Windows.Forms.MaskedTextBox> control se crea como un elemento secundario de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Controles de Windows Forms y controles equivalentes de WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [Hospedar un Control de Windows Forms en WPF mediante XAML de ejemplo](http://go.microsoft.com/fwlink/?LinkID=160000)
