---
title: "Tutorial: Hospedar un control de Windows Forms en WPF | Microsoft Docs"
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
  - "hospedar control de formularios Windows Forms en WPF"
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Tutorial: Hospedar un control de Windows Forms en WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un completo conjunto de características.  Sin embargo, en ocasiones puede que prefiera utilizar controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en páginas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Por ejemplo, es posible que disponga de un importante parque de controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] existentes, o un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que proporcione una funcionalidad única.  
  
 En este tutorial se muestra cómo hospedar un control <xref:System.Windows.Forms.MaskedTextBox?displayProperty=fullName> de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  
  
 Para ver una lista de código completa de las tareas mostradas en este tutorial, vea [Hosting a Windows Forms Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=160057).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Hospedar un control de Windows Forms  
  
#### Para hospedar el control MaskedTextBox  
  
1.  Cree un proyecto de aplicación de WPF denominado `HostingWfInWpf`.  
  
2.  Agregue referencias a los siguientes ensamblados.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Abra MainWindow.xaml en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  Asigne el nombre `grid1` al elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  En la vista Diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.  
  
6.  En la ventana Propiedades, haga clic en la pestaña **Eventos**.  
  
7.  Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. En la parte superior del archivo, agregue `Imports` o la instrucción `using` siguiente.  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. Presione F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Controles de formularios Windows Forms y controles equivalentes de WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)   
 [Ejemplo Hosting a Windows Forms Control in WPF](http://go.microsoft.com/fwlink/?LinkID=160057)