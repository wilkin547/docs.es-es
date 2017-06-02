---
title: "C&#243;mo: Habilitar estilos visuales en una aplicaci&#243;n h&#237;brida | Microsoft Docs"
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
  - "aplicaciones híbridas [interoperabilidad con WPF]"
  - "estilos visuales [formularios Windows Forms]"
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Habilitar estilos visuales en una aplicaci&#243;n h&#237;brida
En este tema se muestra cómo habilitar los estilos visuales de [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Si la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, la mayoría de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] usarán automáticamente estilos visuales cuando la aplicación se ejecute en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].  Para obtener más información, consulte [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tema, vea [Enabling Visual Styles in a Hybrid Application Sample](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## Habilitar los estilos visuales de formularios Windows Forms  
  
#### Para habilitar los estilos visuales de formularios Windows Forms  
  
1.  Cree un proyecto de aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominado `HostingWfWithVisualStyles`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  En el Cuadro de herramientas, haga doble clic en el icono <xref:System.Windows.Controls.Grid> para colocar un elemento <xref:System.Windows.Controls.Grid> en la superficie de diseño.  
  
4.  En la ventana Propiedades, establezca los valores de las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> en **Auto**.  
  
5.  En la vista Diseño o la vista XAML, seleccione <xref:System.Windows.Window>.  
  
6.  En la ventana Propiedades, haga clic en la pestaña **Eventos**.  
  
7.  Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
8.  En MainWindow.xaml.vb o MainWindow.xaml.cs, inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Presione F5 para compilar y ejecutar la aplicación.  
  
     El control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se pinta con estilos visuales.  
  
## Deshabilitar los estilos visuales de formularios Windows Forms  
 Para deshabilitar los estilos visuales, basta con quitar la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
#### Para deshabilitar los estilos visuales de formularios Windows Forms  
  
1.  En el Editor de código, abra MainWindow.xaml.vb o MainWindow.xaml.cs.  
  
2.  Marque como comentario la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
     El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se pinta con el estilo predeterminado del sistema.  
  
## Vea también  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>   
 <xref:System.Windows.Forms.VisualStyles>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)   
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)