---
title: 'Cómo: Habilitar estilos visuales en una aplicación híbrida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 2d714ad020f2f7b6a6343c8f8e3901b59dfd23a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545628"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Cómo: Habilitar estilos visuales en una aplicación híbrida
Este tema muestra cómo habilitar [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual estilos en una [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hospedado en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicación basada en.  
  
 Si la aplicación llama a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método, la mayoría de los [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles usarán automáticamente estilos visuales cuando la aplicación se ejecuta en [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]. Para obtener más información, consulte [representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tema, consulte [habilitar estilos visuales en un ejemplo de aplicación híbrido](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Habilitar estilos visuales de Windows Forms  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Para habilitar estilos visuales de Windows Forms  
  
1.  Crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proyecto de aplicación denominado `HostingWfWithVisualStyles`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  En el cuadro de herramientas, haga doble clic en el <xref:System.Windows.Controls.Grid> icono para colocar un <xref:System.Windows.Controls.Grid> elemento en la superficie de diseño.  
  
4.  En la ventana Propiedades, establezca los valores de la <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> propiedades **automática**.  
  
5.  En la vista Diseño o la vista XAML, seleccione la <xref:System.Windows.Window>.  
  
6.  En la ventana Propiedades, haga clic en el **eventos** ficha.  
  
7.  Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.
  
8.  En el archivo MainWindow.Xaml.cs o MainWindow.Xaml.vb, inserte el siguiente código para controlar la <xref:System.Windows.FrameworkElement.Loaded> eventos.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Presione F5 para compilar y ejecutar la aplicación.  
  
     El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se dibuja con estilos visuales.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Deshabilitar estilos visuales de Windows Forms  
 Para deshabilitar los estilos visuales, basta con quitar la llamada a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Para deshabilitar estilos visuales de Windows Forms  
  
1.  Abra MainWindow.xaml.vb o MainWindow.xaml.cs en el Editor de código.  
  
2.  Marcar como comentario la llamada a la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
     El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se dibuja con el estilo predeterminado del sistema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
