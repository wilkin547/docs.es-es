---
title: 'Tutorial: Organizar controles de formularios Windows Forms en WPF'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: f2cf82c54724a43a60fb9077c5731d4b4ad2cfd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a>Tutorial: Organizar controles de formularios Windows Forms en WPF
En este tutorial se muestra cómo usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de diseño para organizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles en una aplicación híbrida.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Usar la configuración de diseño predeterminada.  
  
-   Ajustar el tamaño al contenido.  
  
-   Usar el posicionamiento absoluto.  
  
-   Especificar el tamaño explícitamente.  
  
-   Establecer las propiedades de diseño.  
  
-   Entender las limitaciones del orden Z.  
  
-   Acoplar.  
  
-   Establecer la visibilidad.  
  
-   Hospedar un control que no se ajusta.  
  
-   Ajustar la escala.  
  
-   Girar.  
  
-   Establecer el relleno y los márgenes.  
  
-   Usar contenedores de diseño dinámico.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [organizar los controles de Windows Forms en WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).  
  
 Cuando haya terminado, tendrá un conocimiento de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] características de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicaciones basadas en.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
  
#### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto  
  
1.  Cree un proyecto de aplicación WPF denominado `WpfLayoutHostingWf`.  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
    -   System.Drawing  
  
3.  Haga doble clic en MainWindow.xaml para abrirlo en la vista XAML.  
  
4.  En el <xref:System.Windows.Window> elemento, agregue las siguientes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] asignación de espacio de nombres.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  En el <xref:System.Windows.Controls.Grid> el elemento establecido el <xref:System.Windows.Controls.Grid.ShowGridLines%2A> propiedad `true` y definir cinco filas y tres columnas.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a>Usar la configuración de diseño predeterminada  
 De forma predeterminada, el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento controla el diseño de hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
#### <a name="to-use-default-layout-settings"></a>Para usar la configuración de diseño predeterminada  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control aparece en el <xref:System.Windows.Controls.Canvas>. El control hospedado se dimensiona basándose en su contenido y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento cambiará de tamaño para alojar el control hospedado.  
  
## <a name="sizing-to-content"></a>Ajuste del tamaño al contenido  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento garantiza que el control hospedado tiene un tamaño para mostrar su contenido correctamente.  
  
#### <a name="to-size-to-content"></a>Para ajustar al contenido  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El tamaño de los dos nuevos controles de botón se ajusta para mostrar correctamente, la cadena de texto más larga y el tamaño de fuente y el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos cambian de tamaño para dar cabida a los controles hospedados.  
  
## <a name="using-absolute-positioning"></a>Usar el posicionamiento absoluto  
 Puede usar la ubicación absoluta para colocar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento en cualquier parte de la interfaz de usuario (UI).  
  
#### <a name="to-use-absolute-positioning"></a>Para usar el posicionamiento absoluto  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se coloca a 20 píxeles de la parte superior de la celda de cuadrícula y 20 píxeles desde la izquierda.  
  
## <a name="specifying-size-explicitly"></a>Especificar el tamaño explícitamente  
 Puede especificar el tamaño de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento utilizando el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades.  
  
#### <a name="to-specify-size-explicitly"></a>Para especificar el tamaño explícitamente  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se establece en un tamaño de 50 píxeles de ancho por 70 píxeles de alto, que es menor que la configuración de diseño de forma predeterminada. El contenido de la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control se reorganiza en consecuencia.  
  
## <a name="setting-layout-properties"></a>Establecer las propiedades de diseño  
 Siempre establece las propiedades relacionadas con el diseño del control hospedado mediante las propiedades de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Si establece las propiedades de diseño directamente en el control hospedado se producirán resultados imprevistos.  
  
 Establecer las propiedades relacionadas con el diseño en el control hospedado en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] no tiene ningún efecto.  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a>Para ver los efectos de establecer las propiedades en el control hospedado  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  En el Explorador de soluciones, haga doble clic en MainWindow.xaml. vb o MainWindow.xaml.cs para abrirlo en el Editor de código.  
  
3.  Copie el código siguiente en el `MainWindow` definición de clase.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación.  
  
5.  Haga clic en el **Click me** botón. El `button1_Click` conjuntos de controlador de eventos el <xref:System.Windows.Forms.Control.Top%2A> y <xref:System.Windows.Forms.Control.Left%2A> propiedades en el control hospedado. Esto hace que el control hospedado cambiar de posición dentro de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. El host conserva la misma área de la pantalla, pero el control hospedado se recorta. En su lugar, el control hospedado siempre debe rellenar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
## <a name="understanding-z-order-limitations"></a>Entender las limitaciones del orden Z  
 Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elementos siempre se dibujan encima de otros elementos WPF, y no se ven afectadas por orden z. Para ver este comportamiento en el orden z, haga lo siguiente:

