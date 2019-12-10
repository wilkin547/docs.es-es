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
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960116"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>Cómo: Habilitar estilos visuales en una aplicación híbrida
En este tema se muestra cómo habilitar los estilos visuales en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Si la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, la mayoría de los controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] usarán automáticamente los estilos visuales. Para obtener más información, consulte [Representar controles con estilos visuales](../../winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Para obtener una lista de código completa de las tareas que se ilustran en este tema, vea el [ejemplo de cómo habilitar estilos visuales en una aplicación híbrida](https://go.microsoft.com/fwlink/?LinkID=159986).  
  
## <a name="enabling-windows-forms-visual-styles"></a>Habilitar estilos visuales de Windows Forms  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>Para habilitar estilos visuales de Windows Forms  
  
1. Cree un proyecto de aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominado `HostingWfWithVisualStyles`.  
  
2. En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. En el cuadro de herramientas, haga doble clic en el icono de <xref:System.Windows.Controls.Grid> para colocar un elemento de <xref:System.Windows.Controls.Grid> en la superficie de diseño.  
  
4. En el ventana Propiedades, establezca los valores de las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> en **auto**.  
  
5. En Vista de diseño o en la vista XAML, seleccione el <xref:System.Windows.Window>.  
  
6. En el ventana Propiedades, haga clic en la pestaña **eventos** .  
  
7. Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.
  
8. En MainWindow. Xaml. vb o MainWindow.xaml.cs, inserte el siguiente código para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Presione F5 para compilar y ejecutar la aplicación.  
  
     El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se dibuja con estilos visuales.  
  
## <a name="disabling-windows-forms-visual-styles"></a>Deshabilitar estilos visuales de Windows Forms  
 Para deshabilitar los estilos visuales, simplemente quite la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>Para deshabilitar estilos visuales de Windows Forms  
  
1. Abra MainWindow.xaml.vb o MainWindow.xaml.cs en el Editor de código.  
  
2. Convoque como comentario la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.  
  
3. Presione F5 para compilar y ejecutar la aplicación.  
  
     El control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se pinta con el estilo predeterminado del sistema.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Representar controles con estilos visuales](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