1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> se pinta el elemento sobre el elemento de etiqueta.  


## <a name="docking"></a>Acoplamiento  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento admite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] acoplamiento. Establecer el <xref:System.Windows.Controls.DockPanel.Dock%2A> propiedad adjunta para acoplar el control hospedado en un <xref:System.Windows.Controls.DockPanel> elemento.  
  
#### <a name="to-dock-a-hosted-control"></a>Para acoplar un control hospedado  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> el elemento se acopla a la derecha de la <xref:System.Windows.Controls.DockPanel> elemento.  
  
## <a name="setting-visibility"></a>Establecer la visibilidad  
 Puede hacer que su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlar invisible o contraerlo estableciendo la <xref:System.Windows.UIElement.Visibility%2A> propiedad en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento. Cuando un control es invisible no se muestra, pero ocupa espacio de diseño. Cuando un control está contraído no se muestra ni ocupa espacio de diseño.  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a>Para establecer la visibilidad de un control hospedado  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Haga clic en el **haga clic aquí para hacer que sea invisible** botón para realizar la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento sea invisible.  
  
5.  Haga clic en el **, haga clic para contraer** botón para ocultar el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento del diseño completamente. Cuando el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] está contraído, los elementos adyacentes se reorganizan para ocupar su espacio.  
  
## <a name="hosting-a-control-that-does-not-stretch"></a>Hospedar un control que no se ajusta  
 Algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen un tamaño fijo y no se ajustan para rellenar el espacio disponible en el diseño. Por ejemplo, el <xref:System.Windows.Forms.MonthCalendar> control muestra un mes en un espacio fijo.  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a>Para hospedar un control que no se ajusta  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento se centra en la fila de cuadrícula, pero no se expande para rellenar el espacio disponible. Si la ventana es lo suficientemente grande, es posible que vea dos o más meses mostrados por hospedado <xref:System.Windows.Forms.MonthCalendar> control, pero éstos se centran en la fila. El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de diseño centra elementos que no se deben preverse para rellenar el espacio disponible.  
  
## <a name="scaling"></a>Cambiar escala  
 A diferencia de los elementos WPF, la mayoría de los controles de formularios Windows Forms no es escalable una continuamente. Para proporcionar una escala personalizada, invalide el <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> método. 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a>Para escalar un control hospedado mediante el comportamiento predeterminado  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El control hospedado y sus elementos adyacentes se escalan por un factor de 0,5. A pesar de ello, la fuente del control hospedado no se escala.

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a>Girar  
 A diferencia de los elementos WPF, controles de formularios Windows Forms no admiten la rotación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento no giran con otros elementos de WPF cuando se aplica una transformación de giro. Cualquier valor de giro distinto de 180 grados genera el <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> eventos.
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a>Para ver el efecto del giro en una aplicación híbrida  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. El control hospedado no se gira, pero sus elementos adyacentes se giran en un ángulo de 180 grados. Es posible que deba cambiar el tamaño de la ventana para ver los elementos.  
 

## <a name="setting-padding-and-margins"></a>Establecer el relleno y márgenes  
 Padding y Margin en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño son similares a padding y Margin en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Basta con establecer la <xref:System.Windows.Controls.Control.Padding%2A> y <xref:System.Windows.FrameworkElement.Margin%2A> propiedades en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento.  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a>Para establecer el relleno y los márgenes de un control hospedado  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  Presione F5 para compilar y ejecutar la aplicación. Se aplica la configuración de relleno y margen para hospedado [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles de la misma manera que se aplicarían en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="using-dynamic-layout-containers"></a>Usar contenedores de diseño dinámico  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proporciona dos contenedores de diseño dinámico, <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel>. También puede utilizar estos contenedores en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseños.  
  
#### <a name="to-use-a-dynamic-layout-container"></a>Para usar un contenedor de diseño dinámico  
  
1.  Copie el código XAML siguiente en el <xref:System.Windows.Controls.Grid> elemento.  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  En MainWindow.xaml.vb o MainWindow.xaml.cs, copie el código siguiente en la definición de clase.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  Agregue una llamada a la `InitializeFlowLayoutPanel` método en el constructor.  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento rellena el <xref:System.Windows.Controls.DockPanel>, y <xref:System.Windows.Forms.FlowLayoutPanel> organiza sus controles secundarios en el valor predeterminado <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Consideraciones sobre el diseño del elemento WindowsFormsHost](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [Organizar Windows Forms en el ejemplo WPF](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
